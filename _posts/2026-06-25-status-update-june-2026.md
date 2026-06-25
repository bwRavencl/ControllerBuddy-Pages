---
layout: post
title: June 2026 Status Update
date: 2026-06-25 23:00:00 +0200
---

### Sun, Sweat, and Status Reports

With a major heatwave currently sweeping across Central Europe, summer is well and truly here. But despite the sweltering temperatures, I am keeping up with my resolution to post regular updates on the development of ControllerBuddy. Here is a look at the most important news and changes from June and the better part of May 2026.

### Assignments Tab Overhaul

In the [May 2026 Status Update](#news/status-update-may-2026){:target="_blank"}, I reported on the refinements I worked on for the *Component Editor*. During the last few weeks, I took it upon myself to overhaul the *Assignments* tab.

While the overall layout and functionality did not change, the aesthetics changed quite a bit. Although the old look was very functional, it clearly lacked the outline of a controller.  
The previous iteration of this central part of the user interface was introduced in 2018. At that time, ControllerBuddy did not yet have a userbase to speak of. Consequently, looks were really not that important back then. In fact, at that point in time, ControllerBuddy did not even use the [FlatLaf](https://www.formdev.com/flatlaf/){:target="_blank"} Look And Feel, which was introduced during 2019.

All in all, I hope the new look catches on with people. As always, when reworking older sections, small bugs and inconsistencies get fixed, and as a result, the overall quality of the codebase improves - it was no different in this case.

### Reducing Memory Footprint

Motivated by the seemingly never-ending surge in computer hardware costs, I took some time to reduce the memory footprint of ControllerBuddy. While ControllerBuddy was never a resource hog to begin with - before my efforts, it typically consumed between 200 and 300 MB of RAM - it now sits at about 180 to 200 MB.

The reduction in RAM usage comes primarily from the fact that I disabled the [C2 compiler](https://en.wikipedia.org/wiki/HotSpot){:target="_blank"} of the JVM. While in theory this reduces the optimization level that long-running code in the JVM can reach and thus theoretically increases the CPU footprint, ControllerBuddy is in no way CPU-bound and typically uses less than 1% of CPU anyway. Therefore, there is no measurable drawback to giving up a tiny bit of runtime optimization in exchange for reducing the memory footprint by nearly one-third.

### Issues with Controller Detection

One of the most regular issues encountered by people using ControllerBuddy involves controller detection problems. Very often, these issues concern third-party Xbox controllers. This sometimes results in lengthy troubleshooting sessions with users I am trying to help. Recently, I had another one of these sessions with a new user who had trouble getting their PDP Afterglow controller to work.

Under the hood, ControllerBuddy relies on [SDL3](https://libsdl.org/){:target="_blank"} for controller abstraction. Depending on the operating system and the particular controller model, SDL uses different APIs to communicate with the controller hardware. On Windows, for Xbox-compatible controllers, this is usually [XInput](https://en.wikipedia.org/wiki/DirectInput#XInput){:target="_blank"}.

In this particular case, the solution to the problem was to force SDL to fall back to other APIs by disabling XInput via a [special environment variable](https://wiki.libsdl.org/SDL3/SDL_HINT_XINPUT_ENABLED){:target="_blank"}. While this fixed the problem for this user, explaining to non-computer-savvy users how to create an environment variable - which may or may not solve the issue for them - can be a pretty lengthy process.  
Thus, in order to simplify things, I added a new setting to ControllerBuddy that allows disabling XInput specifically for the application via a checkbox in the *Global Settings* tab. I hope that this new option will help people self-troubleshoot similar issues in the future.

### DCS F-100D, Legacy Sims, and IL-2 Korea

June 2026 also saw the release of the [Grinelli Designs](https://grinnellidesigns.com/){:target="_blank"} [F-100D Super Sabre](https://grinnellidesigns.com/f-100d/){:target="_blank"} for DCS. I was really looking forward to this new module, and I have to say I have not been disappointed at all. Flying the F-100D has been great fun so far, and waiting for it was well worth the time. For a first commercial release, the Grinelli folks really did an awesome job!  
After the module was released on June 12th, I quickly got to work and was able to provide an official ControllerBuddy profile for it merely a few hours later.

Before jumping into the F-100D, I spent some of my time diving back into old sims from the 90s on my [Steam Deck](https://store.steampowered.com/steamdeck){:target="_blank"}. I particularly enjoyed my time with the recent Steam re-release of [F-22: Air Dominance Fighter](https://store.steampowered.com/app/3146140/F22_Air_Dominance_Fighter){:target="_blank"} and with the classic [F-15 Strike Eagle III](https://en.wikipedia.org/wiki/F-15_Strike_Eagle_III){:target="_blank"}, [Falcon 3.0](https://en.wikipedia.org/wiki/Falcon_3.0){:target="_blank"}, and my childhood favorite [Jetfighter III](https://en.wikipedia.org/wiki/Jetfighter_III){:target="_blank"}.  
As a result, the profiles for these games have received some tweaks and improvements.

Finally, I am looking forward to the upcoming release of [IL-2 Korea](https://il2-korea.com/){:target="_blank"} in August. While this new entry to the IL-2 series is already available in early access, I decided to wait for its release on Steam. After getting hold of it, I plan to quickly come up with a profile and configuration script for it, assuming the current [issues](https://github.com/valvesoftware/proton/issues/9906){:target="_blank"} it has when running on Linux with [Proton](https://github.com/ValveSoftware/Proton){:target="_blank"} are solved by then.
