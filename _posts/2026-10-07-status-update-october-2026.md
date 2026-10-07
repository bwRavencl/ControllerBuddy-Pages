---
layout: post
title: October 2026 Status Update
date: 2026-10-07 02:00:00 +0200
---

<!-- markdownlint-disable-file line-length -->
### Falling Leaves and Fresh Features <!-- markdownlint-disable-line heading-increment -->

How time flies, we are already well into autumn, and it has been almost two months since my last post.
A whole stack of new developments has accumulated that I really should say a few words about here.

Apart from the usual housekeeping tasks around ControllerBuddy - which I do not cover in these posts - a number of features and improvements to the main application itself have been implemented for version 1.10.
Considerable effort has also gone into streamlining the usage of ControllerBuddy on Linux, making it easier than ever before - more on this below.

So let's dive right in...

### Selective Circle to Square Mapping

With the release of ControllerBuddy version 1.10, a new profile feature for axis actions has been introduced.
It comes in the form of a checkbox labeled *Use Raw Value*.
When this option is enabled, ControllerBuddy bypasses the so-called *Circle to Square Mapping* of the corresponding axis for that specific action.

![Lockable Settings Panel](/assets/images/2026-10-07-status-update-october-2026/use-raw-value.png)

If this doesn't make sense yet, let me try to explain:

First of all, let us clarify what *Circle to Square Mapping* means in the context of ControllerBuddy.
In short, it is a setting located under the *Global Settings* tab, and has been part of the application for a long time.
When this option is enabled (the default setting), ControllerBuddy maps physical axis values from a circle to a square.
This is useful for most game controllers, which feature circular analog sticks - essentially almost every controller on the market.
Why is this necessary?
Because with a circular stick, it would otherwise be impossible to reach full deflection along both the X and Y axes simultaneously.
For example, if this option is disabled on a controller with circular sticks, you cannot apply full elevator and full aileron at the same time.

While the *Circle to Square Mapping* feature solves this problem, it comes with a drawback: the stick becomes significantly more sensitive near the corners.
This is especially problematic for the left stick, which in official profiles is mapped to the yaw and throttle axes.
Imagine you have applied full left rudder, then even a slight, unintentional movement along the Y axis will cause a disproportionately strong deflection on the virtual throttle axis.

Traditionally, the official profiles relied on relatively large dead zones on both axes to prevent unintentional inputs.
While this helped to a degree, it was far from perfect.
In this particular scenario, it is much better to disable *Circle to Square Mapping* altogether.
And that is precisely what the new *Use Raw Value* option is designed for.
Official profiles now have this option enabled by default for throttle, prop-pitch, and mixture axis bindings.
If *Circle to Square Mapping* is disabled globally, this option has no effect.

### UI Improvements and JDK 27

The most visible change for users is likely the new lock screen overlay.
It features a stylish blur effect rendered over the UI controls whenever ControllerBuddy is actively running.
Previously, the UI elements used for editing profiles and global settings were simply disabled, which was often confusing for new users.
The lockable tab panels now display a prominent button labeled *Stop execution to unlock*, making it instantly clear why the UI is locked.
Clicking this button directly stops execution without requiring navigation through the main menu, allowing quick access to the controls below.

![Lockable Settings Panel](/assets/images/2026-10-07-status-update-october-2026/lockable-settings-panel.png)

Another small improvement affects the keystroke editor, which now automatically scrolls to ensure the first matching key is visible as soon as you type into the filter box.

Additionally, two minor edge cases involving the overlay have been resolved:

1. Fixed an issue with the On-Screen Keyboard where switching between light and dark themes left the keyboard styled in the colors of the previous theme.
2. Added small vertical spacing in the overlay between the mode label and horizontal indicators when no vertical indicators are configured, making the overlay look less cluttered.

