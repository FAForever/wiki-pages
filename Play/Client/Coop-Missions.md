---
title: Co-op Missions
description: 
published: true
date: 2024-05-16T19:57:02.649Z
tags: client
editor: markdown
dateCreated: 2021-08-31T09:42:43.854Z
---

Cooperative missions are an exclusive feature of Forged Alliance Forever that makes it possible for players to tackle the missions as a team, as well as on their own.

In addition to the original GPG campaign missions from the original Supreme Commander game and the Forged Alliance expansion, exclusive FAF campaigns and single-scenario missions created by the FAF community can also be found.

### Features
- Supreme Commander campaigns
- Supreme Commander: Forged Alliance campaign
- FAForever campaigns and single scenarios
- Can be played solo or with up to 4 players.
- All FAF graphics improvements
- Adjustment for cooperative difficulty
- Slightly better campaign AI
- Additional secondary objectives (thanks to gregory1001)
- Cooperative leaderboard. Fight for the best time!
- Custom "M28AI" mod whose AI can be played with as a teammate similar to a human player, or which can be used to take over existing AI allies or the enemy campaign AI (see below for details on how to setup)
## Interface
The interface is mostly self-explanatory, but we'll document it here anyway, as labelled:
1) **Hosting Missions**
- Select the desired mission from the dropdown list.
- Set the game title (Required)
- Set a password (Optional)

2) **Join Hosted Mission**
Double-click on the hosted game in order to join it. Enter any password as normal.

3) **Leaderboards**
Here you can see the best times for selected missions. Watching these can give you a lot of information on how to beat a mission if you're struggling with it!
Note that a mission must be cleared in 'hard' difficulty in order to qualify for the leaderboard. Difficulty can be changed in the lobby through usual mission options.

![coop-missions.png](/coop-missions.png)

## Missions List
##### GPG original campaigns
| | SupCom - UEF   	| SupCom - Aeon   	| SupCom - Cybran 	 | | SupCom - FA  |
|-|----------------	|-----------------	|------------------- |-|------------	|
|1| Black Earth    	| Joust           	| Liberation         | | Black Day  	|
|2| Snow Blind     	| Machine Purge   	| Artifact           | | Dawn       	|
|3| Metal Shark    	| High Tide       	| Defrag             | | Red Flag   	|
|4| Vaccine        	| Entity           	| Mainframe Tango    | | Meltdown   	|
|5| Forge          	| Shining Star    	| Unlock             | | Mind Games 	|
|6| Stone Wall     	| Beginnings      	| Freedom            | | Overlord   	|

##### FAForever campaigns
Similarly to the original campaigns, these are linked in the story, and it is advised they be played in order.
| | Seraphim Campaign         | Coalition Campaign |
|-|-------------------------- |------------------- |
|1| Yath-Aez                  | Blockade           | 
|2| Operation Tha-Atha-Aez    | Holy Raid          | 
|3| Uhthe-Thuum-QAI           | Golden Crystals    | 
|4| Ioz-Shavoh-Kael           | Rebel's Rest       |
|5| Overlord Surth-Velsok			| Red Revenge        |
##### FAForever custom scenarios
These missions are single scenarios, meaning they are not linked to larger campaigns or other single scenarios and don't require playing in a particular order.
|Custom scenarios       ||||
|---------------------- |------------------------|------------------------|------------------------|
| Prothyon - 16         | Operation Rescue       | Theta Civilian Rescue | Novax Station Assault  |
| Fort Clarke Assault   | Tight Spot        	   | Haven's Invasion      | Operation Trident      |
| Rescue                | Trident                | | |
##### Notes:
- FAForever campaigns are on average harder than the original GPG campaigns - don't forget you can adjust the difficulty setting in the lobby prior to launching the game
- Coalition Campaign missions were designed to be played by co-op teams, rather than as solo missions - they will present quite the challenge for those attempting to play them solo

## Custom campaign AI
![fletcher28.png](/fletcher28.png)![rhiza28.png](/rhiza28.png)
### AI options
The M28AI mod allows you to customise the AI on campaign missions - players can choose any or all of the following options:
- An AI teammate - start the game with a teammate controlled by M28AI (in the same way that you can play a mission with a human teammate).  You can also choose to use an AiX variant and set the resource and build rate modifiers to the desired level.
- Use M28AI logic for allied AI - where there is an allied AI faction with units, this option allows M28AI to take over control of their units.  For example, this allows the rebels on Dawn (FA Mission 2) to have a significant impact on the mission if allowed to survive.  AiX modifiers can be applied to the alleid AI if desired.
- Use M28AI logic for hostile AI - this allows M28AI to take over control of hostile AI armies in campaign missions, meaning it will actively seek to use the units under its control to defeat you (in contrast to the default AI where it can often play more passively with the exception of scripted periodic attacks).  AiX modifiers can be applied to the AI if desired (meaning you can give it a greater or reduced resource and/or build rate).

