---
title: Custom AIs
description: 
published: true
date: 2023-03-22T22:13:20.894Z
tags: 
editor: markdown
dateCreated: 2023-03-21T22:17:51.972Z
---

# Overview of custom AI
FAF features a number of advanced AI that offer significant improvements over the default AI.  In particular, depending on the AI these can include:
- Adaptive playstyle, responding to player actions
- Player tactics/unit microing
- FAF balance and meta focus
- Better CPU performance
- More challenging
- Unit mod compatibility

For example, by one measure the fastest custom AI was more than twice as fast as the default Adaptive AI (August 2022), while the Adaptive AI could lose to the most competitive custom AI even with a 100% boost to its resource generation and build speed (although as the base Adaptive AI is under active development this may change).

Further details on the custom AI available in FAF, and how to play using them, are given below.

# FAF Custom AI
Each AI has a different style of playing, so be sure to try and different AI to see the ones that you like the most.


## Actively developed AI

### AI-Uveso
![uvesoai.jpg](/uvesoai.jpg)
*Author: Uveso*
Other mods required: None
This AI is a turtle focused AI that is designed mainly for 10km maps.  It supports Nomads and other unit mods.

The AI-Uveso mod also allows for the generation of 'map markers', which are used by the default AI and certain other custom AI (as of writing, March 2023, AI-Swarm, Marlo's Sorian Edit, Sorian AI, and RNGAI, although RNGAI is expected to be updated to use separate map markers in the near future).  I.e. enabling AI-Uveso with these other AI mods can improve their performance. 

AI Variants: Easy, Rush, Adaptive, Experimentals, Overwhelm.  Uveso Rush is suggested as the more competitive of these variants.

### RNGAI
![rngai.jpg](/rngai.jpg)
*Author: Relent0r*
Other mods required: AI-Uveso
AI aimed at the players wanting to learn 1v1 gameplay. It provides an avenue to play against something that emulates some of the methods ladder players use!

AI Variants: RNG Standard, RNG Standard Experimental.  RNG Standard is suggested as the more competitive of these variants.

### M27AI
![m27ai.jpg](/m27ai.jpg)
*Author: maudlin27*
Other mods required: None
Adaptive AI, intended for both 1v1 and team games.  Provides a competitive player-like experience, with an estimated rank of 800-1100 (i.e. better than the average FAF player).

Further details on M27AI are available on the forum thread, including a detailed devlog of the AI's progress:
https://forum.faforever.com/topic/2373/ai-development-guide-and-m27ai-v70-devlog

### SCTA AI 
*Author: Dragun101*
Other mods required: SCTABalance, SCTAFix, and AI-Uveso
Note that this AI is part of the wider SCTA conversion mod, and requires both the SCTABalance and SCTAFix modes to work (which result in the two total annihilation based factions as playable options for humans and the SCTA AI).  The AI comes as part of these two mods.

## AI not under active development
### Marlo's Sorian Edit
Author: Degulum/!MarLo
Last updated: October 2022
Other mods required: AI-Uveso

### DilliDalli
![bugfix.png](/bugfix.png)
*Author: Softles*
Last updated: July 2021
Other mods required: None
Aggressive land focused AI, particularly effective at the T1-T2 stages of the game.

See also the forum thread for DilliDalli:
https://forum.faforever.com/topic/2008/dillidalli-1v1-specialist-ai

### Dalli
![bugfix.png](/bugfix.png)
*Author: Softles*
Last updated: May 2021
Other mods required: None
Functioning AI that was a predecessor to DilliDalli - considered inferior to DilliDalli.

### Nutcracker
![nutcracker.jpg](/nutcracker.jpg)
*Author: muchstuff*
Last updated: September 2021
Other mods required: AI-Uveso
Designed to battle against turtle human players on 20x20+ maps with lots of mass points.  Best in a 1v1 enfironment.

### SACUAI


### Dilli
![bugfix.png](/bugfix.png)
*Author: Softles*
Last updated: Jun 2018
Other mods required: None
Functioning AI that was a predecessor to Dalli and DilliDalli - considered inferior to DilliDalli.

## Upcoming AI
### M28AI
Author: maudlin27

This AI is only available from github as it is still in development and not yet suitable for release on the FAF vault.  While it is likely to be in a usable state on the majority of maps using default settings, there is a significant risk of errors.

It should be possible to play with this AI by downloading it from Github, and ensuring the M28AI folder is in your normal FAF mods folder (i.e. the same folder that other AI mods are saved to):
https://github.com/maudlin27/M28AI

Compared with M27AI M28AI aims to provide a more CPU performant AI that works better in teamgame scenarios, applying a decentralised approach to AI decisions to work more effectively on larger maps.


## Historic FAF AI
The following AI have previously been developed for FAF, but currently do not work, and are noted briefly for reference.

### AI-Swarm
![swarmicon.jpg](/swarmicon.jpg)
Author: Azraeel
Last updated: October 2022
Other mods required: AI-Uveso
Swarm stopped working following changes made to FAF in February 2023.  Although the author is currently unavailable, it is hoped that they may update Swarm at some point in the future to fix this issue.

This AI is a multi use AI that is designed mainly for 10km maps.  It provides an additional (optional) 'Eternal' game setting that provides the AI with a steadily increasing resource and build modifier to make it more challenging as the game progresses.
Note that this AI has compatibility issues with RNGAI
Variants: Terror, Eternal.

Further details on SwarmAI are provided in the forum thread, including suggested maps to play it on.
https://forum.faforever.com/topic/53/ai-swarm-ai-mod-for-faforever

# Playing with custom AIs
### Installing AI mods
Most custom AIs for FAF can be accessed from the mod vault in the client.  You can either search for the name of a specific AI, or search for mods containing the name "AI" (although note this will also bring up a number of irrelevant results).
As of writing, popular AI mods have also been included in the M&M Team top pics section of the mod vault.

![ai_-_finding_mod.png](/ai_-_finding_mod.png)

Once you have found the custom AI that you want to try, click on the blue download button to download the mod.![download_button.png](/download_button.png)

### Enabling AI mods
You should then be able to enable the mod from the mods section when hosting a game.  You can either do this when creating a game through the client (by looking for the AI mod in the SIM section):
![create_game_sim_mod.png](/create_game_sim_mod.png)

Or alternatively you can enable the mod from the game lobby itself by selecting "Options", and then "Mods":
![game_lobby_mods_menu.png](/game_lobby_mods_menu.png)

Browse to the relevant AI mod you want to use, and make sure it is selected (i.e. it should be highlighted in blue):
![game_lobby_mods_menu2.png](/game_lobby_mods_menu2.png)

### Selecting AI opponents
Once enabled, you can select the custom AI as one or more of the players in a game via the drop-down menu.  You can either select the 'normal' (non-cheating) AI version of the mod, or the "AIx" (cheating) version of the mod.
Typically the AIx version of an AI will receive a bonus to its resources and build speed (by default a 50% bonus but this can be adjusted via the game options), and by default receives map-wide omni vision (again this can be turned off via the game options).
Certain AI mods may provide multiple options/AI variants.

![game_lobby_select_an_ai.png](/game_lobby_select_an_ai.png)


Note that some AI mods may recommend or require other mods to be enabled, so please check the mod description for the particular AI you want to use for if there are any special requirements noted.

# AI game settings


# Feedback
You can provide feedback on particular AI in the FAF discord, through the ai-feedback channel.  To view this channel, go to the roles selection channel on the FAF discord (https://discord.com/channels/197033481883222026/831394581554790428) and indicating a preference for AI games in the "What Are Your Game Prefernces? Part 2 section.

Alternatively you can join the AI developers discord:
https://discord.gg/qdqcEGR7

Note that there is less likely to be a response regarding AI that are not under active development.

If reporting a bug with an AI, the following will be helpful for the AI developer to investigate it further:
* Include the replay ID number and time stamp of the issue, along with a description of the issue
* Specify whether you have any other mods active (and ideally if you get the same bug with just the AI mod in question active) - i.e. the more SIM mods that are active, the greater the chance of an error, which may be unrelated to the AI itself

# AI comparisons and tournaments

A number of AI tournaments have been held highlighting:

- How well AI perform against each other (competitively)
- How fast AI run
- What maps different AI work best on
- What unit mixes different AI favour

These are summarised in the following forum thread:
https://forum.faforever.com/topic/2931/monthly-ai-tourney-series
Note however that these AI tournaments would only show a snapshot at a particular time, and a number of the AI featured have received significant updates since then.