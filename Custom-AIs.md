---
title: Custom AIs
description: 
published: true
date: 2023-03-23T07:55:19.325Z
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
- Greater challenge
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
![sctarebalance_icon.png](/sctarebalance_icon.png)
*Author: Dragun101*
Other mods required: SCTABalance, SCTAFix, and AI-Uveso
Note that this AI is part of the wider SCTA conversion mod, and requires both the SCTABalance and SCTAFix modes to work (which result in the two total annihilation based factions as playable options for humans and the SCTA AI).  The AI comes as part of these two mods.

## AI not under active development
### Marlo's Sorian Edit
![sorianedit.bmp](/sorianedit.bmp)
Author: Degulum/!MarLo
Last updated: October 2022
Other mods required: AI-Uveso
Based off the Sorian AI, this mod looks to make improvements to the logic to provide a more competitive experience.

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
![sacuai_icon.jpg](/sacuai_icon.jpg)
*Author: Skouby*
Last updated: June 2021
SACUAI was entered in the 2021 computer cup, placing 4th out of the 8 AI entered:
https://forum.faforever.com/topic/1475/supreme-computer-cup/57

### Dilli
![bugfix.png](/bugfix.png)
*Author: Softles*
Last updated: Jun 2018
Other mods required: None
Functioning AI that was a predecessor to Dalli and DilliDalli - considered inferior to DilliDalli.

### Sorian AI
*Author: Sorian*
Last updated: Unknown
Other mods required: None
When released Sorian AI represented an improvement to the base AI in FAF.  Note though that the base adaptive AI has been updated more recently and is more likely to provide a greater competitive experience than the Sorian AI.
AI variants: Sorian, Rush, Air, Water, Turtle, Adaptive

## Upcoming AI
### M28AI
*Author: maudlin27*

This AI is only available from github as it is still in development and not yet suitable for release on the FAF vault.  While it is likely to be in a usable state on the majority of maps using default settings, there is a significant risk of errors.

It should be possible to play with this AI by downloading it from Github, and ensuring the M28AI folder is in your normal FAF mods folder (i.e. the same folder that other AI mods are saved to):
https://github.com/maudlin27/M28AI

Compared with M27AI M28AI aims to provide a more CPU performant AI that works better in teamgame scenarios, applying a decentralised approach to AI decisions to work more effectively on larger maps.

## Historic FAF AI
The following AI have previously been developed for FAF, but currently do not work, and are noted briefly for reference.

### AI-Swarm
*![swarmicon.jpg](/swarmicon.jpg)
Author: Azraeel*
Last updated: October 2022
Other mods required: AI-Uveso
Swarm stopped working following changes made to FAF in February 2023.  Although the author is currently unavailable, it is hoped that they may update Swarm at some point in the future to fix this issue.

This AI is a multi use AI that is designed mainly for 10km maps.  It provides an additional (optional) 'Eternal' game setting that provides the AI with a steadily increasing resource and build modifier to make it more challenging as the game progresses.
Note that this AI may have compatibility issues with RNGAI.
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

The following are general suggestions for creating games with AI - note that depending on specific comments/description made for the AI you are using these may not apply.

