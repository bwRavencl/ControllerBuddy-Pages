---
title: ControllerBuddy

carousels:
  - images:
    - image: https://raw.githubusercontent.com/bwRavencl/ControllerBuddy/master/example_screenshot_6.png
    - image: https://raw.githubusercontent.com/bwRavencl/ControllerBuddy/master/example_screenshot_7.png
    - image: https://raw.githubusercontent.com/bwRavencl/ControllerBuddy/master/example_screenshot_8.png
    - image: https://raw.githubusercontent.com/bwRavencl/ControllerBuddy/master/example_screenshot_1.png
    - image: https://raw.githubusercontent.com/bwRavencl/ControllerBuddy/master/example_screenshot_2.png
    - image: https://raw.githubusercontent.com/bwRavencl/ControllerBuddy/master/example_screenshot_3.png
    - image: https://raw.githubusercontent.com/bwRavencl/ControllerBuddy/master/example_screenshot_4.png
    - image: https://raw.githubusercontent.com/bwRavencl/ControllerBuddy/master/example_screenshot_5.png

accordion: 
  - title: What is the pupose of this FAQ?
    content: |
        Firstly, it will present to you a way to control all aspects of modern flight simulators solely via a gamepad in an intuitive fashion. This means no joystick, keyboard or even mouse will be strictly necessary anymore to control your virtual aircraft and the simulator's user interface.  
        The presented method is applicable to most desktop flight simulators and types of airplanes and helicopters.

        Secondly, it shall serve as a guide for **ControllerBuddy**, an advanced open-source game controller mapping software developed by the author of this document.
  - title: What is ControllerBuddy?
    content: |
        ControllerBuddy is a highly advanced gamepad mapping software, which supports the creation of input profiles for complex target applications such as flight simulators.  

        In addition to the simplistic mapping of buttons and axes of a physical game-controller to keyboard and mouse input, ControllerBuddy also supports the feeding of input commands to a virtual joystick, provided by the awesome vJoy device driver created by Shaul Eizikovich.  

        ControllerBuddy's goal is to enable the user to control target applications solely via a gamepad and not having to reach for a keyboard or mouse at any point in time.
  - title: What exactly do you mean by the term 'gamepad'?
    content: |
        A game controller as used by current generation gaming consoles, with two analog sticks, a D-Pad, a number of face buttons, two triggers and two shoulder buttons.

        Popular examples for this type of input device are:
        - DualShock 4 Controller  
        - DualSense Controller  
        - Xbox 360 Controller  
        - Xbox One Controller  
        - Xbox Series X\|S Controller
  - title: Why would I use a gamepad to control a flight simulator?
    content: |
        While a joystick or yoke in combination with a throttle is probably the most obvious choice for controlling a virtual aircraft, the usage of a gamepad offers a number of advantages, which for some people can make it an interesting alternative:
        - Gamepads, especially the ones name above, offer a high build quality and are very sturdy, which sadly is a virtue only few of the joysticks on the market can offer, that from my experience can break often and are sometimes hard to repair.
        - Many people who own a gaming PC already own a gamepad to begin with. These days joysticks have become more of a rarity compared to the heyday of flight simulators during the 1990s. This is something especially newcomers to the flight simulation genre may be facing or if you are a veteran virtual-pilot and are trying to get a friend interested in this great hobby, who does not (yet) own the necessary peripherials.
        - When it comes to comparing the price tag of a high quality gamepad with the one of a HOTAS- or yoke-based system, the gamepad is obviously the much cheaper choice, making it especially interesting for newcomers, who are just undertaking their first steps in the genre of flight simulation.  
        - While a joystick with a throttle can be considered the bare minimum to start out with, many more senior virtual pilots will say that you will also need a rudder pedals and a headtracking unit to take your experience to a satisfactory level. Depending on your desk you may also need a suitable mounting solution to install your input decvices at a proper height. All these things are not only an additional cost factor, but can also quickly come in someone's way if your PC is not dedicated to your flying hobby.  
        - Even if you call all of the above named devices your own, you most likely will still depend on a keyboard and mouse to be able to navigate the menus of your simulator und to handle switches and buttons inside the virtual cockpit, this means having to take your hands off frin the throttle and stick, which can be cumbersome, which is especially true for VR.
        - A wireless gamepad used in the way as described in this guide, offers you exceptional freedom in the sense that you are no longer tightly bound to a seating position from which all of the necessary input devices are reachable. If your screen is large enough, flying from a comfortable spot on your couch may come to one's mind.  
        - While a gamepad does certainly not come as close to the controls found in a real plane, it still can emulate the controls more or less acurately. If upmost realism is your top priority, you will probably prefer to use a classic stick, but be aware that one set of input devices can usually only realistically represent one particular model of aircraft from the real world. If you like to fly general aviation aircraft, airliners, military jets and helicopters, you actually would need vastly different sets of input devices for at least each one of these categories.
        - Physical strain is another issue I would like to mention: From my experience flying with a gamepad for a long time now has been very comfortable and a lot less straining than with a joystick and throttle, I find this especially true for helicopter flying, where constant very precise inputs are necessary.
  - title: What are the drawbacks of a using a gamepad compared to a HOTAS or yoke?
    content: |
        - The major issue of a gamepad is that is does usually not posess any *relative* axes. A relative axis is an axis which is not spring loaded and stays in the position you last put it into when taking your fingers off from it. Relative axes are the preferred means to control the throttle, propeller pitch and mixture of an aircraft.  
        - Since the two sticks of a gamepad are a lot smaller than a dedicated joystick, they offer a smaller range and thus require more precise inputs.  
        - Due to the declared goal to control an entire aircraft with a gamepad that offers am ample, but still limited number of buttons and axes, we can not avoid using them for more than one function. This esentially means that a very complex aircraft with many buttons on its real-life controls, will probably also require a very complex input profile for your gamepad. This may require more time to get familiar with, compared to a HOTAS-system which already closely resembles the controls of the real aircraft.  
        - Lastly als already mentioned above, a gamepad will certainly never be able to offer the same realism than a well-made joystick or yoke.
  - title: How can we get around these drawbacks?
    content: |
        Instead of binding axes and buttons directly to our gamepad we use a *virtual* joystick provided by the excellent **vJoy**. Created by Shaul Eizikovich as open-source software, vJoy is a device driver that provides virtual joysticks that can be controlled from other applications (in our case ControllerBuddy).

        In **ControllerBuddy** we can create **profiles** that define a mapping of the physical axes and buttons of our gamepad to so called **actions**. Among other things, actions can manipulate the axes of the vJoy device or simulate mouse and keyboard inputs. This allows us for example to work around the above mentioned issue of missing relative axes on our gamepad.  
        Due to the limited number of axes and buttons of a gamepad, a single axis or button usually must serve multiple purposes. This can be handled by so called **modes**. For example an axis normally assigned to the throttle can become the axis controlling for controlling the view (i.e. looking up and down), while swiching to view-mode.

        Another function of ControllerBuddy is the so called **overlay**. The overlay is a transparent window that is displayed on top of the simulator to show the currently active mode and the state of the axes of the virtual axes. This is especially useful for relative axes, for example it is very hard to tell the current throttle setting without such an indication. The overlay can be freely moved around the screen and configured to include only indicators for certain axes of interest.  
        ControllerBuddy also provides a special mode in which an **on-screen-keyboard** is displayed that can be controlled via specialized actions. This is helpful when you want to type in chat messages without having to rely on a physical keyboard. This can be especially interesting to people who would like to use ControllerBuddy in combination with VR.
        Since the required inputs vary greatly from simulator to simulator and even from aircraft to aircraft, a custom tailored profile for each simulator, and in case of complex titles such as DCS for each aircraft, is necessary. These profiles can be edited within ControllerBuddy and be permanently stored as files on your computer.

        [![Overlay](https://github.com/bwRavencl/ControllerBuddy/raw/master/example_screenshot_7.png)](https://github.com/bwRavencl/ControllerBuddy/raw/master/example_screenshot_7.png)
  - title: How do modes (shift-states) work?
    content: |
        **Switching between modes** is done via a specialized type of action for mode-switching that can be assigned to a button of your gamepad. A mode-swichting action can be configured to either temporarily switch to a mode, for as long as the corresponding button is depressed or to permanently toggle a mode on and off by a single press of the button. Depending on the concrete usage scenario one or the other configuration may be preferable.  
        All axes and buttons that do not have a different actions assigned by the currently active mode retain the actions of the mode one level below.
  - title: What does a basic profile look like?
    content: |
        Usually you will want to create a custom profile at least for each simulator and in many cases even for each simulated aircraft. Yet most profiles will have a common foundation which can look as follows:

        - For the **primary controls**, the basic idea behind the control scheme is based on the way radio-controlled aircraft are steered with a radio transmitter:  
        - The right stick controls pitch and roll, just like a typical joystick.
        - The left stick's vertical axis is mapped to a relative vJoy axis that controls the throttle, while the horizontal axis of the stick controls the yaw.

        Due to the small range of the physical axes of a gamepad, you will want to configure at least a small dead zone and some expo (i.e. *curves*) in-game for the vJoy axes that control pitch, yaw and roll.  
        Note that the right stick should never be mapped to anything else in other modes, since having control over the pitch and yaw of the aircraft is vital in all situations, however the left stick can be reused for other functions in other modes, because manipulating the throttle and yaw is usually not required at all times.

        - **Secondary controls**, such as flaps, landing gear and air brake can be mapped to the D-Pad.  
        Note that the gear mapped to the lower part of the D-Pad, sice it is physically located on the lower side of the aircraft, while the air brake is usually located on-top of the fuselage or wings and thus mapped to the upper part of the D-Pad. Following this logic it only makes sense to use the horizontal segement of the D-Pad for the flaps. Mapping the controls in such a way makes profiles a lot more intuitive and natural to use.

        - **Looking around** is done by pressing and holding the right shoulder button, which activates the *Look Mode*:
        - In *Look Mode* the left stick controls the view and is used for looking around. Usually you will want to use two relative vJoy axes for mapping these controls.
        - The D-Pad shifts the head up and down and left and right.
        - The Y and A buttons shift the head forward and back.
        - Pressing the right stick down zooms the view in, pressing the left stick down zooms out.

        - **Changing and centering the view** is done with the X button:
        - As soon as the X button gets pressed the view is centered and the zoom level gets reset.  
        In order to achieve this, usually multiple actions must be performed:
            - The relative vJoy axes that are mapped to looking around must be centered - this can be done via configuring two specialized actions called *Reset vJoy Axis* that target the respective vJoy axes.
            - The in-game commad(s) for centering the view in all view axes must be fired.
            - The in-game command for resetting the zoom level must be fired.
        - Additionally, while holding the X button the *View Mode* gets activated:  
        In *View Mode* the D-Pad is used to switch between the most important views, such as cockpit view, external views or map view.

        - **Triming the aircraft** can be done while activating *Trim Mode* by pressing and holding the left shoulder button:
        - In *Trim Mode* the D-Pad is used to change the pitch and roll trim, while the X and B buttons change the yaw trim.
        - For some aircraft a *Center Trim* command may be available and can for example be mapped to the A button.
        - For most helicopters no dedicated Mode is necessary, instead the left shoulder button should simply be mapped to a *Force Trim* command if available.

        - The *Mouse Mode* allows controlling basic mouse functions via your gamepad. It is activated by pressing down the left stick.  
        In this case the Mode-switching is configured to toggle between *Default Mode* and *Mouse Mode*, this means that pressing down the left stick once activates the *Mouse Mode* and pressing it again toggles it off again.  
        When *Mouse Mode* is active you can perform mouse inputs as follows:
        - The left stick controls the mouse cursor
        - The right trigger performs a left-click
        - The left trigger performs a right-click
        - The Start button performs a middle-click
        - Pressing D-Pad up or down scrolls up or down

        - The **On-Screen Keyboard** can be toggled on and off by pressing down the right stick.  
        In *On-Screen Keyboard Mode* the following actions are configured:
        - The D-Pad moves the key selector of the On-Screen Keyboard around.
        - The A button presses down the currently selected On-Screen Keyboard key - if the A button is released also the respective key on the keyboard gets released.
        - The B button locks the currently selected On-Screen Keyboard key down - the key stays in the pressed down state until it is unlocked in the same way.
        - The Y button releases all keys of the On-Screen Keyboard  
        By locking down multiple keys it is possible to perform key-strokes that consist of multiple keys pressed simultaneously.  
        When the *On-Screen Keyboard Mode* is toggled off by pressing down the right stick, all locked keys are automatically released.

        This concludes the foundation on which a profile can expand upon. It is important to note, that you should keep these basics of all your profiles as similar as possible, this will make it a lot easier when switching between different aircraft models and simulators!  
        As you may have noticed we practically have already covered all the typical controls required for flying a virtual aircraft and controlling the most important aspects of the simulator. And most importantly we now still have quite a few buttons available for mapping some of the more specialized controls of an aircraft.

        ##### Default Mode:
        [![Basic Profile Default Mode](assets/svg/basic_profile_default_mode.svg)](assets/svg/basic_profile_default_mode.svg)

        ##### Look Mode (*hold RB*):
        [![Basic Profile Look Mode](assets/svg/basic_profile_look_mode.svg)](assets/svg/basic_profile_look_mode.svg)

        ##### View Mode (*hold X*):
        [![Basic Profile View Mode](assets/svg/basic_profile_view_mode.svg)](assets/svg/basic_profile_view_mode.svg)

        ##### Trim Mode (*hold LB*):
        [![Basic Profile Trim Mode](assets/svg/basic_profile_trim_mode.svg)](assets/svg/basic_profile_trim_mode.svg)

        ##### Mouse Mode (*toggled by pressing left stick*):
        [![Basic Profile Mouse Mode](assets/svg/basic_profile_mouse_mode.svg)](assets/svg/basic_profile_mouse_mode.svg)

        ##### On-Screen Keyboard Mode (*toggled by pressing right stick*):
        [![Basic Profile On-Screen Keyboard Mode](assets/svg/basic_profile_on_screen_keyboard_mode.svg)](assets/svg/basic_profile_on_screen_keyboard_mode.svg)
  - title: What about more complex profiles?
    content: |
        The more complex the simulated aircraft is, the more time it will take to create a profile and to figure out what is most intuitive. However nothing is impossible and in the author's experience even the most complex systems can be mapped to the limited amount of buttons a gamepad offers.
        
        Here are just a few general guidelines on how to approach this task:
        1. Start out with binding everything found on the stick and throttle of the real aircraft. For aircraft that follow the [HOTAS](https://en.wikipedia.org/wiki/HOTAS){:target="_blank"} concept, this will already include almost everything required for operating the aircraft and its systems.
        2. Now you can concentrate on bindings that offer additional bindings for convenience, e.g.:
        - Propeller and Mixture levers
        - Sensor controls (e.g. Radar and [FLIR](https://en.wikipedia.org/wiki/Forward-looking_infrared){:target="_blank"})
        - Countermeasure controls (Chaff, Flare and [ECM](https://en.wikipedia.org/wiki/Electronic_countermeasure){:target="_blank"}) 
  - title: How do I create such profiles?
    content: |
        A profile can never exist on its own, it always targets a specific game. This game must be configured in such a way that the inputs ControllerBuddy simulates map to the actual actions.  
        For example if ControllerBuddy is configured to simulate a press of the *G*-Key to raise and lower the landing gear, the game must be configured in such a way that the *G*-Key is actually mapped to the landing gear function.  
        Most games come with certain default mappings, it is recommended to stick with these mappings and build ControllerBuddy profiles in such a way that they target the default mappings. If a certain function does not have a mapping by default, it should be mapped to a button of the vJoy device - this must be done in ControllerBuddy as well as in the game. The same applies to all axis functions.  
        For example if you want to map the elevator, the following two steps are required:
        1. Map an axis (or button) of your gamepad to a vJoy axis inside ControllerBuddy
        2. Map the vJoy axis to the function in the game

        The following steps shall help you to decide on how to proceed when mapping a game function to your controller:
        - Mapping an axis function:
         
           In the game        | map the axis function to an unused axis of the vJoy device
           In ControllerBuddy | create a matching mapping axis / button of your gamepad to the axis of the vJoy device
        - Mapping a button / keyboard function that have a default keyboard shortcut:
         
           In the game        | lookup the keyboard shortcut
           In ControllerBuddy | create a matching mapping from a button / axis of your gamepad to the keyboard shortcut
        - Mapping a function that is not mapped by default:
         
           In the game        | map the function to an unused button of the vJoy device
           In ControllerBuddy | create a matching mapping a button / axis of your gamepad to the button of the vJoy device

        **Important:** it is suggested to export or backup your game configuration and keep it alongside your ControllerBuddy profile.

        What follows are some general guidelines on how to proceed when creating a new profile from scratch:
        1. In the game remove all existing default mappings (axes and buttons) to your gamepad, otherwise they will interfere with the mappings done via ControllerBuddy and the vJoy device.  
        (This step is not required if you are using a DualShock 4 or DualSense gamepad!)
        2. Start by mapping the main control axes (elevator, ailerons, rudder, throttle) as part of the *Default Mode*
        3. Add a *Look Mode* and a *View Mode* as described above
        4. Add mappings for basic functions such as: landing gear, flaps, brakes. Usually these mappings should be part of the *Default Mode*. However exceptions can be made: in more modern aircraft such as the F/A-18 Hornet, the flaps are only used during takeoff and landing and in addition other functions such as the tailhook fall into the same category. Since we only have a finite amount of gamepad buttons available it makes sense to put all of these functions only used during takeoff and landing into a dedicated mode.
        5. Add dedicated modes for special functions, e.g. sensor controls.  
        When asigning a button of your gamepad to enable / disable a mode, you have to options:
         - Enabled toggling: this means that a single press of the button toggles the mode on, pressing it again toggles it off
         - Disabled toggling: this means that the mode is only active for as long as you keep the button pressed down
        In general, toggling is more useful for modes that should stay active for a longer amount of time, e.g. a mode dedicated to operating sensor controls.
        6. In rare cases it may make sense to double bind certain axes or buttons within a mode even for unrelated functions. For example, in my profiles I often double bind the triggers of the gamepad to the left and right brake and at the same time for dropping ordanance and firing the gun. This can be be done because while sitting on the ground (when it makes sense to use the brakes), the weapon systems are turned off, so pulling the trigger has no effect at that point. Vice verse, when in combat and the weapon safety is off, pulling the trigger will also activate the corresponding brake, however since you are in the air and the landing gear is retracted, braking will have no effect.
        7. Experiment around! After some time you can come up with input profiles quite fast, but only actual usage of a profile will show up its weaknesses. In that case ControllerBuddy's interface makes it easy for you to make some quick alterations, try them out, and only keep them if you like how they feel.
  - title: What are the hardware and software requirements?
    content: |
        - A gamepad supported by the [SDL_GameControllerDB](https://github.com/gabomdq/SDL_GameControllerDB){:target="_blank"} project (e.g. Xbox Controller, DualShock 4 or DualSense)
        - Windows 7 / 8 / 10 / 11 (x64) or Linux (x64)
  - title: Where can I get the necessary software?
    content: |
        - [vJoy](https://github.com/jshafer817/vJoy/releases/latest){:target="_blank"}
        - [ControllerBuddy](https://github.com/bwRavencl/ControllerBuddy/releases/latest){:target="_blank"}
  - title: How much does it cost?
    content: |
        It's all free!
  - title: How do I set the software up and how does the ControllerBuddy user-interface work?
    content: |
        Please check out the [Getting Started section](#getting-started).  
        Linux users should refer to the [README.md](https://github.com/bwRavencl/ControllerBuddy#linux){:target="_blank"} for setup instructions.
  - title: Where can I get premade profiles?
    content: |
        ControllerBuddy's author is maintaining an exhaustive list of profiles for almost all current flight simulators. All of these profiles, along with matching game configurations can be found in a special GitHub repository called [ControllerBuddy-Profiles](https://github.com/bwRavencl/ControllerBuddy-Profiles){:target="_blank"}.  
        To download the a ZIP-package containing the latest versions of all profiles and configurations [click here](https://github.com/bwRavencl/ControllerBuddy-Profiles/archive/refs/heads/master.zip){:target="_blank"}.  
        Please follow the instructions listed in the repository's [README.md](https://github.com/bwRavencl/ControllerBuddy-Profiles#instructions){:target="_blank"} to get you started.  
        Additionally is is recommended to check out the visualization for each profile either inside ControllerBuddy's visualization tab, after loading the profile, or [below](#profiles) on this website.
  - title: Why is the overlay not displayed?
    content: |
        Please try the following solutions:
        - Ensure the overlay is enabled in the profile settings tab.
        - When running on Windows, make sure the  [Windows Fullscreen Optimizations](https://devblogs.microsoft.com/directx/demystifying-full-screen-optimizations/) are enabled.
        - When running a Vulkan- or OpenGL-based application on a Windows system with an NVIDIA GPU, in the NVIDIA Control Panel, try forcing the setting called 'Vulkan/OpenGL present method' to 'Prefer layered on DXGI swapchain', as shown [here](https://www.reddit.com/r/nvidia/comments/yf6hiw/psa_you_can_now_elevate_openglvulkan_games_to_a/).
        - When running on a Linux system with X11, make sure you have the display compositor enabled, [this article](https://linux-gaming.kwindu.eu/index.php?title=Compositor_(X11)) explains how to configure the Compositor for the most common desktop environments - just remember for ControllerBuddy you will want the compositor enabled not disabled!
  - title: How can I ensure the vJoy device takes precedence over any physical controllers?
    content: |
        - On Windows, make sure the vJoy device is the preferred input device - proceed as follows:
          1. Start -> Run -> enter `joy.cpl` -> OK
          2. Advanced -> Preferred device -> select 'vJoy Device'
        - On Linux in combination with Wine, you can entirely disable physical input devices with the following steps:
          1. From a terminal session run `wine control`
          2. Select each physical input device listed below 'Connected' and click 'Disable' - make sure you do not disable the device called 'ControllerBuddy Joystick'.  
             There should be no devices listed below 'Connected (xinput device)'.
  - title: What is haptic feedback?
    content: |
        Haptic feedback is a special feature, which can be enabled for relative axis mappings. It will cause the controller to vibrate slightly, when either end of a relative axis, or a user defined axis position (dentent), is reached. Support for this feature is implemented for the most common controllers on both Windows and Linux.
  - title: Which controller do you recommend?
    content: |
        The author either recommends a Microsoft Xbox Series X\|S Controller or a Sony DualSense or DualShock 4 controller.  
        Both Sony controllers feature a touchpad, which is supported by ControllerBuddy to function like the typical touchpad of a laptop computer.
  - title: Why is my Xbox Controller not recognized by ControllerBuddy?
    content: |
        Please verify that you do **not** have Steam's 'Xbox Extended Feature Support Driver' installed.  
        The following screenshot shows how to uninstall this driver from within Steam. Please note that you will need to reboot your PC afterwards.
        
        [![Xbox Extended Feature Support Driver](https://steamuserimages-a.akamaihd.net/ugc/2012593630419989216/C1FE814A0D119E67EF7736BD0DC90E34773E0833/)](https://steamuserimages-a.akamaihd.net/ugc/2012593630419989216/C1FE814A0D119E67EF7736BD0DC90E34773E0833/)
  - title: How can I keep track of the battery status of wireless controllers?
    content: |
        When using a Sony DualSense or DualShock 4 controller or a XInput controller on Windows, ControllerBuddy reads the battery state of the device and displays it in the tooltip of the tray icon. For both Sony controllers, ControllerBuddy also adjusts the lighting to keep the user aware of the battery state at a glance.
  - title: Can I use ControllerBuddy in VR?
    content: |
        ControllerBuddy allows the user to fully control all input aspects (game controls and the UI) solely via a gamepad. Hence, the user never has to put his gamepad aside in order to reach for a mouse or keyboard. This makes ControllerBuddy predestined for a VR environment, in which the user cannot see any peripherials.  
        Both the overlay and the on-screen-keyboard of ControllerBuddy are available as overlays inside OpenVR applications, just as they are in a regular non-VR application.
  - title: Is there a way to automate launching ControllerBuddy and loading profiles from within simulators?
    content: |
        ControllerBuddy supports multiple command line parameters which are listed [here](https://github.com/bwRavencl/ControllerBuddy/blob/master/README.md#command-line-parameters){:target="_blank"}.  
        ControllerBuddy is a single-instance application, this means that if an instance of ControllerBuddy is already running, and the user launches a second instance, any supplied command line parameters are passed on to the first instance and the second instance terminates immediately.  
        This behavior can be useful in automation scripts to integrate ControllerBuddy tightly with other applications. For more information check out [ControllerBuddy-DCS-Integration](https://github.com/bwRavencl/ControllerBuddy-DCS-Integration){:target="_blank"}, an exemplary integration of ControllerBuddy into [DCS World](https://www.digitalcombatsimulator.com){:target="_blank"}.
  - title: Is there a way to automatically install and update ControllerBuddy?
    content: |
        The easiest way to setup ControllerBuddy is via the [ControllerBuddy-Install-Script](https://github.com/bwRavencl/ControllerBuddy-Install-Script){:target="_blank"}.  
        The script streamlines the installation and updating of ControllerBuddy itself and of the profiles available as part of the [ControllerBuddy-Profiles](https://github.com/bwRavencl/ControllerBuddy-Profiles) repository.  
        Please note, on Windows it is mandatory that you install [Git for Windows](https://git-scm.com/download/win){:target="_blank"} first, in order to run the script.
  - title: What else should I be aware of as a user of ControllerBuddy?
    content: |
        ControllerBuddy is in permanent active development and has a very small userbase as of this writing. This means that new versions are released very frequently and sometimes stuff might break. As there is currently no update functionality included a user should regularly check the latest release page for updates.  
        Please note, that with major updates the profile file-format might change which can lead to incompatibilities. If that happens ControllerBuddy will notify the user when loading an incompatible profile.
  - title: How can I report bugs?
    content: |
        Should you encounter any bugs, please use the GitHub issue system to report them to the author.  
        Always include information about your system, including the operating system version and the controller hardware you use.  
        Also please take the time to provide exact steps on how to reproduce the encoutered issue.
  - title: How can I contribute?
    content: |
        ControllerBuddy is free and open-source software, licensed under the [GNU General Public License v2.0](https://github.com/bwRavencl/ControllerBuddy/blob/master/LICENSE){:target="_blank"}.  
        This principally enables anyone to take part in its development.  
        If you feel a useful feature is missing feel free to implement it and open a create a pull-request on GitHub. Please be aware that the author will only accept features that he personally finds useful and adhere to his standards for code quality.
  - title: How can I get in touch with you?
    content: |
        Please refer to the [ControllerBuddy Discord](https://discord.gg/2Sg9ggZrAp){:target="_blank"} if you have any additional questions that were not covered here.
---

## Welcome

Ever wanted to fly in your favorite **flight simulators with a gamepad**?  
> Then **ControllerBuddy** is what you have been looking for!

On this page you will find everything you need to take to the skies with your favorite game controller.

## Screenshots

{% include carousel.html height="65" unit="%" duration="10" number="1" %}

## Getting Started

<iframe width="100%" height="315" src="https://www.youtube.com/embed/nHhCSEwaTEA" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

<p class="note-box">
  <strong>
    Note:
    <br>
    With the <a href="https://github.com/bwRavencl/ControllerBuddy-Install-Script">ControllerBuddy-Install-Script</a> there is now an automated way to install and update ControllerBuddy and configure your flight sims for the official profiles!
  </strong>
</p>

Links:
- [Download vJoy](https://github.com/jshafer817/vJoy/releases/latest){:target="_blank"}
- [Download ControllerBuddy](https://github.com/bwRavencl/ControllerBuddy/releases/latest){:target="_blank"}
- [Download ControllerBuddy-Profiles](https://github.com/bwRavencl/ControllerBuddy-Profiles/archive/refs/heads/master.zip){:target="_blank"}

## FAQ

{% include accordion.html %}

## Profiles

All of the profiles listed below can be obtained from the author's [ControllerBuddy-Profiles repository on GitHub](https://github.com/bwRavencl/ControllerBuddy-Profiles){:target="_blank"}.  
Please note that these profiles are continuously updated and improved by the author.

The links below will take you to a visualization of each profile:

<div id="profile-iframe-container" class="profile-iframe-container fade-out">
  <iframe id="profile-iframe" class="profile-iframe"></iframe>
  <button class="close-button" onclick="closeProfileViewer()"></button>
</div>

<div class="profiles-container">
    {% assign sorted_files = site.static_files | sort_natural: 'basename' %}
    {% for file in sorted_files %}
    {% assign relative_path = file.path | remove_first: '/' %}
    {% assign folder = relative_path | split: '/' | first %}
    {% if folder  == 'profiles' %}
    {% assign title = relative_path | split: '/' | last | replace: '_', ' ' | split: '.html' %}
    <button onclick="openProfileViewer(event, '{{ relative_path }}')" class="profile-item">{{ title }}</button>
    {% endif %}
    {% endfor %}
</div>

## About

[ControllerBuddy](https://github.com/bwRavencl/ControllerBuddy){:target="_blank"} is free and open-source software made with ❤ by [Matteo Hausner (bwRavencl)](https://bwRavencl.de){:target="_blank"}.
