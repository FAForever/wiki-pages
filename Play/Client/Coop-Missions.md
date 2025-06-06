---
title: Co-op Missions
description: 
published: true
date: 2025-04-30T07:38:00.641Z
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

*Note: The AIx modifier for "Operation Tha-Atha-Aez" failed with a 10.0 AIx modifier on this mission due to the order it targets enemy bases, resulting in a near-impossible challenge to protect SACUs that walk straight into an enemy base. Without this issue, the AIx modifier is estimated at 2.3 for this mission (meaning a human player is likely to find some of the other maps harder than this mission).

### FAForever Custom Scenarios
These missions are single scenarios, meaning they are not linked to larger campaigns or other single scenarios and don't need to be played in a particular order.

| Custom Scenarios       |                    |                       |                         |
|------------------------|--------------------|-----------------------|-------------------------|
| Prothyon - 16          | Operation Rescue   | Theta Civilian Rescue | Novax Station Assault   |
| Fort Clarke Assault    | Tight Spot         | Haven's Invasion      | Operation Trident       |
| Rescue                 | Trident            |                       |                         |

#### Notes:
- **FAForever campaigns** are generally more challenging than the original GPG campaigns. Remember, you can adjust the difficulty setting in the lobby before starting the game.
- **Coalition Campaign missions** are designed for co-op teams rather than solo play. They will present a significant challenge for those attempting to complete them alone.

## Custom campaign AI
![fletcher28.png](/fletcher28.png)![rhiza28.png](/rhiza28.png)
### AI Options with M28AI Mod

The M28AI mod offers customizable AI options for campaign missions, providing players with several choices:

- **AI Teammate**: Start the game with an AI-controlled teammate using M28AI, similar to playing with a human teammate. You can adjust the AIx variant and set resource and build rate modifiers, which can dynamically change using AIx overwhelm settings to adjust AI strength throughout the game.

- **AI Logic for Allied AI**: Allows M28AI to take control of units belonging to allied AI factions. For instance, this option can significantly impact missions like Dawn (FA Mission 2) if the allied rebels are allowed to survive. AIx modifiers can also be applied to allied AI for additional customization.

- **AI Logic for Hostile AI**: Enables M28AI to control hostile AI armies in campaign missions, making them actively use their units to challenge and defeat the player. This contrasts with the default AI behavior, which tends to be more passive except during scripted attacks. AIx modifiers can adjust the resources and build rates of hostile AI, increasing or decreasing their challenge level.

These options provide players with flexibility to enhance the AI experience in campaign missions, adapting difficulty and gameplay dynamics according to their preferences and strategies.

#### Setup for M28AI Mod

Ensure you have downloaded and activated the M28AI mod from the FAF vault.

**Hosting a Campaign Mission with M28AI:**

When hosting a campaign mission and wanting to play with an M28AI teammate, include it as one of the players:
![m28ai_buddy.png](/m28ai_buddy.png)

**Applying M28AI to In-Mission AI:**

To apply M28AI logic to in-mission AI allies and/or enemies, follow these steps:

1. Navigate to the Options section within the lobby.
2. Select the preferred settings for applying M28AI:
   - Choose "Allied AI," "Enemy AI," or both for comprehensive AI control.
   ![m28ai_game_options_-_ai_to_apply.png](/m28ai_game_options_-_ai_to_apply.png)

**Further Adjustments to M28's behaviour in Game Options:**

You can fine-tune M28AI settings for in-mission allies and hostile AI with these options:

- **M28Coop: Use AIx Modifiers?**
  - Enable to apply AIx cheat and build multipliers to M28AI.
  
- **AIx Cheat Multiplier**
  - Adjusts the resource modifier the AI receives. A setting of 1.0 means normal resource levels; below 1.0 weakens the AI.
  
- **AIx Build Multiplier**
  - Affects the build rate of AI units. A setting of 1.0 means normal build speed; below 1.0 reduces it.
  
- **M28AIx Overwhelm Rate, Interval, and Limit**
  - Controls how the AIx modifier changes over time: rate (amount of change), interval (time between changes), and limit (maximum modifier).
  
- **M28Coop: Hostile Combat Delay**
  - Delays the application of offensive logic to hostile AI units. Default is 300 seconds (5 minutes); adjust as needed.
  