Finally, [Java 27](https://openjdk.org/projects/jdk/27/){:target="_blank"} was released on September 15th.
As usual, ControllerBuddy was immediately updated to this new JDK release to take advantage of its latest performance improvements and enhancements.

### ControllerBuddy Wrapper Scripts for Linux

I have recently invested a lot of effort into making ControllerBuddy on Linux easier to use and better integrated.
On Windows, the installation script handles installing and updating the application, and also invoking the profile configuration scripts that automatically set up supported sims.

While the same installation script runs on Linux, it cannot trigger the configuration scripts the same way it does on Windows.
It is strictly meant for installing and updating ControllerBuddy and its profiles because, unlike Windows, on Linux each game usually runs inside its own isolated [Wine](https://www.winehq.org/){:target="_blank"} or [Proton](https://github.com/ValveSoftware/Proton){:target="_blank"} prefix.

Furthermore, I now consider the [ControllerBuddy Flatpak](https://github.com/bwRavencl/ControllerBuddy-Flatpak){:target="_blank"} to be the primary distribution channel for ControllerBuddy on Linux.
[Flatpak](https://flatpak.org/){:target="_blank"} provides a distribution-agnostic way to package, deploy, and run desktop applications safely.

Instead of configuring all games from a single global setup script like on Windows, it is much more effective on Linux to execute configuration scripts dynamically just before launching a game.
This approach offers an added benefit: any profile or configuration updates released with ControllerBuddy are automatically applied at game launch.
To achieve this, I created two wrapper scripts - one for Proton and one for [DOSBox Staging](https://www.dosbox-staging.org/){:target="_blank"} - which are bundled directly into the Flatpak package.

The `proton-wrapper.sh` script automates the following steps:

- Ensures the Protontricks Flatpak is installed
- Disables native joysticks in the game's Proton prefix
- Updates the ControllerBuddy Flatpak
- Launches ControllerBuddy with the specified profile
- Ensures PowerShell is installed in the game's Proton prefix
- Runs the profile's configuration script inside the game's Proton prefix
- Launches the game
- Shuts down ControllerBuddy when the game exits

The `dosbox-wrapper.sh` script automates the following steps:

- Updates the ControllerBuddy Flatpak
- Launches ControllerBuddy with the specified profile
- Forces DOSBox to use ControllerBuddy's virtual joystick
- Overrides mouse sensitivity in DOSBox if `mouse_sensitivity` is provided
- Launches DOSBox
- Shuts down ControllerBuddy when DOSBox exits

For [Steam](https://store.steampowered.com/){:target="_blank"}/Proton games, all the user needs to do is adjust the Steam *Launch Options* for a title as outlined in the [ControllerBuddy-Flatpak](https://github.com/bwRavencl/ControllerBuddy-Flatpak){:target="_blank"} repository.
This instructs Steam to run the wrapper script instead of executing the game directly.
From there, the script works its magic.
By inspecting its execution environment, the script determines which Wine prefix to configure, which configuration script to execute based on the specified profile name, and which [Protontricks](https://github.com/matoking/protontricks){:target="_blank"} verbs are needed.
The wrapper updates the Flatpak, launches ControllerBuddy with the correct profile, configures the prefix, runs the configuration script, and finally starts the game.
Once you exit the game, ControllerBuddy closes automatically.
This workflow works seamlessly for both native Steam and non-Steam games and integrates nicely with the [SteamOS](https://store.steampowered.com/steamos){:target="_blank"} interface on devices such as the [Steam Deck](https://www.steamdeck.com){:target="_blank"}.

To display progress indicators or potential error messages during startup, the scripts use [zenity](https://gitlab.gnome.org/GNOME/zenity){:target="_blank"}, which is included in the Flatpak package.

![Proton Wrapper Script](/assets/images/2026-10-07-status-update-october-2026/wrapper-script.gif)

I have updated the [ControllerBuddy-Linux-Guides](https://github.com/bwRavencl/ControllerBuddy-Linux-Guides){:target="_blank"} to reflect these changes.
Overall, I am proud to say this implementation makes ControllerBuddy even easier to use and more tightly integrated on Linux than on Windows.
While getting everything working required extensive testing - especially around the quirks of the [gamescope](https://github.com/ValveSoftware/gamescope){:target="_blank"} compositor - the effort has definitely paid off.

### A New Profile for DI's Hind

Since my last post in August, I added a new official profile for the classic 1996 DOS simulator [Hind](https://www.mobygames.com/game/620/hind/){:target="_blank"} by [Digital Integration](https://www.mobygames.com/company/751/digital-integration-ltd/){:target="_blank"}.
I played around with this sim back in the late '90s when I got it as part of [a game collection](https://www.mobygames.com/game/13186/aber-hallo/){:target="_blank"}, but I never got deep into it at the time.

After setting it up in DOSBox and designing a custom ControllerBuddy profile, I played through a few training missions and jumped into the campaigns.
While its flight model and avionics cannot compare to modern implementations like the [Mi-24 in DCS](https://www.digitalcombatsimulator.com/en/shop/modules/hind/){:target="_blank"}, this '90s classic offers still some very enjoyable gameplay even today.
Unfortunately, even early campaign missions feature overwhelming ground and air threats, making survival quite a challenge, which is why I haven't made it very far into the campaign yet.

### GitHub Workflow Improvements

All repositories across the ControllerBuddy project (main application, profiles, install script, Flatpak, website, etc.) rely heavily on [GitHub Actions](https://docs.github.com/en/actions){:target="_blank"} workflows for building, testing, and static analysis.
Automated workflows make it easy to trigger tasks automatically, such as updating the website's *Profiles* section whenever changes are pushed to the profile repository.

Over the past few weeks, I implemented several minor updates and refactorings across these workflows.
Two new automations for the ControllerBuddy Flatpak are particularly noteworthy.
To explain, I need to go back a bit first.

Flatpaks are built using manifest files; the manifest for ControllerBuddy is maintained in a dedicated repository called ControllerBuddy-Flatpak.
Many Flatpak applications are hosted centrally on [Flathub](https://flathub.org){:target="_blank"}, the largest repository in the world of Flatpak.
However, due to Flathub's strict rules regarding release cycles and ControllerBuddy's rolling-release model, I was unable to include it in the official Flathub repository.
Instead ControllerBuddy can be obtained from its own Flatpak repository.
While this requires users to manually add said repository to their system, it gives the project complete independence.
The custom Flatpak repository is hosted via [GitHub Pages](https://docs.github.com/en/pages){:target="_blank"}.
Whenever the manifest file in the Git repository is updated, a GitHub Actions workflow builds Flatpak packages for both x86-64 and aarch64 architectures and deploys them to GitHub Pages.

To ensure the manifest stays updated whenever a new version of ControllerBuddy is released, I integrated a workflow based on the [Flatpak External Data Checker](https://github.com/flathub-infra/flatpak-external-data-checker){:target="_blank"} tool, which is maintained by the Flathub community.
This tool relies on [release-monitoring.org](https://release-monitoring.org/){:target="_blank"}, a project run by the [Fedora Project](https://fedoraproject.org/){:target="_blank"} to track upstream software releases.
The service regularly polls registered projects to check for new versions and exposes that data through a public API.
By authenticating with an API key, we can also trigger on-demand checks for specific projects using API calls.
That is exactly what the release workflow for the primary ControllerBuddy application now does.
Immediately after a new binary release is published, release-monitoring.org is instructed to run a check and detect the new version.

Next, the release workflow triggers an update workflow in the ControllerBuddy-Flatpak repository, which automatically opens a pull request updating the Flatpak manifest.
Once that pull request is approved by me, a build and deployment workflow compiles the Flatpak and publishes the build.
The next time users check for updates on their system, they instantly receive the latest release.

You might wonder why we take this route through release-monitoring.org instead of updating the manifest directly or storing it inside the main repository.
The simple reason is that I prefer to follow Flathub's design patterns and adhere to their standards as closely as possible.

### Summing Up

If you made it all the way to the end, congratulations!
I hope you found these updates interesting and picked up a few helpful takeaways.  
At this point, I often share a roadmap or preview of upcoming plans, but right now, there are no immediate features planned.  
Thank you for your interest, have a great day, and see you around!
