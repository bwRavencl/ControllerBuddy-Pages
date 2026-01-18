---
layout: post
title: Looking Back at 2025 - Progress and Milestones
date: 2025-12-07 16:00:00 +0100
---

### The News Section Debuts!

A long-term goal since ControllerBuddy's inception 11 years ago has been to make it more accessible and better documented. While the software was always perfectly usable, the addition of the website, tutorial videos, and install script over the past years have steadily made it easier for a wider audience to set it up. As a direct result, the number of users from all over the world has steadily increased over the last few years.

In the same vein, in order to communicate new features and changes more effectively, I decided to introduce a dedicated news section on the website, which you are reading right now! If all goes well, I plan to post regular updates about new releases, features, and other relevant topics here in the future.

With the year coming to an end, I naturally tend to reflect on the progress made over the past twelve months, making it the perfect theme for this very first news post.  
So, without further ado, let's dive into what was achieved in the past months:

### The Year of the Linux Desktop

For me, 2025 was somewhat of a turning point with my switch to [Linux](https://kernel.org/){:target="_blank"} (I use [Arch](https://archlinux.org/){:target="_blank"}, by the way) as my daily driver.

Having used Linux for gaming and simming on and off during the mid-2000s, I'm by no means a novice to Linux as a desktop operating system. Over the past few years, mainly due to [Valve Software's](https://www.valvesoftware.com/){:target="_blank"} initiatives, gaming on Linux has become easier than ever. Compatibility and performance have improved by leaps and bounds, reaching the point where Linux is now a viable alternative to Windows, for most flight simulators.

Although Linux support is now more prominent, ControllerBuddy will of course continue to fully support Windows as well as a first-class citizen.

### January: Enhancing Linux Support

ControllerBuddy has supported Linux for quite some time, but a major obstacle was the inability to run the configuration scripts within [Wine](https://www.winehq.org/){:target="_blank"} / [Proton](https://github.com/ValveSoftware/Proton){:target="_blank"}. This was because they required Windows PowerShell 5.1 to run, and while PowerShell 7+ works great with Wine, there is no feasible way to get older releases working.

Therefore, I decided to update all configuration scripts to support PowerShell 7+ while maintaining compatibility with PowerShell 5.1 for a seamless out-of-the-box experience on Windows.  
Additionally, a few minor changes were necessary to support the virtual joystick device on Linux.

While launching the scripts within a Wine prefix on Linux is a bit more involved than on Windows, the functionality offered is now exactly the same on both platforms.

### February: The Shift to SDL3

A recurring theme throughout the year was my continuous effort to reduce ControllerBuddy's direct dependencies, either by eliminating them or replacing them with more modern alternatives.

For handling input devices, ControllerBuddy had relied on [GLFW](https://www.glfw.org/){:target="_blank"} for several years. This was coupled with a lot of custom code to support advanced features of Sony controllers via a proprietary HID driver. On Windows, [jxinput](https://github.com/StrikerX3/JXInput){:target="_blank"} was used for native XInput controller support, and on Linux, more custom code was needed to implement what was frankly pretty poor rumble support.

With the release of [SDL3](https://www.libsdl.org/){:target="_blank"} in January and its support arriving shortly thereafter in [LWJGL](https://www.lwjgl.org/){:target="_blank"}, I saw an opportunity to switch ControllerBuddy to this brand-new backend. This move effectively reduced the amount of code required for handling all these different controller types to zero, while simultaneously improving compatibility.

The only negative consequence of the switch to SDL3 was that I had to strip support for [OpenVR](https://github.com/ValveSoftware/openvr){:target="_blank"}-based overlays. While this is certainly a shame, I doubt it significantly affected many users. OpenVR has largely been replaced by [OpenXR](https://www.khronos.org/openxr/){:target="_blank"}, and supporting the latter is a completely different challenge.

All in all, the switch to SDL3 was probably the biggest change to ControllerBuddy this year, and I couldn't be happier with it. SDL is a joy to work with, and its APIs and documentation are simply superb!

### March: Adopting the FFM API

Continuing my quest to reduce dependencies, the next goal was to eliminate the [JNA](https://github.com/java-native-access/jna){:target="_blank"} library, which allows convenient access to native functions from within Java.

* On Windows, JNA was used by ControllerBuddy primarily to communicate with the [vJoy](http://vjoystick.sourceforge.net/){:target="_blank"} driver and the Windows API.
* On Linux, JNA was used as part of [linuxio4j](https://github.com/bithatch/linuxio4j){:target="_blank"} to communicate with the UINPUT module.

While JNA is easy to use, a modern alternative, the [Function and Memory (FFM) API](https://openjdk.org/jeps/442){:target="_blank"}, was finalized with Java 22. It represents the future-proof and most efficient way to access native APIs from within the JVM.  
Since I constantly strive to keep ControllerBuddy up-to-date with current Java releases and utilize new language and JVM features as soon as possible, I completely replaced JNA with FFM and eliminated linuxio4j entirely by writing my own FFM-based UINPUT interface.  
While likely not noticeable to users, the switch to FFM made calling native code within ControllerBuddy measurably more efficient and state-of-the-art.

### July: Modernizing the Build System

My efforts to remove third-party dependencies also extended to the [Gradle](https://gradle.org/){:target="_blank"} build script.

I relied on multiple plugins, which occasionally made it harder for me to update to the latest Gradle versions. With the imminent release of Gradle 9, I decided to remove all plugins that are no longer actively developed.

Additionally, I took this opportunity to port the entire build script from [Groovy](https://groovy-lang.org/){:target="_blank"} to [Kotlin](https://kotlinlang.org/){:target="_blank"}.

### August: New Tutorial Videos

During August, I tackled a topic I had been avoiding for a long time: the creation of up-to-date video tutorials to guide new users through installing and using ControllerBuddy. I had put this task off for so long because I'm simply not very proficient in video production.

After getting to grips with [kdenlive](https://kdenlive.org/){:target="_blank"}, I was able to produce new [videos](https://www.youtube.com/playlist?list=PLCrcgiMjHO83vtSqCKeNuXt_ZotBfFQ81){:target="_blank"} that, while certainly not Oscar-worthy, should lower the barrier to entry for new users significantly.

### November: Overlay and Button Action Improvements

November saw the introduction of horizontal overlay axis indicators.  
I was able to put this feature to good use immediately with the release of the [C-130J module](https://www.digitalcombatsimulator.com/en/products/planes/c-130j/){:target="_blank"} for [DCS](https://www.digitalcombatsimulator.com/){:target="_blank"}. The C-130J uses a horizontal relative axis for the nose wheel steering tiller, and a horizontal indicator made perfect sense for displaying its exact position in the overlay.

Also during November, with the 1.6 release of ControllerBuddy, button actions were enhanced to also support single immediate and on-release activations.

### December: SVG Rendering and First Donation

At the beginning of this month, I replaced the previously used [Apache Batik](https://xmlgraphics.apache.org/batik/){:target="_blank"} library with the more modern [jsvg](https://github.com/weisJ/jsvg){:target="_blank"} alternative.  
jsvg is used to render the [SVG](https://en.wikipedia.org/wiki/SVG){:target="_blank"} visualizations of profiles.  
While I had to introduce more custom code to handle the correct sizing of the [viewBox](https://developer.mozilla.org/en-US/docs/Web/SVG/Reference/Attribute/viewBox){:target="_blank"} (i.e. the viewport of an SVG), the switch had the benefit of reducing the overall size of the entire ControllerBuddy folder by about 3 to 4 MB, depending on the platform.

Also, in fact just yesterday, I was very happily surprised with the first donation I received from a ControllerBuddy user, who pressed the donation button that I first introduced a few months ago.  
I am so grateful for this wonderful gesture, as it perfectly validates the appreciation for the long hours I have poured into this project over the last decade. Thank you!

### Future Plans

With my switch to Linux, I also started documenting how I personally set up my flight simulators on Linux with Proton in conjunction with ControllerBuddy.  
At first, I only created rough notes intended to allow me to easily reproduce my results in the future. Recently, I decided to start turning these notes into fine, detailed guides that, in the future, other people will be able to follow to start simming on Linux *the ControllerBuddy way*.

### Thank You and Happy Holidays!

Thank you for using ControllerBuddy, for following its journey, and for reading this annual review.  
I look forward to sharing more updates with you in the new year.  
Until then, happy holidays and all the best for 2026! 🎁🎄🎆
