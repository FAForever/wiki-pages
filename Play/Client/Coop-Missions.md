---
title: Co-op Missions
description: 
published: true
date: 2024-06-20T13:04:25.914Z
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

**Further Adjustments in Game Options:**

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
  
- **M28Coop: Use M28Easy?**
  - Applies M28EasyAI to allied/hostile AI instead of M28AI, which simplifies unit micro and attack logic for a different challenge level.

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