#### Setup
Make sure you have downloaded the M28AI mod from the FAF vault and the mod is active.

When hosting a campaign mission, to play with an M28AI buddy, include it as one of the players:
![m28ai_buddy.png](/m28ai_buddy.png)

To apply M28AI to in-mission AI allies and/or enemies, select the Options within the lobby and choose the preferred settings (i.e. Allied AI; Enemy AI; or Allied and Enemy AI)
![m28ai_game_options_-_ai_to_apply.png](/m28ai_game_options_-_ai_to_apply.png)

You can further adjust the M28AI to apply to in-mission allies and the hostile AI in game options as follows:
- M28Coop: Use AIX modifiers? If set to yes, then it will apply the AIx cheat and build multipliers to M28AI
- AIx Cheat Multiplier - affects the resource modifier the AI receives (if Use AIX modifiers is set to yes). 1.0 means it receives a normal level of resources.  Set to below 1.0 for a weaker AI.
- AIx Build Multiplier - affects the build modifier the AI receives (if Use AIX modifiers is set to yes).  1.0 means units have the normal build rate.  Set to below 1.0 for a weaker AI.
- M28Coop: Hostile combat delay - where M28AI is applied to the hostile AI, it will wait this number of seconds before applying most of it's offensive logic to the hostile AI's units.  By default this is set to 300 (being 5 minutes).  On missions where the hostile AI starts with a large army, it may be necessary to increase this to avoid too high a difficulty level.  For more of a challenge, the delay can be decreased.
- M28Coop: Use M28Easy? - This applies M28EasyAI to the allied/hostile AI instead of M28AI.  M28EasyAI uses most of the M28AI's macro logic, but doesn't micro its units and uses very simple attack logic.

### Campaign difficulty level for M28AI
The following is intended to provide a rough indication of the difficulty level for M28AI to complete the indicated campaign mission 'solo' (i.e. a single M28AI teammate is included alongside the (human) player.

The below also allows more of an objective measure of the difficulty of a campaign mission, albeit with the caveat it is from the AI's perspective and human players' experiences will likely vary significantly.

| | SupCom - UEF   	| AiX modifier |
|-|----------------	|-----------------	|
|1| Black Earth    	| 1.0
|2| Snow Blind     	| 1.0
|3| Metal Shark    	| 1.0
|4| Vaccine        	| 1.0
|5| Forge          	| 1.1
|6| Stone Wall     	| 1.0


| | SupCom - Aeon   	| AiX modifier |
|-|----------------	|-----------------	|
|1| Joust    	| 1.0
|2| Machine Purge     	| 1.0
|3| High Tide    	| 1.0
|4| Entity        	| 1.0
|5| Shining Star          	| 1.0
|6| Beginnings     	| 1.0


| | SupCom - Cybran   	| AiX modifier |
|-|----------------	|-----------------	|
|1| Liberation    	| 1.0
|2| Artifact     	| 1.0
|3| Defrag    	| 1.0
|4| Mainframe Tango        	| 1.0
|5| Unlock          	| 1.0
|6| Freedom     	| 2.3


| | Forced Alliance   	| AiX modifier |
|-|----------------	|-----------------	|
|1| Black Day    	| 1.3
|2| Dawn     	| 1.0
|3| Red Flag    	| 1.0
|4| Meltdown        	| 1.0
|5| Mind Games          	| 1.0
|6| Overlord     	| 1.3


| | Coalition Campaign         | AiX modifier |
|-|-------------------------- |------------------- |
|1| Blockade           | 2.2
|2| Holy Raid          | 1.5
|3| Golden Crystals    | 1.8
|4| Rebel's Rest       | 5.5
|5| Red Revenge        | 3.5


#### Notes on AI campaign difficulty
- The human player remains afk throughout the game subject to rare exceptions where they are required to progress the mission (or are given significant starting units required to defend in the opening minutes).
- All missions were done on default settings, meaning Hard difficulty, with timed map expansions enabled, while M28AI was only used for the AI player (not for allies or enemies).
- Unless specifically noted, sub-1.0 AiX modifiers were not used (it is expected that many of the original supcom missions could be completed with a sub-1.0 modifier).

### Other notes
- See the [Custom AI](https://wiki.faforever.com/en/Development/AI/Custom-AIs) section for further details on using Custom AI. 
- Custom AI are unlikely to be tested regularly on campaign maps, meaning it is possible that changes to the AI and/or to FAF could result in unexpected issues or bugs.
- If you encounter bugs when using a custom AI in campaign, please contact the mod author via discord with further details (e.g. in the case of M28AI please contact maudlin27, and include the replayID and a summary of the issue).