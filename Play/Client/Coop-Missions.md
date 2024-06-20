---
title: Co-op Missions
description: 
published: true
date: 2024-06-20T13:01:25.774Z
tags: client
editor: markdown
dateCreated: 2021-08-31T09:42:43.854Z
---

Cooperative missions are a unique feature of Forged Alliance Forever, enabling players to tackle missions either solo or as a team.

Alongside the original GPG campaign missions from Supreme Commander and the Forged Alliance expansion, you can also discover exclusive FAF campaigns and single-scenario missions crafted by the FAF community.

### Features
- Supreme Commander campaigns
- Supreme Commander: Forged Alliance campaign
- FAForever campaigns and single scenarios
- Playable solo or with up to 4 players
- Includes all FAF graphics improvements
- Adjusted for cooperative difficulty
- Enhanced campaign AI
- Additional secondary objectives (thanks to gregory1001)
- Cooperative leaderboard: compete for the best time!
- Custom "M28AI" mod: This AI can be used as a teammate similar to a human player, or to take over existing AI allies or enemy campaign AI. [See details on setup](https://wiki.faforever.com/en/Play/Client/Coop-Missions#custom-campaign-ai).


## Interface
The interface is mostly self-explanatory, but we'll document it here anyway:

### Hosting Missions
- Select the desired mission from the dropdown list.
- Set the game title (Required).
- Set a password (Optional).
- Join Hosted Mission
- Double-click on the hosted game to join it.
- Enter any password as normal.
### Leaderboards
- View the best times for selected missions. These can provide valuable insights on how to beat a mission if you're struggling.
- Qualification: A mission must be cleared on 'hard' difficulty to qualify for the leaderboard. Difficulty can be changed in the lobby through the usual mission options.

The tables also provide an AIx modifier. This is intended to give a rough indication of mission difficulty by showing the AIx modifier needed for M28AI to complete the indicated campaign mission 'solo' (i.e., a single M28AI teammate is included alongside the human player). This offers an objective measure of the difficulty of a campaign mission, although human players' experiences may vary significantly.
![coop-missions.png](/coop-missions.png)

## Missions List
### GPG Original Campaigns & AI Difficulty

| # | SupCom - UEF          | AIx Modifier | SupCom - Aeon         | AIx Modifier | SupCom - Cybran      | AIx Modifier |
|---|-----------------------|--------------|-----------------------|--------------|----------------------|--------------|
| 1 | Black Earth           | 0.5          | Joust                 | 0.5          | Liberation           | 0.5          |
| 2 | Snow Blind            | 0.6          | Machine Purge         | 0.5          | Artifact             | 0.5          |
| 3 | Metal Shark           | 0.5          | High Tide             | 0.6          | Defrag               | 0.5          |
| 4 | Vaccine               | 0.5          | Entity                | 0.6          | Mainframe Tango      | 0.5          |
| 5 | Forge                 | 1.1          | Shining Star          | 0.7          | Unlock               | 0.6          |
| 6 | Stone Wall (remastered) | 0.5        | Beginnings            | 0.6          | Freedom (remastered) | 2.3          |

### Forged Alliance Campaign Mission & AI Difficulty

| # | Forged Alliance Mission | AIx Modifier |
|---|--------------------------|--------------|
| 1 | Black Day                | 1.3          |
| 2 | Dawn                     | 0.5          |
| 3 | Red Flag                 | 0.5          |
| 4 | Meltdown                 | 0.7          |
| 5 | Mind Games               | 0.7          |
| 6 | Overlord                 | 1.3          |


### Seraphim FAF Campaigns & AI Difficulty
Similarly to the original campaigns, these are linked in the story, and it is advised they be played in order.

| # | Seraphim Campaign       | AIx Modifier | Coalition Campaign  | AIx Modifier |
|---|-------------------------|--------------|---------------------|--------------|
| 1 | Yath-Aez                | 1.8          | Blockade            | 2.2          |
| 2 | Operation Tha-Atha-Aez  | >10.0*       | Holy Raid           | 1.5          |
| 3 | Uhthe-Thuum-QAI         | 2.1          | Golden Crystals     | 1.8          |
| 4 | Ioz-Shavoh-Kael         | 1.5          | Rebel's Rest        | 5.5          |
| 5 | Overlord Surth-Velsok   | 2.1          | Red Revenge         | 5.4          |

*Note: The AIx modifier for "Operation Tha-Atha-Aez" is exceptionally high, indicating a very challenging mission.

(*M28 failed with a 10.0 AIx modifier on this mission due to the order it targets enemy bases, resulting in a near-impossible challenge to protect SACUs that walk straight into an enemy base. Without this issue, the AIx modifier is estimated at 2.3 for this mission.)

### FAForever Custom Scenarios
These missions are single scenarios, meaning they are not linked to larger campaigns or other single scenarios and don't need to be played in a particular order.

| Custom Scenarios       |                    |                       |                         |
|------------------------|--------------------|-----------------------|-------------------------|
| Prothyon - 16          | Operation Rescue   | Theta Civilian Rescue | Novax Station Assault   |
| Fort Clarke Assault    | Tight Spot         | Haven's Invasion      | Operation Trident       |
| Rescue                 | Trident            |                       |                         |

##### Notes:
- FAForever campaigns are on average harder than the original GPG campaigns - don't forget you can adjust the difficulty setting in the lobby prior to launching the game
- Coalition Campaign missions were designed to be played by co-op teams, rather than as solo missions - they will present quite the challenge for those attempting to play them solo

## Custom campaign AI
![fletcher28.png](/fletcher28.png)![rhiza28.png](/rhiza28.png)
### AI options
The M28AI mod allows you to customise the AI on campaign missions - players can choose any or all of the following options:
- An AI teammate - start the game with a teammate controlled by M28AI (in the same way that you can play a mission with a human teammate).  You can also choose to use an AIx variant and set the resource and build rate modifiers to the desired level, and/or have this adjust over time using the AIx overwhelm settings (to make the AI stronger or weaker as the game progresses).
- Use M28AI logic for allied AI - where there is an allied AI faction with units, this option allows M28AI to take over control of their units.  For example, this allows the rebels on Dawn (FA Mission 2) to have a significant impact on the mission if allowed to survive.  AIx modifiers can be applied to the alleid AI if desired.
- Use M28AI logic for hostile AI - this allows M28AI to take over control of hostile AI armies in campaign missions, meaning it will actively seek to use the units under its control to defeat you (in contrast to the default AI where it can often play more passively with the exception of scripted periodic attacks).  AIx modifiers can be applied to the AI if desired (meaning you can give it a greater or reduced resource and/or build rate).

#### Setup
Make sure you have downloaded the M28AI mod from the FAF vault and the mod is active.

When hosting a campaign mission, to play with an M28AI buddy, include it as one of the players:
![m28ai_buddy.png](/m28ai_buddy.png)

To apply M28AI to in-mission AI allies and/or enemies, select the Options within the lobby and choose the preferred settings (i.e. Allied AI; Enemy AI; or Allied and Enemy AI)
![m28ai_game_options_-_ai_to_apply.png](/m28ai_game_options_-_ai_to_apply.png)

You can further adjust the M28AI to apply to in-mission allies and the hostile AI in game options as follows:
- M28Coop: Use AIX modifiers? If set to yes, then it will apply the AIx cheat and build multipliers to M28AI
- AIx Cheat Multiplier - affects the resource modifier the AI receives (if Use AIx modifiers is set to yes). 1.0 means it receives a normal level of resources.  Set to below 1.0 for a weaker AI.
- AIx Build Multiplier - affects the build modifier the AI receives (if "Use AIx modifiers" is set to yes, in the case of allied/hostile AIs as opposed to 'player' AIs).  1.0 means units have the normal build rate.  Set to below 1.0 for a weaker AI.
- M28AIx Overwhelm rate, interval and limit - where the AIx modifier is to be applied to an M28AI, these allow you to make the AIx modifier increase or decrease over time (rate being the amount by which the build and resource modifiers change, interval being how many minutes between each change, and the limit being the point at which the modifier stops changing).
- M28Coop: Hostile combat delay - where M28AI is applied to the hostile AI, it will wait this number of seconds before applying most of it's offensive logic to the hostile AI's units.  By default this is set to 300 (being 5 minutes).  On missions where the hostile AI starts with a large army, it may be necessary to increase this to avoid too high a difficulty level.  For more of a challenge, the delay can be decreased.
- M28Coop: Use M28Easy? - This applies M28EasyAI to the allied/hostile AI instead of M28AI.  M28EasyAI uses most of the M28AI's macro logic, but doesn't micro its units and uses very simple attack logic.

### Campaign difficulty level for M28AI
See the above mission listings for how difficult different missions are for M28AI, based on the AIx modifier it needed to complete the mission without human assistance.

For reference, the following are noted in respect of how this was tested
- The human player remains afk throughout the game subject to rare exceptions where they are required to progress the mission (or are given significant starting units required to defend in the opening minutes).
- All missions were done on default settings, meaning Hard difficulty, with timed map expansions enabled, while M28AI was only used for the AI player (not for allies or enemies).
- Most of the above results are based on v91-v96 of M28AI, based on the latest versions of campaign maps available in April-May 2024.

### Other notes
- See the [Custom AI](https://wiki.faforever.com/en/Development/AI/Custom-AIs) section for further details on using Custom AI. 
- Custom AI are unlikely to be tested regularly on campaign maps, meaning it is possible that changes to the AI and/or to FAF could result in unexpected issues or bugs.
- If you encounter bugs when using a custom AI in campaign, please contact the mod author via discord with further details (e.g. in the case of M28AI please contact maudlin27, and include the replayID and a summary of the issue).