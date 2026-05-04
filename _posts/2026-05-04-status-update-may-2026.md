---
layout: post
title: May 2026 Status Update
date: 2026-05-04 19:10:00 +0200
---

### Aloha!

It has been a few months since the February update, and while the weather is warming up, the development pace for ControllerBuddy hasn't cooled down.

The slight delay in getting this post out was for a very special reason: my recent trip to Hawaii, where my wife and I officially tied the knot! We had a truly wonderful time celebrating our marriage and enjoyed the break immensely after a busy start to the new year.

As always, work on ControllerBuddy has continued with a variety of updates and enhancements. Here are the details on what has changed since my last news post.

### Refining the Component Editor

A major focus since the last news post was a significant overhaul of the *Component Editor* dialog to make profile creation more intuitive. The goal was to add documentation for the different types of Actions and integrate it directly into the interface. To achieve this, a contextual help system for Actions and their properties was added, providing immediate guidance where it's needed most.

Furthermore, UTF-8 symbols for each Action type and property were added to make them more recognizable at a glance and to make the dialog less monotonous. Moreover, the layout of the entire dialog was improved for better flow and clarity. Finally, the descriptions of the assigned Actions are now displayed directly within the *Assigned Actions* list, which is especially helpful when multiple Actions of the same type are assigned simultaneously.

### Flexible Action Delays

A seemingly small but powerful new feature is the introduction of customizable action delays. Previously, Actions that had the *Delayed Action* property enabled featured a fixed delay of 1 second, meaning a button had to be held down for at least that long before the Action triggered. A new property called *Delay* was added, which is a freely configurable time interval. This offers far more precision for specific controller or simulator needs, allowing for much more flexibility in how inputs are processed.

### Leveraging Agents for Documentation and Tests

Like most people in software, I've started using AI coding agents recently to handle the kind of tedious work that usually falls by the wayside. This has allowed me to tackle codebase improvements that would have simply taken too much time to do manually.

To start, an [`AGENTS.md`](https://agents.md/){:target="_blank"} file was added to the repository. This file is specifically designed to help coding agents navigate the project structure and understand the coding standards more effectively.

Until recently, the codebase of ControllerBuddy contained no documentation at all. With the help of AI, [Javadoc](https://en.wikipedia.org/wiki/Javadoc){:target="_blank"} comments were added to the entire codebase. While these were mostly generated using the aforementioned agents, they provide essential context for every class and method, making the project easier to navigate and maintain in the future.

In the same vein, the codebase lacked any tests. Over a few days, leveraging AI, nearly 600 tests were created, including unit tests and tests of the complete input pipeline. These tests have already uncovered a few minor bugs that were promptly fixed, and they are primarily meant to prevent potential regressions in the future.

The above changes significantly improve the overall maturity of the codebase, and would never have been implemented if I had to write them all by hand due to the massive time investment required. While the usage of agents made these additions feasible in the first place, a significant amount of time still had to go into reviewing and tweaking the vast amount of code that was generated. At this point in time, the testing code alone comprises nearly 10,000 lines!

### Java, Profile, and Install Script Updates

Continuing the tradition of staying up-to-date with the Java ecosystem, a switch from JDK 25 to the newly released [JDK 26](https://openjdk.org/projects/jdk/26/){:target="_blank"} was made to utilize the latest performance improvements and JVM features.

A small update of the Install Script was necessary to support [Git for Windows](https://gitforwindows.org/){:target="_blank"} version 2.54.0. If you've been having trouble with a fresh install, this update should clear things right up.

On the profile side, a new profile was added for the Steam re-release of the classic [F-22: Air Dominance Fighter](https://store.steampowered.com/app/3146140/F22_Air_Dominance_Fighter){:target="_blank"}.  
To celebrate its release, I created [a quick video](https://www.youtube.com/watch?v=6AKwhZJNnHA){:target="_blank"} to showcase how well the F-22 ADF works with the ControllerBuddy on the Steam Deck.

As always, various small improvements to several existing profiles were also implemented.