- **M28Coop: M28 Personality**
  - Applies the specified personality to allied/hostile AI.  E.g. use M28Easy to simplify unit micro and attack logic for a different challenge level.
  
  **M28 enemy threat factor**
  - Applies the specified factor to the majority of M28's calculations of how strong enemy units are.  For example, a value of 0.1 means M28 will see enemy units as being 10% as strong/valuable as normal.
  - This could be used to try and significantly change how M28 plays (e.g. a value of below 1 means M28 will attack more often with units where it would normally have held off due to expecting to lose the fight), and/or used in conjunction with the shared armies mode.  For a competitive experience it is recommended you use the default value of 1.0.
  
- **Adjust M28 micro (various)**
The following game options allow you to adjust certain micro logic for M28:
  - M28: Use dodge micro? - Allows you to limit the number of units M28 will try to micro to dodge incoming fire
  - M28: Use hover air micro? - Allows you to limit the extent to which bombers will use 'hover-micro' to quickly turn around or hover-bomb (and disables such hovering for inties/asfs)
  - M28 time between orders - By default M28 considers what orders to give its land, air and naval units every second, which allows it to react quickly in order to (for example) kite with its land units.  This setting allows you to increase the time between orders from 1 second to up to every 10 seconds.  This can be useful both to reduce the extent and effectiveness of M28's general microing, and also make it run faster.

**M28: CPU performance mode**
- Disables some of the more CPU intensive logic/uses simpler alternatives.  This reduces the effectiveness of M28 slightly, but also means it should run slightly faster (so may be useful for slow CPUs)

**M28: Prioritise stronger units**
- By default M28 will try and build the units it thinks are the strongest (where it has multiple units of a particular category/type).  Enabling this means it ignores such prioritisation, and can lead to a greater variety of units being built (in the case of certain mods that provide additional units).

**M28: Combined AI-Human armies**
- Enabling this mode allows you to transfer control (temporarily or permanently) of your units to M28 to manage for you, by selecting the relevant units and clicking on the M28 icon in the unit abilities section.
- It can also be worth enabling this even if you dont intend to have M28 take control of any of your units, if M28 is a teammate, as enabling this means M28 assumes you will use your units to support it in the same way that an M28 player would (and so enabling this impacts on its behaviour as a teammate).
- Poor CPUs or games on large maps with lots of players may run slower with this option enabled.
- M28: CA Inherit constructing unit status can be used to set whether units built by such an 'M28 controlled' unit should default to also being controlled by M28 (e.g. enabling this and then giving M28 control of an engineer means if that engineer builds a land factory M28 will start building units, which it will then control, until you click the M28AI icon to toggle its control of the units).

**M28: Helpful teammates**
- If M28 is a teammate of yours (i.e. you star the game with M28AI in one of the player slots) then it by default should try and be helpful, doing things like assisting experimentals you construct if it's nearby, highlighting major enemy threats, etc.; this setting allows you to disable such behaviour.
- As noted above you can also enable the Combined AI-Human armies to have M28 work better with your own forces as a teammate.

These settings allow you to tailor the AI experience in campaign missions according to your preferences, adjusting difficulty and gameplay dynamics for a more customized experience.

### Campaign Difficulty Assessment for M28AI

Refer to the mission listings above to understand the difficulty levels for M28AI, indicated by the AIx modifier required for it to complete the mission without human intervention.

#### Testing Methodology:
- **Human Player Inactivity**: The human player remains AFK (away from keyboard) throughout the game, with rare exceptions where their input is necessary to progress the mission or manage significant starting units.
- **Default Settings**: All missions were conducted on default settings, specifically on Hard difficulty with timed map expansions enabled. M28AI was utilized solely for the AI player and not for allied or enemy factions.
- **Version and Map Considerations**: Results are primarily based on versions v91 to v96 of M28AI, aligned with the latest campaign maps available as of April-May 2024.

These assessments provide insights into the relative difficulty of each mission when M28AI is employed, helping players gauge potential challenges and strategize accordingly.

## Other Notes

- For more information on using Custom AI, refer to the [Custom AI](https://wiki.faforever.com/en/Development/AI/Custom-AIs) section.
- Custom AIs may not undergo regular testing on campaign maps, which could lead to unexpected issues or bugs due to changes in the AI or FAF system.
- If you encounter bugs while using a Custom AI in campaigns, please contact the mod author via Discord. For M28AI, please reach out to maudlin27 and include the replay ID along with a summary of the issue for assistance.