---
title: Co-op troubleshooting compendium
description: Page giving some additional information on how to get co-op working
published: true
date: 2025-07-22T21:02:20.844Z
tags: campaign co-op
editor: markdown
dateCreated: 2025-07-22T21:02:20.844Z
---



## Playing unofficial releases
## Saving/loading missions
In order to save and load your game state, as you could with the original games, you'll have to launch the FAF game binary with some extra parameters. How to do this is explained in the next section: **Playing offline**

## Playing offline
If you prefer playing the scenarios and campaign missions offline, or you don't like launching via the client, you have an option to do that. It will require a bit of setup.

First, you will need to have the scenario files of every mission you want to play this way. You have two ways of getting these files. You can either:
1. Launch each mission in the client once. Hosting a lobby requires the scenario files to be downloaded, so you don't need to start the game once the appropriate mission files are downloaded and you are in the lobby. You do need to repeat this process for every mission you want to have access to.
2. You can manually inject scenario files into your folders. You can do this using the same steps described in **Playing unofficial releases**.

## Game stutter/freeze

A somewhat recent issue that popped up is the game freezing/hanging/stuttering before every voice line. At the time, the exact reason is not know, but current understanding is that Microsoft introduced some firmware update in 2024 that made this issue appear. It freezes every time the game tries to load a voice-over (game is old, assumption is Microsoft deprecated these old file types or something). However, there's an easy fix: you need to disable the "CPU 0" usage by the Windows, and some report increasing process priority also helps with removing the freeze. The steps are:

**1) Locate process:** Open the Task Manager and find your game instance in the process list. Then right click on it, and click "Go to details".
![faf_coop_freeze_1.png](/images/bug_fixing/faf_coop_freeze_1.png =50%x50%)


**2) Set priority:** Right click on the game instance > Set priority  > set it to "High". You'll get a confirmation window asking you if you really want to do it - confirm the change.
![faf_coop_freeze_2.png](/images/bug_fixing/faf_coop_freeze_2.png =50%x50%)
**3) Set affinity:** Right click on the game instance again, but this time click "Set affinity". A new window will open up, that has a list of "processors". Example below has CPU 0 - CPU 4. Your might have less or more, but the problematic one is the CPU 0. Make sure to untick it, and then press "OK". You might get another confirmation window - if so, confirm the changes.
![faf_coop_freeze_3.png](/images/bug_fixing/faf_coop_freeze_3.png =50%x50%)

That's it. Unfortunately, this process needs to be repeated every time you open the program anew. However, you can opt to use 3rd party software to automate this process for you, like Process Lasso or Process Hacker. These types of programs mess with how your PC runs, so make sure to be careful while using them!