- Only enable the AI mods that you intend to use the AI for in a game unless you're using an AI mod that requires/recommends AI-Uveso.  This is because AI mods can still run some logic in the background even if not active as a player, so could impact on game speed and/or provide a risk of incompatibility.
- Maps of 20km or smaller are generally recommended for AI games - larger maps than this are unlikely to have been tested as much, while FAF balance is also more focused on 20km and smaller maps.
- Unit restrictions may have unexpected consequences for the AI, as AI are generally developed without unit restrictions in mind.  Some AI will handle unit restrictions better than others, but as a general rule if applying unit restrictions try to use as sparingly as possible
- Less conventional game settings such as a no rush radius/timer may not be supported by some AI - if the AI hasn't been specifically developed with no rush in mind, it could attempt to expand outside the norush radius, and build units to attack/defend even if under no immediate threat due to the norush timer
- You can adjust the challenge provided by an AI by fighting against the AIx variant and changing the AIx Cheat Multiplier (affects the bonus resources the AI generates), the AIx Build Multiplier (affects the bonus to build speed the AI gets) and the AIx Omni Setting (gives map-wide omni vision for the AI if enabled).
- Certain AI mods provide additional settings for changing how their AI behaves - these will depend on the AI in question, and are likely to only affect that particular AI.
- As a general rule, AI are most likely to perform as intended in a 1v1 scenario on a land focused map.  The extent to which AI handle other scenarios (e.g. naval based maps; games with 3+ teams on them; maps with less conventional features such as a massive amount of reclaim in one location to be fought over, or a strong civilian base) will vary significantly between the AI.
- Some AI will not work properly if given a start position that can't reach the enemy by land, and/or a start position that is in the water.
- Avoid using a low unit cap - AI will struggle to manage their unit counts, and depending on the AI may not have logic to stop building or self-destruct lower tech units to free up space for higher tech ones.
- Games with AI run slower than games with human players - try to avoid using large numbers of AI in a game, particularly on larger (20km+) sized maps unless you have a very good CPU or don't mind the game speed dropping.  If you're seeking more of a challenge, try a smaller number of the harder AI, making use of the AIx version of an AI, and/or one of the AI that runs sigificantly faster (see the AI tournament thread linked in the below section for further details).  As a rough guide, having 5+ AI players in a game is likely to make the game speed noticeably slower late-game.  However, the total number of units in a game is still likely to be the biggest factor in how fast the game runs.
- Try to limit how many different AI you have in a game at once due to the risk of incompatibilities and the increased strain on the computer (since different AI are likely to take different approaches to analysing the map and storing certain data, which could lead to high RAM usage and slower CPU speed).  There was previously a cap of 2GB on the amount of RAM that could be used by Forged Alliance (which could lead to crashes for certain AI late-game), but this RAM limit has been increased by FAF recently so such crashes are less likely (although in theory still possible, with the risk increasing based on both the number of different AI in a game, the number of AI players in a game, the map size, and the likely number of units featuring in the game).

# Feedback
You can provide feedback on particular AI in the FAF discord, through the ai-feedback channel.  To view this channel, go to the roles selection channel on the FAF discord (https://discord.com/channels/197033481883222026/831394581554790428) and indicating a preference for AI games in the "What Are Your Game Prefernces? Part 2 section.

Alternatively you can join the AI developers discord:
https://discord.gg/qdqcEGR7

Note that there is less likely to be a response regarding AI that are not under active development.

If reporting a bug with an AI, the following will be helpful for the AI developer to investigate it further:
* Include the replay ID number and time stamp of the issue, along with a description of the issue
* Specify whether you have any other mods active (and ideally if you get the same bug with just the AI mod in question active) - i.e. the more SIM mods that are active, the greater the chance of an error, which may be unrelated to the AI itself

# AI comparisons and tournaments
## AI vs Human tournaments
### Rainbow Cup
Rainbow Cup tournaments have been held every 6-12 months, the most recent of which, Rainbow Cup VI, is linked to below:
https://forum.faforever.com/topic/5400/rainbow-cup-vi-3v3-1-500
These tournaments typically pit 2 human teams against each other, with the AI featuring as a 3rd (and/or 4th) team in the game.  When one human team loses, the other human team wins the match.

A number of the games in the tournament are casted, and links to the first 2 (out of 3) days of the Rainbow Cup VI casts are below:
https://www.youtube.com/watch?v=EGQZE8nGwJc
https://www.youtube.com/watch?v=RdVUKdeLwE4

## AI vs AI tournaments
### Weekly/Monthly tournaments
A number of AI tournaments have been held highlighting:

- How well AI perform against each other (competitively)
- How fast AI run
- What maps different AI work best on
- What unit mixes different AI favour

These are summarised in the following forum thread:
https://forum.faforever.com/topic/2931/monthly-ai-tourney-series
Note however that these AI tournaments would only show a snapshot at a particular time, and a number of the AI featured have received significant updates since then.

### Computer cup
A computer cup tournament was held in June 2021, the results of the AI vs AI component of this are summarised in the below post:
https://forum.faforever.com/topic/1475/supreme-computer-cup/57

# Creating AI-friendly maps
The following contains tips and suggestions for map makers on how to create AI friendly maps:
https://docs.google.com/document/d/1sMvvSW90pPDXV35nYPbGhjdHFMYRYZws/edit?usp=share_link&ouid=100973959280546778272&rtpof=true&sd=true