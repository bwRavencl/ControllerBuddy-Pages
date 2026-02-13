---
layout: post
title: February 2026 Status Update
date: 2026-02-14 00:00:30 +0100
---

### A New Year, New Updates

How time flies... we are now well into February, and it has already been a busy start to the year. Since my last post in early December, I have been working on several updates and improvements to ControllerBuddy and its broader ecosystem, the details of which I would like to share here.

### Linux Guides Published

As announced in my [previous post](https://controllerbuddy.org/#news/looking-back-at-2025){:target="_blank"}, I have been writing detailed setup guides to assist users interested in running ControllerBuddy on Linux. These guides have now been published in the [ControllerBuddy-Linux-Guides](https://github.com/bwRavencl/ControllerBuddy-Linux-Guides){:target="_blank"} repository on GitHub.

The repository currently includes guides for:
- DCS World
- EF2000 V2.0
- Falcon 3.0
- Jane's Fighters Anthology
- IL-2 Sturmovik: 1946
- IL-2 Sturmovik: Great Battles
- Strike Fighters

A guide for Falcon BMS is currently in the works and will be added in the future.

### ControllerBuddy Development Updates

Next to the usual smaller bug fixes and optimizations, I have been working on a few larger features and improvements for ControllerBuddy itself, which I would like to highlight here:

#### Activation Intervals
I have redefined the meaning of the activation interval for single-immediate and single-on-release actions. Previously, this interval was ill-defined for these action types and offered little practical utility. With this change, the activation interval now directly controls the precise duration a joystick button, key, or mouse button is held down in all cases, enabling outputs to be performed over a defined, prolonged time interval.

#### Visualization Tab
Profile visualizations now feature a dedicated legend to clearly depict the meaning of the various symbols used in the depiction. Additionally, I have implemented panning support, allowing users to move the visualization when zoomed in. This should make it significantly easier to navigate and analyze complex profiles.

#### Packaging
I have implemented packaging optimizations that reduced the overall size of the `.zip` and `.tgz` archives by a few megabytes. Depending on the platform, this results in an archive size of approximately 30 to 34 MB, which is quite reasonable compared to some other modern applications.

#### Wayland Support
I have begun work on native [Wayland](https://wayland.freedesktop.org/) support for Linux, leveraging the [JetBrains Runtime](https://github.com/JetBrains/JetBrainsRuntime){:target="_blank"}. This is an ongoing effort, and you can track the current progress and technical milestones in a dedicated [GitHub issue](https://github.com/bwRavencl/ControllerBuddy/issues/485){:target="_blank"}. While ControllerBuddy currently works well on Wayland via XWayland, native support remains a long-term goal that depends on developments within the Wayland, JetBrains Runtime, and [Wakefield](https://openjdk.org/projects/wakefield){:target="_blank"} projects.

### New Profiles and Install Script Improvements

Two new profiles have been added to the [ControllerBuddy-Profiles](https://github.com/bwRavencl/ControllerBuddy-Profiles){:target="_blank"} repository:
1. [Nuclear Option](https://controllerbuddy.org/#profiles/Nuclear_Option.html){:target="_blank"}
2. [F-15 profile for Falcon BMS](https://controllerbuddy.org/#profiles/Falcon_BMS_F-15.html){:target="_blank"} (This was requested by multiple users, so I have finally taken the time to create it.)

In addition, as always, I have been making minor adjustments and improvements to existing profiles and the configuration scripts to ensure they remain up-to-date and continue to provide the best possible experience for users.

Last but not least, I have made various smaller improvements to the install script, including better error handling.

