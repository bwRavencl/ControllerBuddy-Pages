---
layout: post
title: August 2026 Status Update
date: 2026-08-12 13:00:00 +0200
---

### What's New in ControllerBuddy <!-- markdownlint-disable-line heading-increment -->

As the first half of August already comes to a close, it is time for another status update on the development of ControllerBuddy.
Since the last regular update at the end of June, quite a few developments have piled up.
As always, I will focus on the major changes and skip the routine housekeeping.

### Release of DCS F-14 B(U) and IL-2 Korea

Let us start with two new releases in the flight simulation community.

At the end of July, [Heatblur](https://store.heatblur.com/){:target="_blank"} released their updated version of the F-14 Tomcat, the [F-14 B(U)](https://www.digitalcombatsimulator.com/de/products/planes/f-14bu/){:target="_blank"}, for DCS.
I quickly overhauled the existing DCS F-14 profiles and added a dedicated profile for the B(U) variant.

Then, on August 4th, [1C Game Studios](https://1cgs.net/en){:target="_blank"} released the long-awaited [IL-2 Korea](https://il2-series.com/en/store/korea/new/){:target="_blank"} out of early access.
Over the following weekend, I began building the corresponding ControllerBuddy profile.
Fortunately, the existing configuration script for [IL-2 Great Battles](https://il2sturmovik.com/){:target="_blank"} was easily adaptable to IL-2 Korea.  
Thanks to a fellow [Linux user](https://github.com/silv3rshi3ld){:target="_blank"} who devised a [patch](https://github.com/HansKristian-Work/vkd3d-proton/pull/3202){:target="_blank"} for [vkd3d-proton](https://github.com/HansKristian-Work/vkd3d-proton){:target="_blank"} to fix initial terrain rendering issues, IL-2 Korea now runs flawlessly on my Linux setup, and I have been thoroughly enjoying it.  
For the Linux-users among you, I already published [a guide](https://github.com/bwRavencl/ControllerBuddy-Linux-Guides/blob/master/IL-2_Korea.md) for setting up the Steam version IL-2 Korea on Linux for usage with ControllerBuddy as part of my [ControllerBuddy-Linux-Guides](https://github.com/bwRavencl/ControllerBuddy-Linux-Guides){:target="_blank"} collection.

I particularly appreciate what 1C did with the new *Multimenu* - it greatly improves controller usability in general and integrates seamlessly with ControllerBuddy.
The menu is ideal for secondary commands that are rarely used during flight, eliminating the need for dedicated ControllerBuddy bindings.
For a sim without clickable cockpit controls, this is a very welcome feature.

### Refactoring Intervals Into Rates

While a run mode is active, ControllerBuddy continuously polls controller hardware for state changes across axes and buttons.
Up until version 1.9, polling relied on fixed sleep intervals.
Advanced users might be familiar with the *Poll Interval* setting in the *Global Settings* tab, which directly controlled the sleep duration between polling iterations.

However, this approach did not account for the execution time ControllerBuddy itself spent processing input.
As a result, the effective polling behavior varied depending on profile complexity and system performance.
While the practical impact was minimal, this dependency was undesirable from an engineering perspective.

In version 1.9, the fixed sleep interval has been replaced with dynamic calculations based on the actual time elapsed since the previous poll.
At the same time, I converted the *Poll Interval* option into a *Polling Rate* setting.
Instead of specifying milliseconds (e.g., 1 ms), users now configure frequency in Hertz (e.g., 1000 Hz), which is far more intuitive for input devices.
For consistency, the *Key Repeat Interval* in the *Profile Settings* tab was also refactored to *Key Repeat Rate*.

### Support for Dynamic Polling Rates

Previously, the default poll interval was set to 1 ms - the lowest possible value - resulting in a polling rate of roughly 1000 Hz.
Apart from a few high-end custom devices, standard gamepads (such as an Xbox controller) operate at a hardware polling rate of only 125 Hz.
Polling at 1000 Hz meant most polls detected no new inputs, unnecessarily wasting CPU cycles.

The main reason the interval was originally kept so low involves output smoothness.
Actions that drive relative mouse movements or camera controls depend directly on the dispatch rate to remain smooth, because reading input and making operating system API calls both occur on the main processing thread.
While a bump from 125 Hz to 1000 Hz is barely noticeable on a desktop cursor, it makes a substantial difference when panning camera controls in a flight simulator.

To solve this trade-off, I introduced dynamic polling rates.
ControllerBuddy can now run at a much lower frequency when high output precision is unnecessary, saving CPU cycles and battery life on handhelds like the Steam Deck or laptops.
The moment an action sensitive to output frequency becomes active, ControllerBuddy automatically switches from the minimum rate to the maximum rate.
Users can customize these two states via *Min. Polling Rate* (default: 125 Hz) and *Max. Polling Rate* (default: 1000 Hz).

While testing at 1000 Hz, I noticed that garbage collection cycles under [SerialGC](https://perfmatrix.com/serial-garbage-collector-gc/){:target="_blank"} could occasionally cause micro-stalls in the input thread.
To eliminate this, I switched back to the default [Garbage-First (G1)](https://en.wikipedia.org/wiki/Garbage-first_collector){:target="_blank"} collector.
SerialGC was originally chosen to minimize the memory footprint on small heaps, but modern G1 delivers better pause times with negligible overhead.

Additionally, I further tuned the JVM memory configuration.
ControllerBuddy now operates with an initial heap size of 24 MB and a maximum of 48 MB, reducing the overall memory footprint more than ever before.

### Client-Server Optimizations

Another simple yet effective improvement targets ControllerBuddy's networking code.  
As mentioned in my [previous post](/#blog/origins-of-controllerbuddy){:target="_blank"}, ControllerBuddy was originally designed to operate across a network in client-server mode.
Although relatively few users rely on this setup, I continue to maintain it because it fits naturally into the overall architecture.

While refining the polling loop, I realized there was an easy way to drastically reduce network traffic between the server and the client.
Previously, the server transmitted state updates on every single poll, even when no inputs had changed - which is especially problematic at fast polling rates.
Now, state updates are sent only when an actual change in controller state occurs.  
Best of all, this change was entirely server-side and required no modifications to the network protocol or the client.

### Preventing Null Pointer Exceptions

To continuously improve code quality and safety, I integrated [JSpecify](https://jspecify.dev/){:target="_blank"} annotations throughout the entire codebase.
This was a sizeable effort, but well worth it: in combination with static analysis tools like [NullAway](https://github.com/uber/NullAway){:target="_blank"}, this makes the code more robust and maintainable while helping elimina a number of redundant null checks that had accumulated over the years.

### Mode Switching Improvements

Last but not least, I also refined how ControllerBuddy handles mode switches to eliminate unexpected control delays.

When a button is held down to switch modes - such as using the left stick to look around the cockpit instead of controlling the rudder and throttle axes - ControllerBuddy disables the stick for a moment upon releasing that button.
This safety pause gives the analog stick time to snap back to center, preventing an aircraft from violently jerking when primary flight controls are re-engaged.

Previously, this safety pause always enforced a strict one-second timer.
If a button was quickly pressed again to jump back into that mode, the stick remained unresponsive until that full second ran out.
ControllerBuddy now detects when a mode is re-entered and cancels the safety timer immediately.
This maintains protection against accidental inputs when leaving a mode, while ensuring rapid control toggles feel completely seamless.
