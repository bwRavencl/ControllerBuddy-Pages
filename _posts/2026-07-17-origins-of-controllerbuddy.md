---
layout: post
title: The Origins of ControllerBuddy
date: 2026-07-17 20:00:00 +0200
---

### Looking Back

While so far I have mainly posted development updates, today I felt like doing a different kind of post.  

In about two months, ControllerBuddy will celebrate the 12th anniversary of its first line of code being written.
When looking at the [Git commit history](https://github.com/bwRavencl/ControllerBuddy/commits/master/){:target="_blank"} of the ControllerBuddy project, one can see that my [first commit](https://github.com/bwRavencl/ControllerBuddy/commit/9faa5d861c059c22ab56615e23f616fc4385b9c5){:target="_blank"} in the project was created on Saturday, September 27, 2014, shortly after 2:00 AM.
At that point in time, the project was still called *RemoteStick* - but more on that later...

So get ready and fasten your seatbelts, because in this post I would like to take you on a wild ride back to the origins of ControllerBuddy to explain what influenced its design and how it all started.

### An Early Interest in Aviation

From a young age, I have been fascinated by all things aviation-related.
My grandfather, who enjoyed building and flying RC model airplanes, was a big influence on me.
Even before I reached kindergarten age, I would spend hours in his workshop watching him build and repair his models.
Often, I would accompany him to the flying field and watch him fly them.

### First Steps in Computing

Shortly before turning seven, I got my [first PC](http://kath-rottal.homeunix.org/computermuseum/Computer/Nixdorf/Nixdorf%208810%20M45/slides/Nixdorf%208810%20M45%20(1).html){:target="_blank"}, with an [Intel 486 DX2-66](https://en.wikipedia.org/wiki/I486){:target="_blank"} running [MS-DOS](https://en.wikipedia.org/wiki/MS-DOS){:target="_blank"} 6.22.  
Given my interest in aviation, I quickly got into flight simulators, starting with classic titles such as:

<ul style="display: grid; grid-template-columns: repeat(auto-fit, minmax(min(100%, 30ch), 1fr)); gap: 0.5rem 2.5rem; margin: 1rem 0; padding-left: 1.2rem">
  <li><a href="https://www.mobygames.com/game/228/secret-weapons-of-the-luftwaffe/" target="_blank">Secret Weapons of the Luftwaffe</a></li>
  <li><a href="https://www.mobygames.com/game/4226/air-duel-80-years-of-dogfighting/" target="_blank">Dogfight: 80 Years of Aerial Warfare</a></li>
  <li><a href="https://www.mobygames.com/game/773/tfx/" target="_blank">TFX</a></li>
  <li><a href="https://www.mobygames.com/game/1674/microsoft-flight-simulator-v50/" target="_blank">Microsoft Flight Simulator 5.0</a></li>
  <li><a href="https://www.mobygames.com/game/9967/shuttle-the-space-flight-simulator//" target="_blank">Shuttle: The Space Flight Simulator</a></li>
  <li><a href="https://www.mobygames.com/game/23350/mig-29-fulcrum/" target="_blank">MiG-29 Fulcrum</a></li>
  <li><a href="https://www.mobygames.com/game/1766/red-baron/" target="_blank">Red Baron</a></li>
  <li><a href="https://www.mobygames.com/game/1739/apache/" target="_blank">Apache</a></li>
  <li><a href="https://www.mobygames.com/game/2904/su-27-flanker/" target="_blank">Su-27 Flanker</a></li>
  <li><a href="https://www.mobygames.com/game/4540/fleet-defender/" target="_blank">Fleet Defender</a></li>
</ul>

At first, I was using a simple, two-axis, two-button joystick called the [InterAct PC Mission](https://web.archive.org/web/20260716125243/https://i.ebayimg.com/images/g/FDIAAOSwwxFl0fcC/s-l1600.jpg){:target="_blank"}, which I got for my birthday.  
After it broke, I was upgraded to an original [Logitech WingMan](https://www.dosdays.co.uk/media/logitech/wingman_2.png){:target="_blank"}, which even featured a small thumbwheel for throttle control!

From back then until today, flight simulation has always been an important part of my life.
I have spent time with almost every simulator I could get my hands on.

### First Steps With RC Aircraft

At around nine years old, I got my first RC model airplane, a [Multiplex Panda](https://wiki.rc-network.de/wiki/Panda_von_Multiplex){:target="_blank"} - a wonderful, beginner-friendly model.
Along with it, I also got my first RC transmitter, the [Multiplex Europa Sprint](https://wiki.rc-network.de/wiki/Multiplex_Fernsteuersender_%C3%9Cbersicht#europa_sprint){:target="_blank"}.

The reason I am mentioning all this is that the basic layout of RC transmitters, particularly the so-called [*Mode 2*](https://web.archive.org/web/20230506210607/http://www.rcgroups.com/forums/showatt.php?attachmentid=714749){:target="_blank"} layout, forms the basis of all my profiles for ControllerBuddy.
Mode 2 means that the left stick controls the throttle and rudder, while the right stick controls the ailerons and elevator. It's worth noting that the left stick's Y-axis is not spring-loaded, unlike a standard game controller you may be familiar with.

### Springs and Broken Hardware

Skipping ahead a few years, during the early 2000s, I started using an original [Sony DualShock](https://en.wikipedia.org/wiki/DualShock#DualShock){:target="_blank"} controller together with a special [USB converter](https://web.archive.org/web/20260716131123/https://m.media-amazon.com/images/I/517PedsgsgL.jpg){:target="_blank"}.
I mainly used the DualShock for RC simulators, such as [Aerofly Professional](https://web.archive.org/web/20040611111328/http://www.aerofly.de/index.html){:target="_blank"} and [Aerofly Professional Deluxe](https://web.archive.org/web/20070216094229/http://www.aerofly.de/www/gallery.html){:target="_blank"}.
While this felt like a good solution, at least for RC simulators, it had a big drawback: like all game controllers, the DualShock's sticks had a spring-loaded center position, which made it impossible to hold the throttle at a specific position without constantly applying pressure on the stick.

At the same time, for traditional flight simulators, I was using the legendary [Microsoft Sidewinder Force Feedback 2](https://en.wikipedia.org/wiki/Microsoft_SideWinder_Force_Feedback_2){:target="_blank"} joystick.
It was a great device for its time, but it had a very limited number of buttons and switches.  
Some of the sims I was flying around that time were:

<ul style="display: grid; grid-template-columns: repeat(auto-fit, minmax(min(100%, 30ch), 1fr)); gap: 0.5rem 2.5rem; margin: 1rem 0; padding-left: 1.2rem">
  <li><a href="https://www.mobygames.com/game-group/microsoft-flight-simulator-series" target="_blank">Microsoft Flight Simulator series</a></li>
  <li><a href="https://www.mobygames.com/game/1675/microsoft-combat-flight-simulator-wwii-europe-series//" target="_blank">Microsoft Combat Flight Simulator</a></li>
  <li><a href="https://www.mobygames.com/game/14558/il-2-sturmovik-forgotten-battles/" target="_blank">IL-2 Sturmovik: Forgotten Battles</a></li>
  <li><a href="https://www.mobygames.com/game/11732/lock-on-modern-air-combat/" target="_blank">Lock On: Modern Air Combat</a></li>
  <li><a href="https://www.mobygames.com/game/20430/falcon-40-allied-force/" target="_blank">Falcon 4.0: Allied Force</a></li>
  <li><a href="https://www.mobygames.com/group/8345/wings-over-series/" target="_blank">Wings over Vietnam / Europe</a></li>
  <li><a href="https://www.mobygames.com/group/6348/x-plane-series/" target="_blank">X-Plane 8 / 9</a></li>
</ul>

During the late 2000s, I got my first [HOTAS](https://en.wikipedia.org/wiki/HOTAS){:target="_blank"} setups: first a second-hand [Saitek X36](https://www.combatsim.com/htm/nov99/x36-usb.htm){:target="_blank"} from eBay, and then a [Saitek X52](https://en.wikipedia.org/wiki/Saitek_X52){:target="_blank"}.
Being second-hand, the X36 was already a bit worn out and broke down after a few months of use.
The throttle of the X52 also broke down after less than a year of use and was replaced by Saitek.
But even then, the X52 system had a weird issue where if it was used in conjunction with the Saitek mapping software, rapid, repeated button presses would trigger a hardware bug that caused the device to reset itself.
When I got the X52, the market for HOTAS setups was quite small compared to today, and the only other main option was the [Thrustmaster HOTAS Cougar](https://www.kultboy.com/joystick/224/){:target="_blank"}.

After my rather negative experiences with the Saitek devices, I was not willing to spend any more money on a new HOTAS setup.
I bought an original [Xbox 360 controller](https://en.wikipedia.org/wiki/Xbox_360_controller#Xbox_360_controller){:target="_blank"} with which I experimented a bit in conjunction with [Flight Simulator 2004](https://www.mobygames.com/game/microsoft-flight-simulator-2004-a-century-of-flight){:target="_blank"}, but with the mapping options available at the time, it was not really possible to get a good experience with a game controller.  
Before moving to a new apartment in 2013, I also had to downsize my setup, and thus used a very cheap and weird-looking [Mad Catz Cyborg V.1](https://web.archive.org/web/20260716140410/https://c1.neweggimages.com/productimage/nb1280/26-618-025-08.jpg){:target="_blank"} joystick for a while.
Since I was not flying so much at that time anyway, I did not mind the limitations of the device too much.

### War Thunder and X-Plane Lead the Way

In May of 2014, I got interested in [War Thunder](https://www.mobygames.com/game/73606/war-thunder/){:target="_blank"}, which had a very flexible controller mapping system that offered [relative axes](https://youtu.be/akzzSO4chZo){:target="_blank"}.
A few months earlier, I had also acquired a [DualShock 3](https://en.wikipedia.org/wiki/DualShock#DualShock_3){:target="_blank"} controller.
Together with War Thunder's mapping capabilities, it allowed me to get an excellent flying experience after some experimentation.  
Basically, I was able to recreate the Mode 2 layout I was familiar with from flying RC planes and expand on it.
Using the left stick's Y-axis for throttle control was no longer a problem in War Thunder because I could map it as a relative axis to overcome the spring loading.
Crucially, it was also possible to use modifiers to bind the look axes onto the same stick.
While you cannot compare War Thunder with a more sophisticated simulator like DCS, the basic layout behind all ControllerBuddy profiles today was established right then.

After spending a few months with War Thunder, I wanted to get back into traditional flight simulators - especially [X-Plane 10](https://www.mobygames.com/game/60600/x-plane-10-global-edition/), which I had used for years.
That's when I wrote a small X-Plane plugin in [C](https://en.wikipedia.org/wiki/C_(programming_language)){:target="_blank"} called [X-Gamepad](https://github.com/bwRavencl/X-Gamepad){:target="_blank"}.
This plugin allowed me to use a game controller with X-Plane 10 in a very similar way to War Thunder, but with a few improvements.  

I was so happy with the result that I never wanted to go back to using a HOTAS or joystick again, and I started to think about how I could use a game controller with other flight simulators as well.  
At that time, I was using a [2012 Macbook Pro](https://en.wikipedia.org/wiki/MacBook_Pro#Retina_(2012%E2%80%932016)){:target="_blank"} running [OS X](https://en.wikipedia.org/wiki/MacOS){:target="_blank"}.
While War Thunder and X-Plane 10 ran natively on OS X, I dearly missed a modern combat flight simulator like Lock On, which I had played during the mid-2000s on Windows.
Lock On was already more than 10 years old at that time and ran reasonably well within a Windows virtual machine.
This meant I could run it on my Macbook, but I couldn't control it the way I wanted...

### The RemoteStick Prototype

So, I came up with a plan to take what I had built specifically for X-Plane, split it up into generic building blocks, and make it universally usable with every simulator.

The central goals for my new project were:
1. Support any flight simulator running on Windows.
2. Support any game controller on any host operating system (in my case, OS X).
3. Provide a graphical user interface to build and edit profiles.

Part of the solution to the first problem came in the form of [vJoy](https://sourceforge.net/projects/vjoystick/), which was developed by Shaul Eizikovich as open-source software.
It is a virtual joystick driver for Windows that allows you to create virtual joysticks and feed them input from any source.
Instead of targeting a specific game, my new approach would emulate joystick, keyboard, and mouse inputs.
This would make it usable with every simulator out there.

Since I was using the DualShock 3 controller connected via Bluetooth to my Macbook Pro, I needed a way to get the input from the controller into Windows.
Looping the Bluetooth connection through the virtual machine was not possible at that time, so I needed a way to send the inputs over the network.
I decided on a two-part solution consisting of a server application running on the host operating system, which would read the input from the controller, apply the necessary mappings, and send the resulting data to a client application running on Windows.
The client would then feed that input into vJoy and the Windows API to simulate input events.

I chose to write the server application in [Java](https://en.wikipedia.org/wiki/Java_(programming_language)){:target="_blank"} since it was fast, a good fit for cross-platform support, and the language I had the most experience with.
For the smaller client, I went with [C#](https://en.wikipedia.org/wiki/C_Sharp_(programming_language)) because vJoy came with examples for it and it felt the most natural for accessing Windows APIs.

Within a few weeks, I had cobbled together a rough prototype of both applications, which I named *RemoteStick Server* and [*RemoteStick Client*](https://github.com/bwRavencl/RemoteStickClient){:target="_blank"} - that was in the autumn of 2014.
Then after the new semester at university started, work on RemoteStick stalled.

### The Impetus

A short time later, I became quite annoyed with the declining quality of OS X, as well as the sub-par performance I was experiencing with X-Plane and other games on my MacBook, so I decided it was time to switch systems again.
I settled on a ZOTAC mini-PC, the [ZBOX EN760](https://www.zotac.com/de/product/mini_pcs/en760){:target="_blank"}, running Linux and was quite happy for a while.
For the better part of a year, I mainly ran X-Plane and War Thunder on my new Linux PC, gradually improving X-Gamepad and expanding upon it (for example, by adding support for helicopters and add-on aircraft that required specific commands).

Then, after visiting the [Jet World Masters 2015](https://youtu.be/2LNY_hlcnmg) in Leutkirch, the itch to fly some modern military jets got me again.
I decided to give [DCS World](https://www.digitalcombatsimulator.com/){:target="_blank"} a try on my new system.
Since this was by no means a powerful gaming PC, it barely ran DCS.
Luckily, only a short time later, version 1.5 of DCS was released, which greatly improved performance with the introduction of Direct3D 11.
Also, because this was well before the recent rise of Linux as a gaming platform, I grudgingly had to switch over to Windows to enjoy DCS.  
But merely switching to Windows was not enough, I also needed a way to fly in DCS with my preferred control scheme.

### Two Intense Weeks

So, I dug out the RemoteStick prototype I had written almost a year earlier and began to extend it.
Basically, I wanted to get rid of the C# client and have it all in a single application that could run as a single instance feeding directly to vJoy when operating locally.
Nevertheless, I decided to keep the client-server mode alive as an option.
Now, however, the client and server would be the exact same Java application running in different modes.

While much of the foundation was already there, I worked incredibly hard on it for about two weeks, and what came out in the end was the first version of ControllerBuddy.
Since the main focus of the application was no longer remote control, I changed the name from RemoteStick to ControllerBuddy.
All of this happened between the end of August and the beginning of September 2015.

This initial version of ControllerBuddy worked great for me.
I used it extensively with DCS at first, and then began diving back into other simulators such as [IL-2 Sturmovik: Cliffs of Dover](https://www.mobygames.com/game/51970/il-2-sturmovik-cliffs-of-dover/){:target="_blank"} and [IL-2 Sturmovik: Battle of Stalingrad](https://www.mobygames.com/game/88507/il-2-sturmovik-battle-of-stalingrad/){:target="_blank"}.

### Building an Ecosystem

Compared to the software today, the 2015 version of ControllerBuddy still had many rough edges.
It was designed purely for my personal use and lacked not only many features it has today - like the Overlay or Profile Visualizations - but it also did not come with any documentation.  

While browsing flightsim subreddits, I occasionally encountered people looking for advice on how to use a game controller for flying.
I knew I had the exact tool they needed, but setting it up, configuring the simulators for it, and explaining the concepts behind ControllerBuddy would have been incredibly time-consuming.  
So, over the following years, I refined not only the application itself but also the whole ecosystem around it to make it accessible to everyone.  
Essential components like the [website](https://controllerbuddy.org){:target="_blank"} you are on now, the [Install-Script](https://github.com/bwRavencl/ControllerBuddy-Install-Script), and the [videos](https://youtube.com/playlist?list=PLCrcgiMjHO83vtSqCKeNuXt_ZotBfFQ81&si=eQH4lJqFRTy7DXJH){:target="_blank"} came into being.  
On the profile side, while I started out with a handful of profiles for DCS modules, I gradually expanded the official [profile repository](https://github.com/bwRavencl/ControllerBuddy-Profiles){:target="_blank"} to support more and more simulators, both new and old.
Today, the repository counts a total of 94 profiles!

While I still see myself as the primary user of ControllerBuddy, quite a few features and enhancements over the years were directly based on feedback from a slowly growing user base.
I cannot tell exactly how many people use ControllerBuddy, but based on release download statistics, I estimate there are probably at least a few hundred long-term users.  
This might be a good point to say: if you are a user and enjoy ControllerBuddy, let me know!
Drop a line on [Discord](https://discord.gg/2Sg9ggZrAp){:target="_blank"}.
While most people join the Discord to get technical help - which was the main intention behind it - it is always wonderful to hear from people who are simply enjoying what I built.

### Ten Years and 33,000 Lines Later

When I wrote the first line of code for this hobby project back in 2014, I would never have guessed that I would still be working on it more than a decade later, nor would I have believed that I would put more than 10,000 hours into this side project, which now spans more than 33,000 lines of code.

All in all, I am still very happy with the technical foundation I chose back then.
Java has proven to be a solid choice for this project.  
While Java may seem like an unusual choice for a gaming tool, I couldn't be happier with the decision.
In fact, over the last ten years, there have been countless improvements to the platform that make it better suited than ever for developing desktop applications and small utilities.  
For a long time now, ControllerBuddy has been shipped as a [self-contained application](https://docs.oracle.com/en/java/javase/26/docs/specs/man/jpackage.html){:target="_blank"} with a download size of about 30 MB.
In an era where shipping desktop apps at sizes of hundreds of megabytes is the norm, that's a number I can live with.  
The same goes for memory consumption: after a few recent optimizations, ControllerBuddy uses about 100 to 150 MB of RAM - an amount that is completely negligible, even on low-end systems.

Many of the architectural choices, like the client-server architecture, have also proven to be highly powerful and extensible over the years.
While I have refactored many essential parts and switched out underlying libraries more than once, the basic architecture remains the same as it was in 2014 because it simply works.

I still work on ControllerBuddy almost every day in one way or another.
While there are periods with relatively little change, during which only dependencies get updated, there are also times when I have grander ideas.
These include user interface overhauls or even monumental tasks like switching out the underlying input system from [GLFW](https://www.glfw.org/){:target="_blank"} to [SDL3](https://www.libsdl.org/), which I undertook in early 2025.
Most of the time, such ideas just come to me on a whim when I learn something new or get excited to try out a promising technology.  
Next to working on the core application, there are always things to improve or expand upon on the website or the Install-Script, or a new simulator module gets released and a profile has to be created for it.
All I'm saying is that it never gets boring...

### Finishing Line

Congratulations on making it this far, and thank you very much for your interest!

I have no idea how many people actually read these posts.
If I had to guess, I'd say the number is probably very small.  
That's why I'd love to hear from you!
I want to know what kind of posts you find interesting and learn a bit more about my audience.
Your feedback helps me decide how many technical details to include and whether it's worth my time to continue writing posts like this one.
The best way to reach me is via [Discord](https://discord.gg/2Sg9ggZrAp){:target="_blank"}.
