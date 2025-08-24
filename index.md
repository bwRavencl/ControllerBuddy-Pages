---
title: ControllerBuddy

accordion: 
  - title: What is the purpose of this FAQ?
    content: |
        Firstly, it will show you how to intuitively control all aspects of modern flight simulators using only a gamepad. This means that a joystick, keyboard or even a mouse are no longer strictly necessary to control your virtual aircraft and the simulator's user interface.  
        This method is applicable to all flight simulators and all types of aircraft and helicopters.

        Secondly, it is intended as a guide to **ControllerBuddy**, an advanced open-source game controller mapping software developed by the author of this document.
  - title: What is ControllerBuddy?
    content: |
        ControllerBuddy is a powerful and flexible gamepad mapping tool designed for creating custom input profiles for demanding applications like flight simulators.

        It goes far beyond the basic button and axis remapping offered by many other gamepad mapping tools. In addition to translating gamepad input into keyboard and mouse actions, ControllerBuddy can also send input to a virtual joystick device.

        The core goal of ControllerBuddy is to let you control any flight simulator entirely with a gamepad, so you never have to reach for a keyboard or mouse during gameplay.
  - title: What problems does ControllerBuddy solve?
    content: |
      - It enables you to use a gamepad to control flight simulators, even if the simulator doesn't natively support gamepads.
      - For simulators that only offer limited or no customization of gamepad inputs, ControllerBuddy lets you create fully customized input profiles, giving you complete control over how your gamepad behaves.
  - title: How do you define 'gamepad'?
    content: |
        A game controller as used by current generation gaming consoles, with two analog sticks, a D-Pad, a number of face buttons, two triggers and two shoulder buttons.

        Popular examples for this type of input device are:
        - DualShock 4 Controller
        - DualSense Controller
        - Xbox 360 Controller
        - Xbox One Controller
        - Xbox Series X\|S Controller
  - title: Why choose a gamepad for flight simulation?
    content: |
        While a joystick or yoke in combination with a throttle is probably the most obvious choice for controlling a virtual aircraft, the usage of a gamepad offers a number of advantages, which for some people can make it an interesting alternative:
        - Gamepads, especially the ones name above, offer a high build quality and are very sturdy, which sadly is a virtue only few of the joysticks on the market can offer, that from my experience can break often and are sometimes hard to repair.
        - Many people who own a gaming PC already own a gamepad to begin with. These days joysticks have become more of a rarity compared to the heyday of flight simulators during the 1990s. This is something especially newcomers to the flight simulation genre may be facing or if you are a veteran virtual-pilot and are trying to get a friend interested in this great hobby, who does not (yet) own the necessary peripherials.
        - When comparing the cost of a high-quality gamepad to that of a HOTAS or yoke system, the gamepad is clearly the more affordable option, making it especially appealing to newcomers taking their first steps into flight simulation.
        - While a joystick with a throttle can be considered the bare minimum to start out with, many more senior virtual pilots will say that you will also need a rudder pedals and a headtracking unit to take your experience to a satisfactory level. Depending on your desk you may also need a suitable mounting solution to install your input decvices at a proper height. All these things are not only an additional cost factor, but can also quickly come in someone's way if your PC is not dedicated to your flying hobby.
        - Even if you call all of the above named devices your own, you most likely will still depend on a keyboard and mouse to be able to navigate the menus of your simulator und to handle switches and buttons inside the virtual cockpit, this means having to take your hands off frin the throttle and stick, which can be cumbersome.
        - Even handheld devices like the Steam Deck, can become a viable platform to enjoy flight simulators when used in conjunction with ControllerBuddy as demonstrated in [this video](https://www.youtube.com/watch?v=HLd0bi02wmE){:target="_blank"}.
        - A wireless gamepad used in the way as described in this guide, offers you exceptional freedom in the sense that you are no longer tightly bound to a seating position from which all of the necessary input devices are reachable. If your screen is large enough, flying from a comfortable spot on your couch may come to one's mind.
        - While a gamepad does certainly not come as close to the controls found in a real plane, it still can emulate the controls more or less acurately. If upmost realism is your top priority, you will probably prefer to use a classic stick, but be aware that one set of input devices can usually only realistically represent one particular model of aircraft from the real world. If you like to fly general aviation aircraft, airliners, military jets and helicopters, you actually would need vastly different sets of input devices for at least each one of these categories.
        - Physical strain is another issue I would like to mention: From my experience flying with a gamepad for a long time now has been very comfortable and a lot less straining than with a joystick and throttle, I find this especially true for helicopter flying, where constant very precise inputs are necessary.
  - title: What are the limitations of using a gamepad?
    content: |
        - An inherent disadvantage of using gamepads for flight simulators is that they do not have *relative* axes. A relative axis is an axis that is not spring-loaded, like a slider, and is the preferred means of controlling the throttle, propeller pitch, and mixture of an aircraft.
        - Since the two sticks of a gamepad are a lot smaller than a dedicated joystick, they offer a smaller range and thus require more precise inputs.
        - Due to the stated goal of controlling a complete aircraft with a gamepad that offers a large but still limited number of buttons and axes, we cannot avoid using modifiers to make some of them perform more than one function.
        - Lastly as already mentioned above, a gamepad will certainly never be able to offer the same realism than a well-made joystick or yoke.
  - title: How to overcome the limitations of a gamepad?
    content: |
        Instead of binding axes and buttons directly to our gamepad we use a *virtual* joystick.  
        On Windows, this virtual joystick is provided by the excellent **vJoy**. Created by Shaul Eizikovich as open-source software, vJoy is a device driver that provides virtual joysticks that can be controlled from other applications (in our case ControllerBuddy).  
        Under Linux, ControllerBuddy dynamically creates its own virtual joystick device using the uinput kernel module.

        In **ControllerBuddy** we can create **profiles** that define a mapping of the physical axes and buttons of our gamepad to so called **actions**. Among other things, actions can manipulate the axes of the virtual joystick device or simulate mouse and keyboard inputs. This allows us for example to work around the above mentioned issue of missing relative axes on our gamepad.  
        Due to the limited number of axes and buttons of a gamepad, a single axis or button usually must serve multiple purposes. This can be handled by so called **modes**. For example an axis normally assigned to the throttle can become the axis controlling for controlling the view (i.e. looking up and down), while swiching to view-mode.

        Another function of ControllerBuddy is the so called **overlay**. The overlay is a transparent window that is displayed on top of the simulator to show the currently active mode and the state of the axes of the virtual axes. This is especially useful for relative axes, for example it is very hard to tell the current throttle setting without such an indication. The overlay can be freely moved around the screen and configured to include only indicators for certain axes of interest.

        ControllerBuddy also provides a special mode in which an **on-screen-keyboard** is displayed that can be controlled via specialized actions. This is helpful when you want to type in chat messages without having to rely on a physical keyboard.  
        Since the required inputs vary greatly from simulator to simulator and even from aircraft to aircraft, a custom tailored profile for each simulator, and in case of complex titles such as DCS for each aircraft, is necessary. These profiles can be edited within ControllerBuddy and be permanently stored as files on your computer.

        [![Overlay](https://raw.githubusercontent.com/bwRavencl/ControllerBuddy/master/screenshot_7.png)](https://raw.githubusercontent.com/bwRavencl/ControllerBuddy/master/screenshot_7.png)
  - title: How do modes (shift-states) work?
    content: |
        **Switching between modes** is done via a specialized type of action for mode-switching that can be assigned to a button of your gamepad. A mode-swichting action can be configured to either temporarily switch to a mode, for as long as the corresponding button is depressed or to permanently toggle a mode on and off by a single press of the button. Depending on the concrete usage scenario one or the other configuration may be preferable.

        All axes and buttons that do not have a different actions assigned by the currently active mode retain the actions of the mode one level below.
  - title: What should a basic profile include?
    content: |
        Typically, you will want to create a unique profile for each simulator, and in many cases, for each aircraft simulated. However, most profiles will have a common base, which may look like this:

        **Primary controls:**  
        The control scheme presented here originates from the world of RC planes:
        - The right stick functions like a traditional joystick, controlling pitch and roll.
        - The left stick's vertical axis is mapped to a relative virtual joystick axis for throttle control, while its horizontal axis manages yaw.
        Given the limited range of a gamepad's physical axes, it's advisable to configure at least a small dead zone and some expo (curves) in-game for the virtual joystick axes controlling pitch, yaw, and roll.

        Note:  
        We will keep the right stick dedicated to pitch and roll control because these inputs are crucial in all situations. In contrast, the left stick will be repurposed for other functions in other modes, since throttle and yaw control are not always necessary.

        **Secondary controls:**  
        Controls such as flaps, landing gear and air brake can be mapped to the D-Pad.  
        Note that the gear is mapped to the down button of the D-Pad because it is physically located on the bottom of the aircraft, while the air brake is usually located on-top of the fuselage or wings and is therefore mapped to the up button. Following this logic, it only makes sense to use the horizontal section of the D-Pad for the flaps. Mapping the controls in such a way makes profiles much more intuitive and natural to use.

        ##### Default Mode:
        ![Basic Profile Default Mode](assets/svg/basic_profile_default_mode.svg)

        **Looking around**:  
        Pressing and holding the right shoulder button activates *Look Mode*:
        - In this mode the left stick controls the view and is used to look around. You will normally want to use two relative virtual joystick axes for mapping these controls.
        - The D-Pad shifts the head up and down and left and right.
        - The Y and A buttons shift the head forward and backward.
        - Pressing the right stick down zooms the view in, pressing the left stick down zooms out.

        ##### Look Mode (*hold RB*):
        ![Basic Profile Look Mode](assets/svg/basic_profile_look_mode.svg)

        **Centering and changing views:**  
        The X button does two things:
        1. As soon as the X button gets pressed the view is centered and the zoom level gets reset.  
        In order to achieve this, usually multiple actions must be performed:
            - The relative virtual joystick axes that are mapped to looking around must be centered - this can be done via configuring two specialized actions called *Reset Joystick Axis* that target the respective virtual joystick axes.
            - The in-game command(s) to center the view in all view axes must be fired.
            - The in-game command to reset the zoom level must be fired.
        2. Holding down the X button will also activate *View Mode*:  
        In this mode, the D-Pad is used to switch between the main views, such as the cockpit view, external views or map view.

        ##### View Mode (*hold X*):
        ![Basic Profile View Mode](assets/svg/basic_profile_view_mode.svg)

        **Trimming the aircraft:**  
        Pressing and holding the left shoulder button activates *Trim Mode*.
        - While in this mode, the D-Pad is used to change the pitch and roll trim, while the X and B buttons are used to change yaw trim.
        - Some aircraft may have a *Center Trim* command that can be assigned to the A Button.
        - For most helicopters, no dedicated Mode is necessary. Instead, the left shoulder button should simply be mapped to a *Force Trim* command, if available.

        ##### Trim Mode (*hold LB*):
        ![Basic Profile Trim Mode](assets/svg/basic_profile_trim_mode.svg)

        **Controlling the mouse:**  
        *Mouse Mode* allows you to control basic mouse functions with your gamepad. It is activated by pressing down the left stick momentarily.  
        Pressing down on it once more will deactivate it and drop you back to *Default Mode*.  
        When *Mouse Mode* is active you can perform mouse inputs as follows:
        - The left stick controls the mouse cursor
        - The right trigger performs a left-click
        - The left trigger performs a right-click
        - The Back button performs a middle-click
        - Pressing D-Pad up or down scrolls up or down

        ##### Mouse Mode (*toggled by pressing left stick*):
        ![Basic Profile Mouse Mode](assets/svg/basic_profile_mouse_mode.svg)

        **Generic keyboard inputs:**  
        Pressing down the right stick toggles *On-Screen Keyboard Mode* on and off. As the name implies, this mode brings up a special On-Screen Keyboard, which can be controlled via as follows:
        - The D-Pad moves the On-Screen Keyboard key selector around.
        - The A button depresses the currently selected On-Screen Keyboard key - when the A button is released, the corresponding key on the keyboard is also released.
        - The B button locks the currently selected On-Screen Keyboard key down - the key remains in depressed state until it is unlocked by selecting it with the selector and pressing the B button again.
        - The Y button is shortcut to release all locked keys at once.  
        By locking multiple keys, it is possible to perform key-strokes consisting of multiple keys pressed simultaneously.  
        When the *On-Screen Keyboard Mode* is exited by pressing down the right stick, all locked keys are automatically released.

        ##### On-Screen Keyboard Mode (*toggled by pressing right stick*):
        ![Basic Profile On-Screen Keyboard Mode](assets/svg/basic_profile_on_screen_keyboard_mode.svg)

        **Wrap-up:**  
        This forms the foundation upon which a complete profile can be built. It is recommended to keep certain core principles consistent across all your profiles, as this will make switching between different aircraft models and simulators much easier.  
        At this stage, we have covered all the essential controls for flying a virtual aircraft and managing the simulator's key functions. Most importantly, we still have several unused buttons available for avionics, weapons, and other features.
  - title: What about more complex profiles?
    content: |
        The more complex the simulated aircraft is, the more time it will take to create a profile and to figure out what is most intuitive. However nothing is impossible and in the author's experience even the most complex systems can be mapped to the limited number of buttons a gamepad offers.
        
        Here are just a few general guidelines on how to approach this task:
        1. Start by mapping everything you can find on the stick of the real aircraft. For aircraft that follow the [HOTAS](https://en.wikipedia.org/wiki/HOTAS){:target="_blank"} concept, this will already include almost everything needed to operate the aircraft and its systems.
        2. Now you can focus on additional bindings for convenience, such as:
        - Propeller and Mixture levers
        - Sensor controls (e.g. Radar and [FLIR](https://en.wikipedia.org/wiki/Forward-looking_infrared){:target="_blank"})
        - Countermeasure controls (Chaff, Flare and [ECM](https://en.wikipedia.org/wiki/Electronic_countermeasure){:target="_blank"}) 
  - title: Which steps are needed to create a profile?
    content: |
        A profile always targets a specific game. The game must be configured so that the inputs that ControllerBuddy simulates are bound to actual actions in the game.  
        For example, if a ControllerBuddy profile contains an action that should perform a *G*-Key press to raise and lower the landing gear, the *G*-Key must be mapped to the landing gear function in the game.

        Most games come with certain default mappings, it is recommended to stick to these mappings and create ControllerBuddy profiles that target the default mappings. If a function does not have a default mapping, it should be mapped to a button of the virtual joystick device, both in ControllerBuddy and in the game. The same goes for all axis functions.

        The steps below will guide you in assigning game functions to your controller:

        **Mapping an axis function:**

        | Location           | Action                                                                                          |
        |--------------------|-------------------------------------------------------------------------------------------------|
        | In the game        | Map the desired axis function to an unused axis on the virtual joystick device.                 |
        | In ControllerBuddy | Create a corresponding mapping from a gamepad axis or button to the same virtual joystick axis. |

        **Mapping a function with a default shortcut:**

        | Location           | Action                                                                                               |
        |--------------------|------------------------------------------------------------------------------------------------------|
        | In the game        | Identify the default keyboard shortcut for the desired function.                                     |
        | In ControllerBuddy | Create a corresponding mapping from a gamepad axis or button to trigger that same keyboard shortcut. |

        **Mapping a function without a default shortcut:**

        | Location           | Action                                                                                                     |
        |--------------------|------------------------------------------------------------------------------------------------------------|
        | In the game        | Map the desired function to an unused button on the virtual joystick device.                               |
        | In ControllerBuddy | Create a corresponding mapping from a gamepad axis or button to trigger that same virtual joystick button. |

        **Important:** It is recommended that you export or backup your game configuration and keep it with your ControllerBuddy profile.

        What follows are some general guidelines on how to proceed when creating a new profile from scratch:
        1. In the game remove all existing mappings (axes and buttons) for your gamepad.  
        This is to ensure that the game only acts upon the inputs that are sent by ControllerBuddy. If you do not do this, you may end up with conflicting mappings, which will lead to unexpected behavior.
        2. Start by mapping the main control axes (elevator, ailerons, rudder, throttle) as part of the *Default Mode*
        3. Add a *Look Mode* and a *View Mode* as described above
        4. Add mappings for basic functions such as: landing gear, flaps, brakes. Normally these mappings should be part of the *Default Mode*. However, exceptions can be made: in modern aircraft such as the F/A-18 Hornet, the flaps are only used during take-off and landing and in addition other functions such as the tailhook fall into the same category. Since we only have a limited number of gamepad buttons available it makes sense to put all of these functions only used during take-off and landing into a dedicated mode.
        5. Add dedicated modes for special functions, e.g. sensor controls.  
        When assigning a gamepad button to a mode action, you have two options:
         - Toggle checked: this means that a single press of the button toggles the mode on, pressing it again toggles it off
         - Toggle unchecked: this means that the mode is only active for as long as you keep the button pressed down
        In general, toggling is more useful for modes that should stay active for a longer period of time, e.g. for a mode dedicated to operating sensor controls.
        6. In rare cases it may be useful to have certain axes or buttons double-bound within a mode, even for unrelated functions. For example, in my profiles I often double-bind the gamepad triggers for left and right braking, as well as for dropping weapons and firing the gun.  
        This is possible because when you are on the ground (when it makes sense to use the brakes), the weapon systems are turned off, so pulling the trigger has no effect at that point. Conversely, if you are in combat and the weapon safety is off, pulling the trigger will also activate the corresponding brake, but since you are in the air and the landing gear is retracted, braking will have no effect.
        7. Experiment! After a while you can quickly come up with input profiles, but it is only when you actually use a profile that its weaknesses become apparent. In this case, ControllerBuddy's interface makes it easy for you to make some quick changes, try them out, and only keep them if you like how they feel in action.
  - title: What are the hardware and software requirements?
    content: |
        **Hardware:**
        - Xbox Controller
        - DualShock 4
        - DualSense
        - Any other controller supported by [SDL_GameControllerDB](https://github.com/mdqinc/SDL_GameControllerDB)

        **Operating System:**
        - Windows 10 or 11 (x64)
        - Linux (x64 or aarch64)
  - title: Are there preconfigured profiles available?
    content: |
        ControllerBuddy's author is maintaining an exhaustive list of profiles for almost all current flight simulators. All of these profiles, along with matching game configurations can be found in a special GitHub repository called [ControllerBuddy-Profiles](https://github.com/bwRavencl/ControllerBuddy-Profiles){:target="_blank"}.

        To download the a ZIP-package containing the latest versions of all profiles and configurations [click here](https://github.com/bwRavencl/ControllerBuddy-Profiles/archive/refs/heads/master.zip){:target="_blank"}.

        If you have installed ControllerBuddy via the [ControllerBuddy-Install-Script](https://github.com/bwRavencl/ControllerBuddy-Install-Script){:target="_blank"}, you do not need to download the profiles separately, because the script has already placed a copy into your *Documents* folder.

        **Note:** When the script is launched via the *Update ControllerBuddy* shortcut, it will not only update ControllerBuddy, but attempt to update the profiles to the latest available version, that's why it is recommended to save your personal profiles or modified profiles to a different folder.

        Please follow the instructions listed in the repository's [README.md](https://github.com/bwRavencl/ControllerBuddy-Profiles#instructions){:target="_blank"} to get you started.  
        Additionally, it is recommended to check out the visualization for each profile, either in ControllerBuddy's visualization tab after loading the profile, or [below](#profiles) on this website.
  - title: Why can't I see the ControllerBuddy overlay?
    content: |
        Please try the following solutions:
        - Ensure the overlay is enabled in the profile settings tab.
        - When running on Windows, make sure the  [Windows Fullscreen Optimizations](https://devblogs.microsoft.com/directx/demystifying-full-screen-optimizations/) are enabled.
        - When running a Vulkan- or OpenGL-based application on a Windows system with an NVIDIA GPU, in the 'NVIDIA Control Panel', try forcing the setting called 'Vulkan/OpenGL present method' to 'Prefer layered on DXGI swapchain', as shown [here](https://www.reddit.com/r/nvidia/comments/yf6hiw/psa_you_can_now_elevate_openglvulkan_games_to_a/).
        - When running on a Linux system with X11, make sure you have the display compositor enabled, [this article](https://linux-gaming.kwindu.eu/index.php?title=Compositor_(X11)) explains how to configure the Compositor for the most common desktop environments - just remember for ControllerBuddy you will want the compositor enabled not disabled!
  - title: How can I ensure the vJoy device is used as the primary input?
    content: |
        - On Windows, make sure the vJoy device is the preferred input device - proceed as follows:
          1. Start -> Run -> enter `joy.cpl` -> OK
          2. Advanced -> Preferred device -> select 'vJoy Device'
        - On Linux in combination with Wine, you can entirely disable physical input devices with the following steps:
          1. From a terminal session run `wine control`
          2. Select each physical input device listed below 'Connected' and click 'Disable' - make sure you do not disable the device called 'ControllerBuddy Joystick'.  
             There should be no devices listed below 'Connected (xinput device)'.
  - title: Why is the mouse cursor so sensitive on Linux with KDE?
    content: |
        By default, KDE has pointer acceleration enabled, which can cause the mouse cursor to feel overly sensitive.  
        To disable pointer acceleration, follow these steps:
        1. Start ControllerBuddy and make sure, the
        2. Open the KDE 'System Settings' application.
        3. In the left sidebar, select 'Mouse & Touchpad'.
        4. In the 'Mouse' section, choose 'ControllerBuddy Mouse' from the 'Device' dropdown menu.
        5. Set 'Pointer acceleration' to 'None'.
        6. Click 'Apply' to save the changes.
  - title: Can I swap the left and right stick functions?
    content: |
        Yes! Go to the global settings tab and enable the 'Swap Left and Right Sticks' option.
  - title: What is haptic feedback?
    content: |
        Haptic feedback is a special feature that can be enabled for relative axis mappings. It causes the controller to vibrate slightly when either end of a relative axis, or a user defined axis position (dentent), is reached.

        Haptic feedback support is implemented for the most popular controllers on both Windows and Linux.
  - title: What's the best controller for ControllerBuddy?
    content: |
        The author recommends either a Microsoft Xbox Series X\|S Controller or a Sony DualSense or DualShock 4 controller.
        
        Both Sony controllers feature a touchpad, which is supported by ControllerBuddy to function like the typical touchpad of a laptop computer.
  - title: Can ControllerBuddy launch automatically with a sim?
    content: |
        ControllerBuddy supports multiple command line parameters which are listed [here](https://github.com/bwRavencl/ControllerBuddy/blob/master/README.md#command-line-parameters){:target="_blank"}.

        ControllerBuddy is a single-instance application, this means that if an instance of ControllerBuddy is already running, and the user launches a second instance, any supplied command line parameters are passed on to the first instance and the second instance terminates immediately.  
        This behavior can be useful in automation scripts to integrate ControllerBuddy tightly with other applications. For more information check out [ControllerBuddy-DCS-Integration](https://github.com/bwRavencl/ControllerBuddy-DCS-Integration){:target="_blank"}, an exemplary integration of ControllerBuddy into [DCS World](https://www.digitalcombatsimulator.com){:target="_blank"}.
  - title: Is there a way to automatically install and update ControllerBuddy?
    content: |
        The easiest way to setup ControllerBuddy is via the [ControllerBuddy-Install-Script](https://github.com/bwRavencl/ControllerBuddy-Install-Script){:target="_blank"}.

        The script streamlines the installation and updating of ControllerBuddy itself and of the profiles available as part of the [ControllerBuddy-Profiles](https://github.com/bwRavencl/ControllerBuddy-Profiles) repository.

        **Note:** on Windows it is mandatory that you install [Git for Windows](https://git-scm.com/download/win){:target="_blank"} first, in order to run the script.

        Alternatively, Linux users have the option of installing [ControllerBuddy as a Flatpak package](https://github.com/bwRavencl/ControllerBuddy-Flatpak).
  - title: How can I report bugs?
    content: |
        If you encounter any bugs, please use the [GitHub issue system](https://github.com/bwRavencl/ControllerBuddy/issues){:target="_blank"} to report them to the author.  
        Always include information about your system, including the operating system version and controller hardware you are using.  
        Also, please take the time to provide exact steps on how to reproduce the problem you encountered.
  - title: How can I contribute?
    content: |
        The easiest way everybody can contribute to ControllerBuddy is simply by spreading the word:  
        Online, people new to flight simulation are regularly asking how they can enjoy this hobby without a joystick, so the next time you see one of these posts, help them out and let them know about ControllerBuddy!

        If you are a developer and would like to contribute to ControllerBuddy by implementing a feature or fixing a bug feel free to do so and open a pull-request on GitHub.  
        ControllerBuddy is free and open-source software, licensed under the [GNU General Public License v3.0](https://github.com/bwRavencl/ControllerBuddy/blob/master/LICENSE){:target="_blank"}, this allows everyone to participate in its development.  
        Please note that the author will only accept features that he personally finds useful and that meet his standards for code quality.
  - title: Do you take donations?
    content: |
        First of all, thank you so much for even considering a donation!

        I created ControllerBuddy primarily for myself - not to make any money.  
        That said, receiving a donation is one of the most meaningful ways to show appreciation for the thousands of hours I've put into the project. It genuinely motivates me to keep going.

        If you'd like to support ControllerBuddy, you can send a donation via PayPal by clicking [here](/donate){:target="_blank"}.

        Please only donate if it’s easy for you. Otherwise, just sending me a quick message to say you enjoy using ControllerBuddy means just as much to me!
  - title: How can I get in touch with you?
    content: |
        Please refer to the [ControllerBuddy Discord](https://discord.gg/2Sg9ggZrAp){:target="_blank"} if you have any additional questions that were not covered here.
---

## Welcome

<div class="centering-container slide-in-right">
  <div class="post-it">
      <div class="pin">
      <div class="shadow"></div>
      <div class="metal"></div>
      <div class="bottom-circle"></div>
    </div>
    <div class="welcome-headline">
      Your&nbsp;gamepad, your&nbsp;cockpit&nbsp;-
      <br>
      no&nbsp;compromises!
    </div>
    <div class="welcome-text">
      Ditch the expensive gear and fly with ease.
    </div>
    <div class="welcome-text">
      Enjoy any flight&nbsp;simulator
      <br>
      with a game&nbsp;controller.
    </div>
    <div class="welcome-text">
      Take off now with <strong>ControllerBuddy</strong>!
    </div>
  </div>
</div>

## Screenshots

<div class="centering-container">
<section class="splide">
  <div class="splide__track">
    <ul class="splide__list">
      <li class="splide__slide">
        <img src="https://raw.githubusercontent.com/bwRavencl/ControllerBuddy/master/screenshot_6.png">
      </li>
      <li class="splide__slide">
        <img src="https://raw.githubusercontent.com/bwRavencl/ControllerBuddy/master/screenshot_7.png">
      </li>
      <li class="splide__slide">
        <img src="https://raw.githubusercontent.com/bwRavencl/ControllerBuddy/master/screenshot_1.png">
      </li>
      <li class="splide__slide">
        <img src="https://raw.githubusercontent.com/bwRavencl/ControllerBuddy/master/screenshot_2.png">
      </li>
      <li class="splide__slide">
        <img src="https://raw.githubusercontent.com/bwRavencl/ControllerBuddy/master/screenshot_3.png">
      </li>
      <li class="splide__slide">
        <img src="https://raw.githubusercontent.com/bwRavencl/ControllerBuddy/master/screenshot_4.png">
      </li>
      <li class="splide__slide">
        <img src="https://raw.githubusercontent.com/bwRavencl/ControllerBuddy/master/screenshot_5.png">
      </li>
    </ul>
  </div>
</section>
</div>

## Getting Started

<iframe class="bordered" width="100%" height="315" src="https://www.youtube.com/embed/AYBr_zzQCqA" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

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
