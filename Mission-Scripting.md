---
title: Mission Scripting
description: 
published: true
date: 2022-06-14T22:40:36.194Z
tags: mapping
editor: markdown
dateCreated: 2021-08-31T09:44:25.458Z
---

## Introduction
Currently there is no campaign editor for creating custom missions for Supreme Commander, but every mission is written in lua and it's easy to edit. You don't need to have too much experience with code since most of it is already used in the official campaign missions. In this tutorial I will explain how to create a mission and as an example we will use [Prothyon - 16](https://mega.co.nz/#!RpZ3GZZa!zBAJfoJ-29PDA3lewcJYMBVbyLLDoK609ueeMe80N00).

### Tools we need
- [Map Editor](/Map-Editing-Tools) for creating map, placing units and markers.
- Text Editor that highlight syntax [Visual Studio Code](https://code.visualstudio.com/)

### Sources of inspiration
You can always look in one of the original campaign files to find the right code. There is a list of them. In order to open them in [Map Editor](/GPG-Map-Editor), use files from [this link](https://mega.nz/#!V4BmhZzB!BT61LjJsjkcW_vIiwjykfUK5bOSGYuTGAVc7DsdJ1As). Don't forget you can also look at custom map scripts for useful code snippets, some of which aren't present in the original campaign. Additionally, you can look at in game lua files, and take apart the functions there for your own uses. 

It is better to look at Forged Alliance missions because the code there is simpler and easier to read and understand. Also AI was improved a lot there. So for creating AI we will use FA missions. 
<table>
<thead>
<tr class="header">
<th><p>Original Missions</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><dl>
<dt></dt>
<dd>
</dd>
</dl>
<table>
<thead>
<tr class="header">
<th><p>Campaign</p></th>
<th><p>Folder Name</p></th>
<th><p>Mission Name</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><img src="/images/mapping/fa_icon.png" title="fig:FA_Icon.png" width="20" alt="FA_Icon.png" /> FA</p></td>
<td><p>X1CA_001</p></td>
<td><p>Black Day</p></td>
</tr>
<tr class="even">
<td><p><img src="/images/mapping/fa_icon.png" title="fig:FA_Icon.png" width="20" alt="FA_Icon.png" /> FA</p></td>
<td><p>X1CA_002</p></td>
<td><p>Dawn</p></td>
</tr>
<tr class="odd">
<td><p><img src="/images/mapping/fa_icon.png" title="fig:FA_Icon.png" width="20" alt="FA_Icon.png" /> FA</p></td>
<td><p>X1CA_003</p></td>
<td><p>Red Flag</p></td>
</tr>
<tr class="even">
<td><p><img src="/images/mapping/fa_icon.png" title="fig:FA_Icon.png" width="20" alt="FA_Icon.png" /> FA</p></td>
<td><p>X1CA_004</p></td>
<td><p>Meltdown</p></td>
</tr>
<tr class="odd">
<td><p><img src="/images/mapping/fa_icon.png" title="fig:FA_Icon.png" width="20" alt="FA_Icon.png" /> FA</p></td>
<td><p>X1CA_005</p></td>
<td><p>Mind Games</p></td>
</tr>
<tr class="even">
<td><p><img src="/images/mapping/fa_icon.png" title="fig:FA_Icon.png" width="20" alt="FA_Icon.png" /> FA</p></td>
<td><p>X1CA_006</p></td>
<td><p>Overlord</p></td>
</tr>
<tr class="odd">
<td><p><img src="/images/mapping/aeon.png" title="fig:Aeon.png" width="20" alt="Aeon.png" /> Aeon</p></td>
<td><p>SCCA_A01</p></td>
<td><p>Jous</p></td>
</tr>
<tr class="even">
<td><p><img src="/images/mapping/aeon.png" title="fig:Aeon.png" width="20" alt="Aeon.png" /> Aeon</p></td>
<td><p>SCCA_A02</p></td>
<td><p>Machine Purge</p></td>
</tr>
<tr class="odd">
<td><p><img src="/images/mapping/aeon.png" title="fig:Aeon.png" width="20" alt="Aeon.png" /> Aeon</p></td>
<td><p>SCCA_A03</p></td>
<td><p>High Tide</p></td>
</tr>
<tr class="even">
<td><p><img src="/images/mapping/aeon.png" title="fig:Aeon.png" width="20" alt="Aeon.png" /> Aeon</p></td>
<td><p>SCCA_A04</p></td>
<td><p>Operation Entity</p></td>
</tr>
<tr class="odd">
<td><p><img src="/images/mapping/aeon.png" title="fig:Aeon.png" width="20" alt="Aeon.png" /> Aeon</p></td>
<td><p>SCCA_A05</p></td>
<td><p>Shining Star</p></td>
</tr>
<tr class="even">
<td><p><img src="/images/mapping/aeon.png" title="fig:Aeon.png" width="20" alt="Aeon.png" /> Aeon</p></td>
<td><p>SCCA_A06</p></td>
<td><p>Beginnings</p></td>
</tr>
<tr class="odd">
<td><p><img src="/images/mapping/uef.png" title="fig:Uef.png" width="20" alt="Uef.png" /> UEF</p></td>
<td><p>SCCA_E01</p></td>
<td><p>Black Earth</p></td>
</tr>
<tr class="even">
<td><p><img src="/images/mapping/uef.png" title="fig:Uef.png" width="20" alt="Uef.png" /> UEF</p></td>
<td><p>SCCA_E02</p></td>
<td><p>Snow Blind</p></td>
</tr>
<tr class="odd">
<td><p><img src="/images/mapping/uef.png" title="fig:Uef.png" width="20" alt="Uef.png" /> UEF</p></td>
<td><p>SCCA_E03</p></td>
<td><p>Metal Shark</p></td>
</tr>
<tr class="even">
<td><p><img src="/images/mapping/uef.png" title="fig:Uef.png" width="20" alt="Uef.png" /> UEF</p></td>
<td><p>SCCA_E04</p></td>
<td><p>Vacinne</p></td>
</tr>
<tr class="odd">
<td><p><img src="/images/mapping/uef.png" title="fig:Uef.png" width="20" alt="Uef.png" /> UEF</p></td>
<td><p>SCCA_E05</p></td>
<td><p>Forge</p></td>
</tr>
<tr class="even">
<td><p><img src="/images/mapping/uef.png" title="fig:Uef.png" width="20" alt="Uef.png" /> UEF</p></td>
<td><p>SCCA_E06</p></td>
<td><p>Stone Wall</p></td>
</tr>
<tr class="odd">
<td><p><img src="/images/mapping/cybran.png" title="fig:Cybran.png" width="20" alt="Cybran.png" /> Cybran</p></td>
<td><p>SCCA_R01</p></td>
<td><p>Liberation</p></td>
</tr>
<tr class="even">
<td><p><img src="/images/mapping/cybran.png" title="fig:Cybran.png" width="20" alt="Cybran.png" /> Cybran</p></td>
<td><p>SCCA_R02</p></td>
<td><p>Artifact</p></td>
</tr>
<tr class="odd">
<td><p><img src="/images/mapping/cybran.png" title="fig:Cybran.png" width="20" alt="Cybran.png" /> Cybran</p></td>
<td><p>SCCA_R03</p></td>
<td><p>Defrag</p></td>
</tr>
<tr class="even">
<td><p><img src="/images/mapping/cybran.png" title="fig:Cybran.png" width="20" alt="Cybran.png" /> Cybran</p></td>
<td><p>SCCA_R04</p></td>
<td><p>Mainframe Tango</p></td>
</tr>
<tr class="odd">
<td><p><img src="/images/mapping/cybran.png" title="fig:Cybran.png" width="20" alt="Cybran.png" /> Cybran</p></td>
<td><p>SCCA_R05</p></td>
<td><p>Unlock</p></td>
</tr>
<tr class="even">
<td><p><img src="/images/mapping/cybran.png" title="fig:Cybran.png" width="20" alt="Cybran.png" /> Cybran</p></td>
<td><p>SCCA_R06</p></td>
<td><p>Freedom</p></td>
</tr>
</tbody>
</table></td>
</tr>
</tbody>
</table>
Map Editor sees only maps located in **maps** folder where Supreme Commander is installed. Usually:

`C:\Program Files (x86)\THQ\Gas Powered Games\Supreme Commander\maps`

All functions used in missions are defined in lua files that are in your FA installation. You can study then to find out more option you can use in your missions. They are commented and usually easy to understand. ".scd" files are just renamed zip.

`Supreme Commander - Forged Alliance\gamedata\lua.scd`
`Supreme Commander - Forged Alliance\gamedata\mohodata.scd`

### How it works
Each mission is basically a map with extra files for AI and extended script file. In our example we can see several files. Always name these files same as the name of the folder they're in.

Folder is called **Prothyon16** (followed by version, for example Prothyon16.v0004. Versioning is done automatically on the server so you don't need to care about it) and these are the files in it:
- **Prothyon16.scmap** - This file is missing since map Shards was used instead.
- **Prothyon16_m1uefai.lua** - File controling UEF AI from first objective.
- **Prothyon16_m2uefai.lua** - File controling UEF AI from second objective.
	- Other AI files...
- **Prothyon16_CustomFunctions.lua** - You won't find this file in other missions since it contains functions I wrote, that are not part of coop mod or FAF patch. Usually things for AI that are under testing or not fully finished. Once done they are added into either FAF patch or coop mod so everyone can use them easily.
- **Prothyon16_save.lua** - Armies and markers are saved here. 
- **Prothyon16_scenario.lua** - Basic information are stored here. Path to other files, mission name, armies, etc...
- **Prothyon16_script.lua** - Main file that is in control of everything.
- **Prothyon16_strings.lua** - Voice overs and taunts.

### How to test missions
You can test your mission offline, which allows restarting and even saving, so its usually faster. In order to test your mission start the FAF version of FA from

`C:\ProgramData\FAForever\bin\`

You can create a shortcut on your desktop of that executable, go into its properties (right click) and change the target to include a [command line switch](/Command-Line-Switches):
`ForgedAlliance.exe /init init_coop.lua`
- Make sure you have the Coop patch downloaded if it's different from FAF patch - to do this simply host a coop game.
- You don't need to restart FA each time you modify a script. You can just restart the map inside FA.
- Run FA in windowed mode and use the game log for debug. The default hotkey for showing the log window is: **F9** (in some cases, just **Ctrl + F9**). It can be opened during the map loading screen. If you make a mistake in any of the files, the log will show you what you did wrong, giving the file and line where the error is.

## Scenario
Game uses this file to get basic information about the map. Name, path to other files, armies, etc. It is created with map, once you save your map. You can edit these information.
- **name** - Name of your map that will be displayed in game lobby.
- **description** - Description of your map that will be displayed in game lobby.
- **type** - Change this value to **campaign_coop**. 
- **preview** - Keep this empty to have working map preview in FAF lobby.
- **size** - Size of the map, do not change it.
- **map** - Path to map file.
- **save** - Path to save file.
- **script** - Path to script file.
- **map_version** - Version of the mission, set this to 1, it is used by the server when updating the missions in coop tab.
- **norushradius** - Set this to 0, it is used for skirmish maps, but the Map Editor needs this value else it will crash during loading

All armies have to be listed here. This part is created once [Games configuration](/Map-Editor#create-armies) is set in Map
Editor. Example:
```lua
Configurations = {`
       ['standard'] = {`
           teams = {`
               { name = 'FFA', armies = {'Player1','UEF','UEFAlly','Objective','Seraphim','Player2','Player3','Player4',} },`
           },`
           customprops = {`
           },`
           factions = { {'uef'}, {'uef'}, {'uef'}, {'uef'} },`
       },`
   }}`
```

One coop addition that you find here is the table with available factions per spot, this restricts the lobby and offers the player to pick only from the factions you specify here. There are 4 tables with **'uef**' as Prothyon mission is for 4 players and it's UEF only.

## Save
This file contains all data about armies and markers that was created in the [Map Editor](/Map-Editor).
![armies.png](/images/mapping/armies.png){.align-right}

### Alliances
Alliances among armies can be changed in Armies tab by clicking on the army you want to edit. They need to be set for every army. By default all alliances are set to **Neutral**.

### AI Faction
You also need to set AI faction here else AI won't do anything in it's base. Since [Map Editor](/Map-Editor) is from vanilla times it supports only original factions. If your AI is Seraphim, you will have to edit **save.lua** file, open it and find Seraphim army and change the value.
```lua
faction = 3,
```
**If the faction isn't set correctly, the AI won't build any units!!**

### AI Plan

The last thing that needs to be changed is the AI Plan. Since we script our AI using functions from Forged Alliance we need to set it to no plan. We can't do this directly in [Map Editor](/Map-Editor) so we need to edit our **save.lua** file again. Do this for every army you have.
```lua
plans = '/lua/ai/opai/defaultblankplanlist.lua',
```
## Script

This part will take most of the time to create. Script file is in control of everything. Here we will import other files we will use, set how the mission will start, end and everything what will happen in between. As an example we will use **Prothyon16_script.lua**. Open that file while reading this tutorial because there won't be every line in this tutorial. I'm going to highlight only the most important parts of it.

First thing to do is import other files. That will be at the very beginning of **script**. We can add these files as we're adding new functions to our script. Basic ones that we will surely use are: 
```lua
local Objectives = import('/lua/ScenarioFramework.lua').Objectives
local ScenarioFramework = import('/lua/ScenarioFramework.lua')
local ScenarioPlatoonAI = import('/lua/ScenarioPlatoonAI.lua')
local ScenarioUtils = import('/lua/sim/ScenarioUtilities.lua')
local Utilities = import('/lua/utilities.lua')
```
Other files to import are AI files, Voice overs and if we use more function, we add those files later.

We can also set up variables that will be accessible anywhere in the script. For example for debugging cinematics.

- **local SkipNIS1 = false** - if set to **true** it will allow us to skip cinematics mission intro if we have one.
	- You can set one for all cinematics or one for each, which is recommended.

Other variables that you can see in the vanilla mission sctips are usually for objectives and attack triggers. They can be set at the beginning of the script or right away when adding the objective or script. It's up to you what you what you prefer. I followed the format of FA missions where it's set directly.

### Start up
Beginning of the mission is handled by two functions, they are called by the game engine. One will spawn all the initial units (**OnPopulate**), second one will take care of everything else **OnStart**).

First one is caller **OnPopulate**.
```lua
function OnPopulate(scenario)
    -- body
end
```
- **ScenarioUtils.InitializeScenarioArmies()** - Calls for **InitializeScenarioArmies** function from ScenarioUtils file that we imported at the beginning.
	- This functions initialize data for all armies that are in the game (UEF, Player1, etc..).

#### Army Colors

There are two ways to set color. We can choose from preset colors that are defines in **ScenarioFramework** or pick our own color by using [RGB Color Code](http://www.rapidtables.com/web/color/RGB_Color.htm). We need to choose army that we're setting color to as we defined them at the beginnig of script
```lua
ScenarioFramework.SetUEFAllyColor(UEF)
SetArmyColor('UEFAlly', 71, 134, 226)
```
![capture.png](/images/mapping/capture.png)

Easy way of setting custom colors for all coop players:
```lua
local colors = {
    ['Player2'] = {255, 200, 0}, 
    ['Player3'] = {189, 116, 16}, 
    ['Player4'] = {89, 133, 39}
}
local tblArmy = ListArmies()
for army, color in colors do
   if tblArmy[ScenarioInfo[army]] then
       ScenarioFramework.SetArmyColor(ScenarioInfo[army], unpack(color))
   end
end
```

#### Unit Cap
Army unit capacity can be changed using the **SetArmyUnitCap** function, we need to specify the army and the value that we want it to be. Example:
```lua
SetArmyUnitCap(UEF, 1000)
```
- Sets 1000 unit cap for UEF army, do so for all armies you want.
	- This can be adjusted during the mission, just set new value and it will override the previous one.

The easy way to restrict unit capacity for players is to use the **SetSharedUnitCap** function, it will divide the number among the current human players.
```lua
ScenarioFramework.SetSharedUnitCap(1000)
```
- This will set the unit cap to 1000 if the player is playing alone, 500 for each if there are two players, etc...

#### Spawning Units and Bases
There are several functions to spawn units. We can either spawn only one unit specified in editor/save file or whole group. Depending on chosen function we can just spawn them, spawn as wreckage, add veterancy level, etc...

This is an example of basic function to spawn unit group
```lua
ScenarioUtils.CreateArmyGroup('Player1', 'Starting Base')
```
- Spawns unit group named in editor **Starting Base** for **Player1** army
	- Use this function to spawn any group of units you prepared in editor.

This code will create specific unit from editor and also allow us to work with it, in this case set it so it can't be reclaimed. If we would add parameter **true** in the function, our group would get spawned as wreckage.
```lua
ScenarioInfo.Gate = ScenarioUtils.CreateArmyUnit('Player1', 'Gate')
ScenarioInfo.Gate:SetReclaimable(false)
```
If we just want to spawn a unit(s) we call the function we want. If we need to give some orders or change atributes of the unit we need to set a variable, either local or global. Example of local variable can be seen few lines above when spawning a patrol. Local variable means that we can work with it only in current function (OnPopulate). Global variable can be used anywhere in the script and also in other lua files. Example of global variable is above when spawning the Gate.

##### More information about unit spawning
AI uses platoons to control units. When AI builds units from factories, it will form a platoon out of them and then give order to the platoon. This way it keeps track on what units already have orders and what units are free to be used. We need to keep this in mind when spawning units. With the 4 most common ways:
```lua
ScenarioUtils.CreateArmyUnit()
ScenarioUtils.CreateArmyGroup()
ScenarioUtils.CreateArmyGroupAsPlatoon()
ScenarioUtils.CreateArmyGroupAsPlatoonVeteran()
```
- **CreateArmyUnit** - spawns a single unit
- **CreateArmyGroup** - spawns a group
- **CreateArmyGroupAsPlatoon()** - spawns a group, assigns all the units into a platoon
	- Requires one more parametr than **CreateArmyGroup** and it is a formation. Most common formation types are **'AttackFormation**', **'GrowthFormation**' and **'NoFormation**'.
	- CreateArmyGroupAsPlatoon will make sure that AI base will not try to use the units we spawned when forming new platoons out of  built units. The AI looks at all units in radius of the base and it doesn't matter if it's a unit that just came out of factory or it's a unit we spawned at the edge of the base. As long as it's not in a platoon AI can use it. So if you're spawning units next to the AI bases, and the base is set to build same type of units, spawn the group of units as a platoon, or assign the single unit to the platoon. You can fing an example of how to assign a unit spawned via **CreateArmyUnit** into a platoon in the **IntroMission2()** function (spawning engineers for reclaiming).
- **CreateArmyGroupAsPlatoonVeteran()** - works similar as above, it just needs one more parametr with veterancy level which should be set on the units. Number 1-5.

For detailed description of spawn fucntions, look in **ScenarioUtilities**

`Supreme Commander - Forged Alliance\gamedata\mohodata.scd\lua\sim\ScenarioUtilities.lua`

##### Initial Patrols
You can add initial patrols that don't count into attack platoons you have ready in your AI file.
```lua
local units = ScenarioUtils.CreateArmyGroupAsPlatoon('UEF', 'EastBaseAirDef', 'GrowthFormation')
   for k, v in units:GetPlatoonUnits() do
       ScenarioFramework.GroupPatrolRoute({v}, ScenarioPlatoonAI.GetRandomPatrolRoute(ScenarioUtils.ChainToPositions('M1_East_Base_Air_Defence_Chain')))
   end
```
- **local units** - Sets the variable units
	- First group needs to be **local units =**, other groups can only **units =**
- **CreateArmyGroupAsPlatoon** - spawn this group. 
	- **'UEF**' - army this group belongs to.
	- **'EastBaseAirDef**' - Name of the group as it is in Map Editor/save.lua file
	- **'GrowthFormation**' - formation this group will use. Other option is **AttackFormation** and **NoFormation**
- Next part gives command to this group to patrol using **'M1_East_Base_Air_Defence_Chain**' specified in editor/save.lua file.
	- **ScenarioFramework.GroupPatrolRoute** and **ScenarioPlatoonAI.GetRandomPatrolRoute** - for air units using random patrol route.
	- **ScenarioFramework.GroupPatrolChain** - for land units 
	- Pay attention to this, one is **Route**, other one is **Chain**, it's easy to do mistake while copy pasting this.

##### Most common usage of patrols
These are the 3 most common ways of setting up a unit patrol. I will show it on the same example group.

First one will put the platoon on the patrol in a formation. The platoon will follow the chain as it's set in the map editor.
```lua
local platoon = ScenarioUtils.CreateArmyGroupAsPlatoon('UEF', 'M1_Patrol_Group', 'AttackFormation')
ScenarioFramework.PlatoonPatrolChain(platoon, 'M1_UEF_Base_Patrol_Chain')
```
Second example will put each unit of the platoon on the patrol. Each unit will recieve it's own order.
-  Note that the formation won't have any effect here since each unit will recieve individual order so we could as well go with **'NoFormation**' if we wanted. But we have to set some formation into the function since parametr with formation is mandatory.
```lua
local platoon = ScenarioUtils.CreateArmyGroupAsPlatoon('UEF', 'M1_LandPatrol', 'AttackFormation')
for _, unit in platoon:GetPlatoonUnits() do
    ScenarioFramework.GroupPatrolChain({unit}, 'M1_UEF_Base_Patrol_Chain')
end
```
Last one will put each unit of the platoon on it's own randomly generated patrol. It will use markers from the chain we specify. This one is mostly used for air patrols over bases. The same as in the example above applies to the formation.
```lua
local units = ScenarioUtils.CreateArmyGroupAsPlatoon('UEF', 'M1_Patrol_Group', 'AttackFormation')
   for k, v in units:GetPlatoonUnits() do
       ScenarioFramework.GroupPatrolRoute({v}, ScenarioPlatoonAI.GetRandomPatrolRoute(ScenarioUtils.ChainToPositions('M1_UEF_Base_Patrol_Chain')))
   end
```
Unit's don't need to just patrol, you can also set move, attack move commands. It can be combined as well. Typical example where you would want to give more than one type of a command is when you have bases on the islands and you want to send some experimental unit on attack. If you put it just on patrol you might end up with unit staying close to shore, still under water and trying to attack on it's maximum gun range. It can't shoot because it's still under water so it will stay there forever.

To go around this you set up a chain that ends at the island and second chain that is on the island. First you put the unit on move using the first chain and then you set either patrol or attack move on the second chain.

This doesn't need to be used just for experimentals but for any group of unit that you first want to arrive somewhere and not attak everyone on the way there.

#### Setting up AI

If we've already [created AI](/Mission-Scripting#creating-ai), now is the time to activate it for the first mission. We need to import it's file at the beginning of the script,
```lua
local M1UEFAI = import('/maps/Prothyon16_DEMO/Prothyon16_DEMO_m1uefai.lua')
```
so we can call for functions that will activate it, there are two main bases in Prothyon - 16 DEMO, therefore two functions:
```lua
M1UEFAI.UEFM1WestBaseAI()
M1UEFAI.UEFM1EastBaseAI()
```
We can also add some starting recources to AI by using this code:
```lua
ArmyBrains[UEF]:GiveResource('MASS', 4000)
ArmyBrains[UEF]:GiveResource('ENERGY', 6000)
```
#### Cheat Economy/Build power

AI that is used in missions has already set buff for build power. It was 2x more build power on factories and 3x more build power on engineers. This is causing AI to use much more resources. Good way how to add more resources to AI the code below that allow are to multiply mass and energy income as much as we want. It can be set for every AI differently and changed during mission. You can ask why should be AI allowed to have more economy than player? The answer is simple, AI can't use resources efficiently so it needs to have more than player to be able to give a challenge. As you will learn in [Creating AI](/Mission-Scripting#creating-ai) part, everything AI builds are just scripted, predefined attacks, using marker chains we defined. AI can react to certain situations we add, but it will never be as good as player.

In order to use this buff we need to import file with buff definitions at the beginning of the script
```lua
local Buff = import('/lua/sim/Buff.lua')
```
This code will allow us to change multipliers to economy income. We just need to set our values and specify army that will be affected.
```lua
buffDef = Buffs['CheatIncome']
   buffAffects = buffDef.Affects
   buffAffects.EnergyProduction.Mult = 1
   buffAffects.MassProduction.Mult = 1.5

       for _, u in GetArmyBrain(UEF):GetPlatoonUniquelyNamed('ArmyPool'):GetPlatoonUnits() do
               Buff.ApplyBuff(u, 'CheatIncome')
       end
```
For changing values later in the mission or setting them for another army we need to use only this part:
```lua
buffAffects.EnergyProduction.Mult = 1
buffAffects.MassProduction.Mult = 1.8

for _, u in GetArmyBrain(UEF):GetPlatoonUniquelyNamed('ArmyPool'):GetPlatoonUnits() do
    Buff.ApplyBuff(u, 'CheatIncome')
end
```
- GPG used code that was giving resources to AI every few second, which was basically infinite eco and killing economy structures of AI didnt have too much of an effect. With the code above, this problem is removed.

------------------------------------------------------------------------
Second function we will use on start up is OnStart funciton
```lua
function OnStart(scenario)
    -- body
end
```
#### Restrictions
The function for restricting units looks like this
```lua
ScenarioFramework.AddRestriction(army, categories.TECH2 + categories.TECH3 + categories.EXPERIMENTAL)
```
- **army** - Army that will be restricted.
- **categories.TECH2** - Units we are restricting.
- Check the [list of all categories](/Mission-Scripting#categories).
	- We can restrict whole unit groups that has something in common using one of these categories or specific units, using unit IDs
- Using this code you can restrict units for AI as well
	- Usually you don't need to put restrictions to AI since it builds only units you specify, but it is usefull if you don't want AI to build lower tech engineers for example.
- Similar code is used for removing restrictions, only thing that will change is **AddRestriction** to **RemoveRestriction**
	- This can be used anywhere duting the mission, usually as a result of some objective or when starting another objective.

For restricting the same units for all players, you can use this function
```lua
ScenarioFramework.AddRestrictionForAllHumans(categories.TECH2)
```
- It doesn't need the parameter **army** since it takes the armies from the **ScenarioInfo.HumanPlayers** table.
- And for removing the restrictions
```lua
ScenarioFramework.RemoveRestrictionForAllHumans(categories.TECH2)
```
To restrict ACU upgrades there is this function:
```lua
ScenarioFramework.RestrictEnhancements({})
```
- It's a table with all upgrades we want to restrict. [Full list here](/Mission-Scripting#enhancements).
- To unlock ACU upgrades, set new restriction without those upgrades that you want to allow.

#### Other Things

We can set here camera angle so it doesn't start all the way zoomed out, revealing how the whole map looks.
```lua
Cinematics.CameraMoveToMarker('Cam_1_1', 0)
```
- For this to work we need to import Cinematics file, more info in [Cinematic Intro](/Mission-Scripting#cinematic-intro)

Last thing to do is to set which function will follow, if we didn't spawn ACU yet, we can do it during cinematics or after first objective is assigned. In our example next function is **IntroMission1NIS**. But before we get there we need to set what will happen at the end of the game.

### End Game
The classic case is that the mission can end in 3 ways. Either player wins, dies or loses (this means failing a primary objective). You can set different ending depending on what objectives were or were not finished or failed. 

We'll start with the simpliest one.

#### Death

There is simple function to handle this situation as we usually want to do the same thing. Zoom on the dying ACU, play some dialogue "informing" player about his death and end the mission. For all this to happen you will need a new function in your script. Usually it's named **PlayerDeath**
```lua
function PlayerDeath(commander)
    ScenarioFramework.PlayerDeath(commander, OpStrings.PlayerDies1)
end
```
- **PlayerDeath** - the name of our function in the script file. 
- It calls a function from **ScenarioFramework** with a same name using 2 parameters.
	- **commander** - the unit that is dying, it uses it's position to rotate the camera around it.
	- **OpStrings.PlayerDies1** - the dialogue that will be played.
- For this to work you also need to set this function to be called when the ACU dies, you can do that when [spawning the ACU](/Mission-Scripting#spawning-acus)

Everything else is handeled by the funcion and after the dialogues finished it will show the "Operation Failed" pop up to quit.

#### Loss

#### Win

This part can be as complicated as you want. You can include several camera movements, showing different part of the maps with different units or anything that comes to your mind to end the mission in a nice way.

The minimum is two functions, **PlayerWin** and **KillGame**
```lua
function PlayerWin()
    if not ScenarioInfo.OpEnded then
        ScenarioFramework.EndOperationSafety()

        ScenarioInfo.OpComplete = true

        ScenarioFramework.Dialogue(OpStrings.PlayerWins, KillGame, true)
    end
end
function KillGame()
    local bonus = Objectives.IsComplete(ScenarioInfo.M1B1Objective) and Objectives.IsComplete(ScenarioInfo.M1B2Objective) and Objectives.IsComplete(ScenarioInfo.M2B2Objective)
    local secondary = Objectives.IsComplete(ScenarioInfo.M1S1Objective) and Objectives.IsComplete(ScenarioInfo.M2S1Objective) and Objectives.IsComplete(ScenarioInfo.M3S1Objective)
    ScenarioFramework.EndOperation(ScenarioInfo.OpComplete, ScenarioInfo.OpComplete, secondary, bonus)
end
```
What this does is that first it checks if the mission hasn't ended yet, for example finishing the final objective right after you get killed or any other unlikely but possible case. **ScenarioInfo.OpEnded** is variable set inside **ScenarioFramework.EndOperationSafety** function. Now what this fucntion does, it sets alliances between armies to neutral, so there is no more shooting, it also sets the player's ACU unkillable. Next thing is to set variable **ScenarioInfo.OpComplete**, this is used in the **KillGame** function. Last part is to play the winning dialogue which is set to call the **KillGame** function after it's done.

The final function that has to be called to end the mission and show the "Operation Complete" window is **ScenarioFramework.EndOperation**. As you can see it can take up to 4 parameters, first 2 are minimum. All of them are true/false. First one is if the operation was succesful. Inside **ScenarioInfo.OpComplete** variable we saved true in the previous function. You can see it's used as the second parameter as well since that is if all primary objective are completed. When player wins it means that they are so there is no need for other check. Third and fourth parameters are for secondary and bonus objectives. To find out if all objevtives of a type are completed we need to check them all. 

### Cinematic Intro

Cinematics are usually used as intro to main objectives, but it can be used anywhere. First thing to do is to import file with their functions we will use. As with every file importing, put it at the beginning of the script.
```lua
local Cinematics = import('/lua/cinematics.lua')
```
If we haven't set playable area yet, now is the time to do so.
```lua
ScenarioFramework.SetPlayableArea('M1_Area', false)
```
- **'M1_Area**' - Name of our area as it's set in Map Editor.
- Second value **false/true** can play **'Operation Area Expanded**' voice. Set to true if you want this.

#### Camera Info Markers

Setting camera angle is happening in [map editor](/Map-Editor).
- Select Markers layer and place **Camera Info Marker** anywhere on the map.
- Rotate view by holding **ALT + Middle Mouse Button**
- Once you have angle ready, right click on the **Camera Info Marker** in the markers list and select **Set Orientation**
- Rename your marker so it's easier to use in script.
- Place as many of those markers as you want. In script you will be setting how fast will the camera be moving through them.

#### Setting up Cinematics

At the beginning we prepared variable to skip this upcoming cinematics. Now it's time to set it. Beacuse we will be spawning ACUs during cinematics, we need to set it twice, once with camera movent in first part, then just the ACU spawning in second part.
```lua
if not SkipNIS1 then
    -- First part, everything that will happen during cinematics
else
    -- Second Part, everything that will happen if we're skipping cinematics
end
```
First we need to enter Cinematic mode
```lua
Cinematics.EnterNISMode()
```
We can set several visual markers to get Vision on area we're looking. Any **Blank Marker** can be used for this. But it's recommended to create a new one.
```lua
local VisMarker1_1 = ScenarioFramework.CreateVisibleAreaLocation(30, 'M1_Vis_1_1', 0, ArmyBrains[Player1])
```
- **30** - vision radius
- **'M1_Vis_1_1**' - name of out marker
- **0** - how long to provide vision in seconds
	- **0** = infinite time
- **ArmyBrains\[Player1\]** - army that will get vision over this marker

After camera moves away from these markers, we can destroy them by using this code:
```lua
ForkThread(
    function()
          WaitSeconds(2)
          VisMarker1_1:Destroy()
          WaitSeconds(2)
          ScenarioFramework.ClearIntel(ScenarioUtils.MarkerToPosition('M1_Vis_1_1'), 40)
     end
)
```
- You can additionslly clear intel that was given from these markers to force player to send scouts.
	- **ScenarioUtils.MarkerToPosition('M1_Vis_1_1')** - Marker to clear intel around.
	- **40** - radius, should be bigger by 10 than was the radius of vision marker to be sure no intel will left.

If we have Camera Info Markers ready from Editor, we can use them now.
It's handles by one function:
```lua
Cinematics.CameraMoveToMarker(ScenarioUtils.GetMarker('Cam_1_2'), 15)
```
- **'Cam_1_2**' - Marker to move camera to.
- **15** - Travel time to this marker in seconds.
- [Voice Overs](/Mission-Scripting#voice-overs) can be placed here.

After the last Camero Info marker we need to leave cinematics:
```lua
Cinematics.ExitNISMode()
```
#### Spawning ACUs

There is a function in called **SpawnCommander** in **ScenarioFramework.lua** for easy ACU spawning. It's good to put the ACU into global variable **ScenarioInfo** Depending on how he want to ACU to be spawned we will use the parametrs of this function. The function has 7 parametrs.
```lua
SpawnCommander(brain, unit, effect, name, PauseAtDeath, DeathTrigger, enhancements)
```
- **brain** - Army we want the ACU to spawn in (needs to be placed in Map Editor in that army)
- **unit** - Name of the unit in Map Editor
- **effect** - Type of effect we want to use for spawn
	- **'Warp**' - for spawning in the field
	- **'Gate**' - for spawning from Quantuum Gate
	- **false** - no effect
- **name** - Sets the name of the ACU
	- **'Fletcher**' - string with the name, can be inside ' ' or " " symbols
	- **true** - if we pass just true it will automatically pick a name of the army, use this for naming player's ACU
- **PauseAtDeath** - if true if will pause ACU before explosion so camera can catch up
- **DeathTrigger** - Name of the function we want called when ACU is killed
- **enhancements** - table with names of upgrades we want to have ACU spawned with. Find all upgrades [here](/Mission-Scripting#enhancements).

Example from Prothyon - 16:
```lua
ScenarioInfo.PlayerCDR = ScenarioFramework.SpawnCommander('Player', 'Commander', false, true)
```
- Spawn a unit called **'Commander**' from army **'Player**' with no effect and name it (in my case name would be speed2)
```lua
ScenarioInfo.SeraACU = ScenarioFramework.SpawnCommander('Seraphim', 'M5_Sera_ACU', false, 'Zottoo-Zithutin', false, false,
    {'AdvancedEngineering', 'DamageStabilization', 'DamageStabilizationAdvanced', 'RateOfFire})
```
- Spawn a unit called **'M5_Sera_ACU**' from army **'Seraphim**' with no effect, name it **'Zottoo-Zithutin**', does not pause explosion, no trigger when destroyed, adds all the upgrades that are in the table.

For spawning all coop ACUs at once we can use this for example. It's up to you if you want to set death trigger also on Coop ACU's.
```lua
ScenarioInfo.CoopCDR = {}
local tblArmy = ListArmies()
coop = 1
for iArmy, strArmy in pairs(tblArmy) do
    if iArmy >= ScenarioInfo.Coop1 then
        ScenarioInfo.CoopCDR[coop] = ScenarioFramework.SpawnCommander(strArmy, 'Commander', Warp', true)
        coop = coop + 1
        WaitSeconds(0.5)
    end
end
```
Spawning Coop ACUs is slightly different in Prothyon since they get loaded onto transport and moved to the starting position. You can do different things with ACU spawning. All ACUs don't need to be spawned at the same time. You don't even need to give an ACU to the player, it can  be a sACU, an enginner or just few combat units. Keep in mind that missions run in 'Sandbox' so it's just up to you how you design your mission.

Now let's get back to the Prothyon - 16. We are inside IntroMissionNIS() function and now we have to specify what will happen next, at the last line we call this function:
```lua
IntroMission1()
```
### Mission Objective

Before we get to first objective there is one more function in which we'll set mission number.
```lua
function IntroMission1()
    ScenarioInfo.MissionNumber = 1

    StartMission1()
end
```
#### Objective types

There are several objective types, each require different target data to work.
- Kill
- Capture
- KillOrCapture
- Reclaim
- Locate
- SpecificUnitsInArea
- CategoriesInArea
- Protect
- Timer
- Camera

Basic data every objective needs:
```lua
ScenarioInfo.Name = Objectives.Type(
    'primary',
    'incomplete',
    'Title',
    'Description',
    'Action',
    {target
    }
)
```
- **Name** - Name of our objective for script. M1P1 for Mission 1 Primary 1 etc...
- **Objectives.Type** - Now we choose type of the objective
- **'primary**' - Objective priority. Others are **secondary, bonus**.
- **'incomplete**' - Objective isn't completed yet. Other is **complete**.
- **'Title**' and **'Description**' - Will be shown with objective on UI.
- **'Action**' - This is required by only some objective types. Others can't have it.
- Last one is table with target. There are several data that can be here depending on objective type
```lua
FlashVisible = true,
AlwaysVisible = true,
MarkUnits = true,
MarkArea = true,
ShowProgress = true,
PercentProgress = true,
ShowFaction = 'Faction',
NumRequired = 'Number',

Units = {},
Area = 'Area',
Requirements = {
    {Area = 'Area', Category = categories.type, CompareOp = '', Value = Number, ArmyIndex = Army},
},
Category = categories.UnitID,

Timer = Number, -- if nil, requires a manual update for completion
ExpireResult = 'complete',
```
- **FlashVisible** - Intel flash over a target to show it on the map.
- **AlwaysVisible** - Constant vision on the target.
- **MarkUnits** - Highlights target units on the map.
- **MarkArea** - Highlighs target area on the map.
- **ShowProgress** - Shows progress of the objective. (2/8, etc...)
- **PercentProgress** - Shows progress of the objective in percents.
- **ShowFaction** - Icon of objective is defined by units that are targeted, this over rides it and whows faction icon instead.
- **NumRequired** - How many units are required to complete objective, usually used with **Capture**
- **Units** - Table with target units
- **Area** - Name of the area as we named it in Map Editor/save.lua file.
- **Requirements** - Used for **CategoriesInArea** objective type.
	- **Area** - Name of the area as we named it in Map Editor/save.lua file.
	- **Category** - Unit categories, it can be one of [these](/Mission-Scripting#categories) or unit IDs.
	- **CompareOp** - Options are: **'\<=', '>=', '\<', '>', '==**'
		- **==** - is checked only once per 5 ticks.
		- **Value** - Number we require.
		- **ArmyIndex** - Army we defined at the beginning of script.
- **Category** - Forces icon of this unit.
- **Timer** - Number in seconds.
- **ExpireResult** - What happens when time runs up. Options are: **complete, failed**

Detailed description is in SimObjectives file

`Supreme Commander - Forged Alliance\gamedata\lua.scd\lua\SimObjectives.lua`

Now we will set up our first objective:
```lua
ScenarioInfo.M1P1 = Objectives.CategoriesInArea(
    'primary',                      -- type
    'incomplete',                   -- complete
    'Destroy UEF Forward Bases',    -- title
    'Eliminate the marked UEF structures to establish a foothold on the main island.',  -- description
    'kill',                         -- action
    {                               -- target
        MarkUnits = true,
        Requirements = {
            {   
                Area = 'M1_UEF_WestBase_Area',
                Category = categories.FACTORY,
                CompareOp = '<=',
                Value = 0,
                ArmyIndex = UEF,
            },
        },
    }
)
```
Then we set what will happen when objective is complete. In our example we will move to another mission.
```lua
ScenarioInfo.M1P1:AddResultCallback(
    function(result)
        if(result) then
            ScenarioFramework.Dialogue(OpStrings.BeachBaseDestroyed, IntroMission2, true)
        end
    end
)
```
- [Voice over](/Mission-Scripting#voice-overs) that will tell us we finished objective and move us to another mission.

### Player's Choice

This part is very important when you're designing your mission. It brings on option of non-linear story where player can decide what will happen. It can even lead to different endings, if you want to.

You can make a pop up dialogue and offers choices to the player. It looks similar to the pop-up you get when you want to exis and it asks you if you are sure. To get this into you mission you need just few simple lines. Random example of use:
```lua
local dialogue = CreateDialogue('Who do you want to help?', {'Rhiza', 'Fletcher'})
dialogue.OnButtonPressed = function(self, info)
    dialogue:Destroy()
    if info.buttonID == 1 then
        AllyWithRhiza()
    elseif info.buttonID == 2 then
        AllyWithFletcher()
    end
end
```
- **local dialogue** - in local variable **dialogue** we store the table that is returned by **CreateDialogue** function
- **CreateDialogue** function works with 3 parametrs
	- **title** - Text to be displayed
	- **tblButtons** - table of strings, one for each button
	- **position** - string, it is either **'left**', **'right**' or by default it's in the center of the screen

Pressing any of the buttons calls **OnButtonPressed** funtion of the dialogue, but we need to adjust this function for our needs. That is what the rest of the code does. For each button we need to create **if**/**elseif**' statement with **info.buttonID == number** as a
condition where **number** is an ID of the button. As you can expect it's in the order as you put the options into the table.

- **dialogue:Destroy()** makes the window with a dialogue disappear from the screen when we press any button.

## Creating AI

Campaign AI is different from skirmish AI. Everything that AI will do is scripted, from base design, expantions to every attack platoon. Each army AI has it's own file for every mission unless it survives to another mission. In that case, platoons will get different orders in
each mission.

### Things to do in Map Editor

We need to use [Map Editor](/Map-Editor) to design base and set up markers and chains AI will use. Lets start with base template

#### Base template

Go to **Armies** tab. Create new unit group in your army. It's better to have several subgroups so you always find the right one fast.
- Enable **View - Debug - Skirts** to see how much space buildings take.
- For building placement use also **Options - AutoSnap to o-grid**. You need to 'shake' every building you place to be properly alligned in the grid.

With group selected, right click on map and add structures.
- Units can be copy pasted
- Make sure that buildings and units are in the right group.
- Units can be rotated by holding **R** key and moving cursor.
- Building can be rotated only by setting **Abs Yaw** in Armies tab. (0-360)
- Units are grouped by their ID's

<table>
<tbody>
<tr class="odd">
<td><p><strong>First letter indicates unit pack</strong></p>
<dl>
<dt></dt>
<dd><dl>
<dt></dt>
<dd>
</dd>
</dl>
</dd>
</dl></td>
<td><p><strong>Second letter is faction</strong></p>
<dl>
<dt></dt>
<dd><dl>
<dt></dt>
<dd>
</dd>
</dl>
</dd>
</dl></td>
<td><p><strong>Third letter for type</strong></p>
<dl>
<dt></dt>
<dd><dl>
<dt></dt>
<dd>
</dd>
</dl>
</dd>
</dl></td>
<td><p><strong>First number for general role</strong></p>
<dl>
<dt></dt>
<dd><dl>
<dt></dt>
<dd>
</dd>
</dl>
</dd>
</dl></td>
<td><p><strong>Second number for tech level</strong></p>
<dl>
<dt></dt>
<dd><dl>
<dt></dt>
<dd>
</dd>
</dl>
</dd>
</dl></td>
<td><p><strong>Third/Fourth number for individual unit</strong></p>
<dl>
<dt></dt>
<dd><dl>
<dt></dt>
<dd>
</dd>
</dl>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p><strong>d</strong></p>
<dl>
<dt></dt>
<dd>
</dd>
</dl></td>
<td><p>Units added in one of the Supreme Commander patches</p></td>
<td><p><strong>a</strong></p>
<dl>
<dt></dt>
<dd>
</dd>
</dl></td>
<td><p><img src="/images/mapping/aeon.png" title="fig:Aeon.png" width="20" alt="Aeon.png" /> Aeon</p></td>
<td><p><strong>a</strong></p>
<dl>
<dt></dt>
<dd>
</dd>
</dl></td>
<td><p>Air</p></td>
</tr>
<tr class="odd">
<td><p><strong>o</strong></p></td>
<td><p>Units for objectives in Supreme Commancder</p></td>
<td><p><strong>e</strong></p></td>
<td><p><img src="/images/mapping/uef.png" title="fig:Uef.png" width="20" alt="Uef.png" /> UEF</p></td>
<td><p><strong>b</strong></p></td>
<td><p>Base</p></td>
</tr>
<tr class="even">
<td><p><strong>u</strong></p></td>
<td><p>Units from Supreme Commancder</p></td>
<td><p><strong>r</strong></p></td>
<td><p><img src="/images/mapping/cybran.png" title="fig:Cybran.png" width="20" alt="Cybran.png" /> Cybran</p></td>
<td><p><strong>c</strong></p></td>
<td><p>Civilian</p></td>
</tr>
<tr class="odd">
<td><p><strong>x</strong></p></td>
<td><p>Units added in Forged Alliance</p></td>
<td><p><strong>s</strong></p></td>
<td><p><img src="/images/mapping/map-script/seraphim.png" title="fig:Seraphim.png" width="20" alt="Seraphim.png" /> Seraphim</p></td>
<td><p><strong>l</strong></p></td>
<td><p>Land</p></td>
</tr>
<tr class="even">
<td><p><strong>z</strong></p></td>
<td><p>Units added in FAF</p></td>
<td></td>
<td><p><strong>o</strong></p></td>
<td><p>Operation</p></td>
<td><p><em>There are <strong>many</strong> exceptions to this rule.</em></p></td>
</tr>
<tr class="odd">
<td></td>
<td><p><strong>s</strong></p></td>
<td><p>Naval</p></td>
<td></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>

#### Markers and Chains
![untitled-2.png](/images/mapping/map-script/untitled-2.png){.align-right}Each base requires two markers to work and a lot more for sending units. There are two marker types we are going to use. **Rally Point** and **Blank Marker**.

##### Base Marker

First thing to to is to set up **Base Marker** around which the base will be defined.
- AI will use factories and units only in radius around this marker
- Go to **Markers** layer and place **Blank Marker** in the middle of your base.
	- It's highly recommended to rename your markers to keep track on them. In our case: **M1_West_Base_Marker**.
	- Radius of base markers **should not be overlapping!**

##### Rally Point

Another one is **Rally Point**.
- You can put different rally points for each factory types.
- **Rally Point** marker needs to be in **Base Marker** radius
	- If you have platoon of many units and some of them will get outside of the **Base Marker** while waiting on the **Rally Point**, these units won't be sent by AI on attack and will stay on that place untill they are destroyed.
- For naval factories use **Naval Rally Point**

##### Marker Chains
Next step is set up all kinds of chains for units. Click on **Chains** tab and create a new chain ![new_map_icon.png](/images/mapping/map-script/new_map_icon.png). While having this chain selected, put Blank Markers on the map and they will create a chain. You can also add existing marker to chain by clicking on ![markertochain.png](/images/mapping/map-script/markertochain.png) . marker can be also deleted from chain, but **save your map first before doing so, editor might sometimes crash during it!**
- Set up as many chains as you want, with more chains AI will be harder to predict where it'll send units.
- Don't forget to rename your chains, that can be done by double clicking on chain name. Markers can be renamed only in **Markers** tab.
- First marker of the chain should be relatively close to rally point. It's not necessary but without that AI won't stop to attack enemy units if set on patrol and just go to first marker.
- Markers in chain for land and naval attacks should not be too close together, since units are moving in formation and they tend to regroup at every marker.
- You can make a chain called **'BaseName_EngineerChain**' where **BaseName** is name of your base. This chain will be used by engineers for patrolling if they have nothing to build or assist.  Example: **'M1_WestLand_Base_EngineerChain**'

Once you have your base and markers ready, we can move to next part which will be putting the code together.

### Creating AI lua file

We need to create new lua file. Name this file same as your folder name plus specific name for this file. It's good to follow some simple format to know what this file is on the first sight. For example:

`Prothyon16_m1uefai.lua`
- **m1** - First mission.
- **uef** - Army the AI belongs to.
- **ai** - So we know its file for AI.

At the beginning of this file we will import other lua files.

This one will manage our base. Build and rebuild buildings, assembly attack platoons and send then on the field.
```lua
local BaseManager = import('/lua/ai/opai/basemanager.lua')
```
We will use functions from this file to give out platoons orders. Attack, patrol etc...
```lua
local SPAIFileName = '/lua/scenarioplatoonai.lua'
```
Next step is setting locals, here we will give index to our army, it's the same number as in the script file.
```lua
local UEF = 2
```
Now we will create base managers to all of our bases. Every base needs i t's own base manager. In Prothyon there are two bases in first part ofthe mission. The name of base managers doesn't matter but it's better to stick to one format. I'm using similar name format as in FA missions.
- **UEF** - Faction of the base
- **M1** - Mission number
- **Westbase** - Name of the base
- **BaseManager.CreateBaseManager()** - will call ***CreateBaseManager()*** function from file we imported at the beginning. It set's up basic functions that the base will use.
```lua
local UEFM1WestBase = BaseManager.CreateBaseManager()
local UEFM1EastBase = BaseManager.CreateBaseManager()
```
#### Base

Next step is to set up specific base. This function will be called from out script file.
```lua
function UEFM1WestBaseAI()
   UEFM1WestBase:Initialize(ArmyBrains[UEF], 'M1_WestLand_Base', 'M1_West_Base_Marker', 40, {M1_WestBase = 100})
   UEFM1WestBase:StartNonZeroBase(``)
   UEFM1WestBase:SetActive('AirScouting', true)
   UEFM1WestBase:SetActive('LandScouting', true)

   UEFM1WestBase:AddBuildGroup('M1_WestBaseExtended', 90, false)

   UEFM1WestBaseAirAttacks()
   UEFM1WestBaseLandAttacks()
end
```
- For each base we need to set several values.
- First line initializes our base
	- **ArmyBrains\[UEF\]** - Army that will control this base
	- **'M1_WestLand_Base**' - Name of out base, it can be whatever.
	- **'M1_West_Base_Marker**' - Marker in save file. AI will use  only factories, and send units, that are around this marker in radius we set as next.
	- **40** - Radius around our marker in game units.
		- Radius of base markers **should not be overlapping!**
		- **{M1_WestBase = 100}** - Name of unit group as we wrote in [Map Editor](/Map-Editor) / save.lua file and priority AI will rebuild buildings with.
- Second line starts the base
	- **StartNonZeroBase** - Means that base will spawn, all units that are in ***M1_WestBase*** group. 
		- **StarEmptyBase** - If you want this base to be build later by other base manager.
		- **()** - Two tables with 3 numbers in it. First table is for total engineer count in the base. It's in a table because we want different engineer count for different difficulties. Second table is for engineers that are permanently assisting factories, again differs by difficulty.
		- If we use just one table, it will set up just total engineer count in the base, with no engineers permanently assisting factories, depending on difficulty.
		- If we put there single number without a table. It will set up same engineer count no matter the difficulty.
- Next 3 lines will activates some base functionality that are  disabled by default.
- This base was designed so only bigger part of it is spawned *(M1_WestBase)* and rest is build during missions.
		- **AddBuildGroup** - adds group created in map editor to base manager
			- **'M1_WestBaseExtended**' - Name of the group as it is in [Map Editor](/Map-Editor) / save.lua file.
			- **90** - priority
			- **false** - This means that the group will not be spawned at the beginning. Use ***true*** if you want this group spawned from the beginnig.
- Last lines are for functions that will assembly attacks.
	- **UEFM1WestBaseAirAttacks()** - All air attacks in that will be build in  this base.
	- All attacks could be in one function but that would be terrible mess and it would be really hard to find specific attack for you and everyone else who would be trying to learn from it.
	- You can group your attacks as your want, for example Air, Land, Naval, Drops, etc...

#### Attacks

Now, when we have base working we want to set up attack that will be built and sent from this base. There are two way to set up platoons. We either use already existing platoon from lua files or create completely new one. For basic attacks like, group of tanks or bombers we can use the easy variation and using already created platoon. I didn't manage to get naval platoons working properly so I'm using custom ones.

##### Existing Platoon Templates

Files with templates we can use are located in:

`Supreme Commander - Forged Alliance\gamedata\lua.scd\lua\AI\OpAI`

If we want to used unit types from these files, only thing we need is to set which file to use and child type
- AI will keep this platoon alive, this platoon will be rebuilt once every unit from it is destroyed.

<table>
<thead>
<tr class="header">
<th><p>Available Templates</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><dl>
<dt></dt>
<dd>
</dd>
</dl>
<table>
<thead>
<tr class="header">
<th><p>File</p></th>
<th><p>Child</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>AirAttacks</p></td>
<td><p>Interceptors</p></td>
</tr>
<tr class="even">
<td><p>AirAttacks</p></td>
<td><p>Bombers</p></td>
</tr>
<tr class="odd">
<td><p>AirAttacks</p></td>
<td><p>LightGunships</p></td>
</tr>
<tr class="even">
<td><p>AirAttacks</p></td>
<td><p>Gunships</p></td>
</tr>
<tr class="odd">
<td><p>AirAttacks</p></td>
<td><p>CombatFighters</p></td>
</tr>
<tr class="even">
<td><p>AirAttacks</p></td>
<td><p>TorpedoBombers</p></td>
</tr>
<tr class="odd">
<td><p>AirAttacks</p></td>
<td><p>AirSuperiority</p></td>
</tr>
<tr class="even">
<td><p>AirAttacks</p></td>
<td><p>StratBombers</p></td>
</tr>
<tr class="odd">
<td><p>AirAttacks</p></td>
<td><p>HeavyGunships</p></td>
</tr>
<tr class="even">
<td><p>BasicLandAttack</p></td>
<td><p>LightBots</p></td>
</tr>
<tr class="odd">
<td><p>BasicLandAttack</p></td>
<td><p>LightTanks</p></td>
</tr>
<tr class="even">
<td><p>BasicLandAttack</p></td>
<td><p>LightArtillery</p></td>
</tr>
<tr class="odd">
<td><p>BasicLandAttack</p></td>
<td><p>MobileAntiAir</p></td>
</tr>
<tr class="even">
<td><p>BasicLandAttack</p></td>
<td><p>HeavyTanks</p></td>
</tr>
<tr class="odd">
<td><p>BasicLandAttack</p></td>
<td><p>AmphibiousTanks</p></td>
</tr>
<tr class="even">
<td><p>BasicLandAttack</p></td>
<td><p>MobileBombs</p></td>
</tr>
<tr class="odd">
<td><p>BasicLandAttack</p></td>
<td><p>MobileFlak</p></td>
</tr>
<tr class="even">
<td><p>BasicLandAttack</p></td>
<td><p>MobileMissiles</p></td>
</tr>
<tr class="odd">
<td><p>BasicLandAttack</p></td>
<td><p>MobileShields</p></td>
</tr>
<tr class="even">
<td><p>BasicLandAttack</p></td>
<td><p>MobileStealth</p></td>
</tr>
<tr class="odd">
<td><p>BasicLandAttack</p></td>
<td><p>SiegeBots</p></td>
</tr>
<tr class="even">
<td><p>BasicLandAttack</p></td>
<td><p>HeavyBots</p></td>
</tr>
<tr class="odd">
<td><p>BasicLandAttack</p></td>
<td><p>MobileHeavyArtillery</p></td>
</tr>
<tr class="even">
<td><p>BasicLandAttack</p></td>
<td><p>MobileMissilePlatforms</p></td>
</tr>
<tr class="odd">
<td><p>EngineerAttack</p></td>
<td><p>T1Transports</p></td>
</tr>
<tr class="even">
<td><p>EngineerAttack</p></td>
<td><p>T2Transports</p></td>
</tr>
<tr class="odd">
<td><p>EngineerAttack</p></td>
<td><p>T3Transports</p></td>
</tr>
<tr class="even">
<td><p>EngineerAttack</p></td>
<td><p>T1Engineers</p></td>
</tr>
<tr class="odd">
<td><p>EngineerAttack</p></td>
<td><p>T2Engineers</p></td>
</tr>
<tr class="even">
<td><p>EngineerAttack</p></td>
<td><p>T3Engineers</p></td>
</tr>
</tbody>
</table></td>
</tr>
</tbody>
</table>

There is an example of simple attack. AI will build platoon of 4 bombers and send them on patrol over selected marker chain.
```lua
function UEFM1WestBaseAirAttacks()
   local opai = nil
   local quantity = {}

   -- Builds platoon of 2/3/4 Bombers
   quantity = {2, 3, 4}
   opai = UEFM1WestBase:AddOpAI('AirAttacks', 'M1_WestAirAttack1',
       {
           MasterPlatoonFunction = {SPAIFileName, 'PatrolThread'},
           PlatoonData = {
               PatrolChain = 'M1_Land_Attack_Chain'
           },
           Priority = 100,
       }
   )
   opai:SetChildQuantity('Bombers', quantity[Difficulty])
end
```
- **function UEFM1WestBaseAirAttacks()** - Our function that we're calling from out base.
- **local opai = nil** and **local quantity = {}** - Adds variables to our function. Needs to be set once in each function with platoons.
- Description of our attack, everything after **#** sign will game take as a comment.
- Next several lines are creating the actual attack.
- **opai = UEFM1WestBase:AddOpAI** Creates function for our attack
	- **UEFM1WestBase** - Will define in which base will be this platoon created.
	- **AddOpAI** - calls for the function that creates the platoon
	- **'AirAttacks**' - Name of the file we use to create platoon where the template is stored.
	- **'M1_WestAirAttack1**' - Our name for our platoon. Make sure you don't have two platoons with same name!
	- **MasterPlatoonFunction** - What should this platoon do.
		- **SPAIFileName** - our file with orders we imported at the beginning.
		- **'PatrolThread**' - Function from the file we are going to use.
			- Most of the attacks are set as a patrol.
			- **'PatrolThread**' - Patrol over the defined chain.
			- **'PatrolChainPickerThread**' - Randomly picks one chain from out table of chains.
			- **'RandomDefensePatrolThread**' - Assign random patrol route for each unit from platoon using defined chain.
			- Different functions requires different **PlatoonData**!!! Find all avaiable funcitons and data they need in **ScenarioPlatoonAI.lua**
		- **PlatoonData** - Table with data that our function requires.
			- **PatrolChain = 'M1_Land_Attack_Chain**' - Name of our chain as it is in [Map Editor](/Map-Editor![markertochain.png](/images/mapping/map-script/markertochain.png)) / save.lua file.
			- If we are using ***PatrolChainPickerThread*** function, we need to give more chains in a table.
			- Make sure you change ***PatrolChain***to***PatrolChains***	
		- **Priority = 100** - Platoons with higher priority will be build first, obviously.
- **opai:SetChildQuantity('Bombers', 4)** - Type and number of units we want to be built.
	- There can be more unit types at once.
	- **opai:SetChildQuantity({'Bombers', 'Interceptors'}, 8)** - platoon of 4 Bombers and 4 Interceptors

We can also add build condition. In this example, platoon will be built only if player has more than 20 air mobile units.
```lua
opai:AddBuildCondition('/lua/editor/otherarmyunitcountbuildconditions.lua', 'BrainsCompareNumCategory',
       {'default_brain', {'HumanPlayers'}, 20, categories.ALLUNITS * categories.MOBILE, '>='})
```
- **'/lua/editor/otherarmyunitcountbuildconditions.lua**' - path to file with build condition
- **'BrainsCompareNumCategory**' - name of the function that will compare the numbers
- **'default_brain**' - our AI army
- **{'HumanPlayers'}** - target armies, in this case it will look for all human player, else we can put in any number of armies, example: **{'Player', 'Order', 'Coop2'}**'
- **20** - number of units
- **categories.ALLUNITS \* categories.MOBILE** - units we're looking for
- **'>=**' - compare type, available: **'>=**', **'\<=**', **'>**', **'>**'

Lua files with all build conditins available are in this folder:

`Supreme Commander - Forged Alliance\gamedata\lua.scd\lua\editor`

##### Custom Unit Platoons

In our custom template we can set as many unit types and unit count as we want. We will need to know ID's of the units so [Unit Database](/Unit-Database) will come in handy.
```lua
   Temp = {
       'NavalAttackTemp2',
       'NoPlan',
       { 'ues0201', 1, 4, 'Attack', 'GrowthFormation' },   -- Destroyers
       { 'ues0202', 1, 2, 'Attack', 'GrowthFormation' },   -- Cruisers
       { 'xes0205', 1, 2, 'Attack', 'GrowthFormation' },   -- Shield Boat
   }
   Builder = {
       BuilderName = 'NavyAttackBuilder2',
       PlatoonTemplate = Temp,
       InstanceCount = 1,
       Priority = 400,
       PlatoonType = 'Sea',
       RequiresConstruction = true,
       LocationType = 'SouthNavalBase',
       BuildConditions = {
           { '/lua/editor/otherarmyunitcountbuildconditions.lua', 'BrainGreaterThanOrEqualNumCategory',
       {'default_brain', 'Player', 20, categories.NAVAL * categories.MOBILE + categories.uel0203}},
       },
       PlatoonAIFunction = {SPAIFileName, 'PatrolChainPickerThread'},     
       PlatoonData = {
           PatrolChains = {'M3_Air_Base_NavalAttack_Chain2', 'M3_Air_Base_NavalAttack_Chain4}
       },
   }
   ArmyBrains[UEF]:PBMAddPlatoon( Builder )
```
- If this is our first custom template in function then we need to put **local =** in front of **Temp** and **Builder**
- **Temp = {}** - Our custom template.
	- **'NavalAttackTemp2**' - Name of our template, make sure it's unique in your mission!
	- **'NoPlan**' - We will specify what platoon will do few lines below.
	- **{ 'ues0201', 1, 4, 'Attack', 'GrowthFormation' }, # Destroyers** - table for one unit
		- **'ues0201**' - Unit ID
		- **1** -
		- **4** - Number of units to be built
		- **'Attack**' - Basic unit function. Other typer are **Support, Scout, Artillery**
		- **'GrowthFormation**' - There are 2 formations used in FA, this one is more compact. **AttackFormation** is more wide open.
		- **# Destroyers** - Note to keep track on units.
- **Builder = {}** - This will build our template.
		- **BuilderName = 'NavyAttackBuilder2**' - Name of our builder, make sure it's unique in your mission!
		- **PlatoonTemplate = Temp** - Using template we created few lines  above.
		- **InstanceCount = 1** - How many of these platoon we want.
		- **PlatoonType = 'Sea**' - Specify factory type that this template should be sent it.
    	- Other types are **Land, Air, Gate**
		- **RequiresConstruction = true,** - True since we need the platoon to be built by AI.
		- **LocationType = 'SouthNavalBase**' - Name of our base as it is in [Map Editor](/Map-Editor) / save.lua file.
		- **BuildConditions** - This is optional if we want the platoon to be built only if certain conditions are met.
- On last line our custom platoon will get finally assembled
		- **ArmyBrains\[UEF\]** - Army that will use this template
		- **PBMAddPlatoon( Builder )** - Adds our platoon builder that contains our template.

### Usage

Now when we have our AI ready, we need to import it's file to the beginning of **script** to use it.
```lua
local M1UEFAI = import('/maps/Prothyon16/Prothyon16_m1uefai.lua')
```
Next step is to activate it. This line will handle that:
```lua
M1UEFAI.UEFM1WestBaseAI()
```
- This calls for **UEFM1WestBaseAI()** function in **M1UEFAI** that we imported at the beginning of script file.
- Every base is usually defined by it's own function. So to activate them all, you need to call for all functions.

## Voice Overs
![vo_example.png](/images/mapping/map-script/vo_example.png){.align-right}
Voice overs are a table of several variables. They could be defined it script file but to keep better track on them, they have their own file called **_string.lua** and are imported into script. In our example it is.

`Prothyon16_DEMO_strings.lua`

Right now there in no other way where to have videos and sound files than in Forged Alliance installation folder:

`Supreme Commander - Forged Alliance\movies`
`Supreme Commander - Forged Alliance\sounds\Voice\us`

### Format

One VO can contain more than one videos, they will be played one after another. The format is:
```lua
VOname = {
  {text = `*`,`` ``vid`` ``=`*`, bank = `*`,`` ``cue`` ``=`*`, faction = ''},
  {text = `*`,`` ``vid`` ``=`*`, bank = `*`,`` ``cue`` ``=`*`, faction = ''},
  {text = `*`,`` ``vid`` ``=`*`, bank = `*`,`` ``cue`` ``=`*`, faction = ''},
}
```
And in our example:
```lua
-- Third objective intro 1 / Actor: Gyle / Update 22/05/2015 / VO Ready
airbase1 = {
  {text = '[Gyle]: The island is now secure.', vid = 'Pro_16_airbase1.sfd', bank = 'G_VO1', cue = '21airbase1', faction = 'UEF'},
}
```
- First line is description of our VO.
- **airbase1** - is unique name for this VO that will be called in
    **script**.
		- **text = '\[Gyle\]: The island is now secure.**' - This will be displayed in VO box in game.
		- **vid = 'Pro_16_airbase1.sfd**' - Name of VO's video file.
		- **bank = 'G_VO1**' - Name of VO's sound file.
		- **cue = '21airbase1**' - Specific track inside of the sound file.
		- **faction = 'UEF**' - Faction displayed with VO. Options are: **UEF, Aeon, Cybran, Seraphim, NONE**.

### Usage

In order to use VO's we created in **string** file, we need to import this file at the beginning of the **script**
```lua
local OpStrings = import('/maps/Prothyon16_DEMO/Prothyon16_DEMO_strings.lua')
```
Function with VO is called **Dialogue** and it's defined in **ScenarioFramework.lua** so we need to import this file as well.
```lua
local ScenarioFramework = import('/lua/ScenarioFramework.lua')
```
- If you want to get more detailed information what excatly this function do, look inside ScenarioFramework

Now we have everything ready to use VOs in our code. The format for is following:
```lua
ScenarioFramework.Dialogue(OpStrings.VOname, callback, critical)
```
- **ScenarioFramework.Dialogue** - Calls for Dialogue function in ScenarioFramework that we imported at the beginning
- **OpStrings.VOname** - calls for our specific VO we created in **string.lua** file.
- **callback** - Callback function that this VO will start. If there is no, then type **nil**
- **critical** - **true** or **false** / nothing. If set to true, this will make sure this VO will be always played. WIll not be blocked by some other VO.
	- Story VO's are usually set to true, while taunts are not that important.

Example without and with callback fucntion:
```lua
ScenarioFramework.Dialogue(OpStrings.intro1, nil, true)
ScenarioFramework.Dialogue(OpStrings.airbase1, IntroMission3)
```
### Video

Adding videos to supcom can be very troublesome if you don't know how, and don't have the right tools. Luckily, this wiki explains it all for you!

Required Tools:
- SFDmux - this is a hard to find software which you need to create .sfd files from m1v files.
- TMPGEnc - you can use this to convert .wav files to .m1v files, for SFDmux to use.
- (Optional) Video editing software - so you can create and convert the videos to the right format.

The required tools are very difficult to find, so both of them are available for download
[here](https://mega.nz/#!9kAFSbyQ!Sz6Q8ZB5Ekg-jxLXQLlfFnusrp_24eoNiF6inr4B54g).
- First open TMPGEnc and select the path to your video file.
- You can mess around with the settings, or you can load settings included in the download; for this example, **Example_VOs.mcf** was used.
- Once you are happy with how it looks, select the checkbox *Video only* under *Stream Type* and press **Start**.
- Next put your newly-created .m1v file into the **SFDmux** folder, and rename the file to **video.m1v**.
- Run **convert video without audio.bat** to convert the file.
- You can edit the .bat file with notepad to convert a file under a different name, or do many at once; see **Example batch file.bat** for the settings that were used for the mission.
- Rename your .sfd file so it matches what you have specified in your mission script and then place it into your game directory:

`Supreme Commander - Forged Alliance\movies`

### Audio
![xact_audio_creation.png](/images/mapping/map-script/xact_audio_creation.png){.align-right}
To add audio to your mission, the audio files first need to be prepared - supcom only accepts audio as *wavebank (.xwb)* and *soundbank (.xsb)* formats, both of which are needed to work.

Some useful words you should know about:
- A ***wave*** is the term used for .wav sound files in XACT.
- A ***wavebank*** is a file which contains the actual audio files needed for your project - it can contain many files at once, in any order.
- A ***soundbank*** file uses the files from the wavebank, and arranges them into sounds.
- A ***cue*** is inside the soundbank and is what the game uses to call the sounds from the soundbank. A cue can call multiple sounds in different orders in needed.

Here is a list of tools you require to add sounds to your map (or mod):
-   Cross Platform Audio Creation Tool ***version 2.0*** (XACT) - this is available from microsoft as part of the DirectX SDK [here](https://www.microsoft.com/en-gb/download/confirmation.aspx?id=13287)
- The sound files you want to put in, formatted as .wav files
- (Optional) Some Sound editing software, just to make it easier if some of the sounds are not quite right.

Everything else can be done from inside the tool. If you mess around with it, you should be able to work out how it works in 5 minutes, there is also a pretty good documentation of the tool [here](https://msdn.microsoft.com/en-us/library/ff827590.aspx). Once you have made your *wavebank (.xwb)* and *soundbank (.xsb)* files, you need to place them into:s

`Supreme Commander - Forged Alliance\sounds\Voice\us`

Note that the sounds will only work if you are running the **us** localization of supcom. For the sounds to work with other languages, you need to put the files into their respective localization folders. 

#### Adding Compression

#### Adding Compression

You can add compression to your sounds, which makes them take up roughly 4 times less space.

- Right click on the compression presets and select *New Compression Preset*.
- There are presets for Windows and Xbox, leave Xbox as is, and select ADPCM for Windows.
	- The default 128 samples per block works fine and results in a 27% compression ratio.
	- Other ratios are untested at time of writing but you can try them out.
- Then select your waves in the wavebank and in the bottom left choose your compression preset from the drop down list.
- The table should show the PC format as ADPCM and the PC Ratio as 27% or similar.

#### Setting the sound categories
Supcom uses various categories for each sound to work out how loud they should be, and set their volumes correctly in the options menu. So you need to set them in the XACT project beforehand. Known categories are:
- Global
- World (sharing the SFX slider)
- Interface (sharing the SFX slider)
- VO
 ![xact.png](/images/mapping/map-script/xact.png)
## Tables

### Categories

![capture.png](/images/mapping/map-script/capture.png)
### Enhancements
| **ACU Upgrades** 	|
|---	|---	|---	|---	|
| <img src="/images/mapping/map-script/a_acu.png" width="60" align="center"/> **Aeon** 	| <img src="/images/mapping/map-script/cybran_acu.png" width="60" align="center"/> **Cybran** 	| <img src="/images/mapping/map-script/uef_acu.png" width="60" align="center"/> **UEF** 	| <img src="/images/mapping/map-script/sera_acu.png" width="60" align="center"/> **Seraphim** 	|
| AdvancedEngineering <br> T3Engineering <br> ChronoDampener <br> CrysalisBeam (Range) <br> EnhancedSensors <br> HeatSink (Fire Rate) <br> ResourceAllocationAdvanced <br> Shield <br> ShieldHeavy <br> ResourceAllocation <br> Teleporter 	|   AdvancedEngineering <br> T3Engineering <br> CloakingGenerator <br> CoolingUpgrade (Gun) <br> MicrowaveLaserGenerator <br> NaniteTorpedoTube <br> StealthGenerator <br> ResourceAllocation <br> Teleporter 	| AdvancedEngineering <br> T3Engineering <br> DamageStabilization (Nano) <br> HeavyAntiMatterCannon (Gun) <br> LeftPod <br> RightPod <br> Shield <br> ShieldGeneratorField <br> TacticalMissile <br> TacticalNukeMissile <br> ResourceAllocation <br> Teleporter 	| AdvancedEngineering <br> T3Engineering <br> AdvancedRegenAura <br> BlastAttack (Splash Gun) <br> DamageStabilization (Nano) <br> DamageStabilizationAdvanced <br> Missile <br> RateOfFire (Gun) <br> RegenAura <br> ResourceAllocationAdvanced <br> ResourceAllocation <br> Teleporter 	|
| **sACU Upgrades** 	|
| <img src="/images/mapping/map-script/a_sacu.png" width="60" align="center"/> **Aeon** 	| <img src="/images/mapping/map-script/cybran_scu.png" width="60" align="center"/> **Cybran**	| <img src="/images/mapping/map-script/uef_scu.png" width="60" align="center"/> **UEF**	| <img src="/images/mapping/map-script/sera_scu.png" width="60" align="center"/> **Seraphim**	|
| EngineeringFocusingModule <br> ResourceAllocation <br> Shield <br> ShieldHeavy <br> StabilitySuppressant (Gun) <br> SystemIntegrityCompensator (Nano) <br> Sacrifice <br> Teleporter 	| CloakingGenerator <br> EMPCharge <br> FocusConvertor (Gun) <br> NaniteMissileSystem (AA) <br> ResourceAllocation <br> SelfRepairSystem <br> StealthGenerator <br> Switchback (Engineering) 	|  AdvancedCoolingUpgrade (Rate of Fire) <br> HighExplosiveOrdnance (Splash) <br> Pod <br> RadarJammer <br> ResourceAllocation <br> SensorRangeEnhancer <br> ShieldGeneratorField <br> Shield 	| DamageStablization (Nano) <br> EngineeringThroughput <br> EnhancedSensors <br> Missile <br> Overcharge <br> Shield <br> Teleporter 	|

'attack'
'support'
'artillery'
'scout'
'guard'

## Common Issues

This part will contain mistakes that are made quite often, example warning in the log is taken a random mission so it won't be 100% as you see it in your mission. But the file and the name of function will be the same.

### ExecutePlan
```lua
 WARNING: Error running lua script: ...ments\github\fa\lua\ai\aiarchetype-managerloader.lua(52): attempt to call method `HasBuilderList' 
(a nil value)
    stack traceback:
         ...ments\github\fa\lua\ai\aiarchetype-managerloader.lua(52): in function `ExecutePlan' 
         ...users\multimedia\documents\github\fa\lua\aibrain.lua(712): in function `ExecutePlan' 
```
**Solution:** [Set AI Plan for each army](/Mission-Scripting#ai-plan)

### AI not building any units

If you managed to spawn a base with BaseManager, engineers are assisting factories, patrol in the base, but the base is not producing any units that it should.

**Solution:** [Set Faction for AI Army](/Mission-Scripting#ai-faction)

### Syntax Error
```lua
WARNING: SCR_LuaDoFileConcat: Loading ...
```
If the map loads all zoomed out and nothing happens, you might see this error in the log, it means you have a syntax error in the file it's showing. The number behind the file in brackets is suggestion on which line the problem is.

### WaitSeconds
```lua
WARNING: BeginSession() failed: attempt to yield across metamethod/C-call boundary
	stack traceback:
			[C]: in function `WaitTicks' 
			c:\users\odstr\documents\github\fa\lua\siminit.lua(28): in function `WaitSeconds' 
```
This error happens when you try to use **WaitSeconds()** function in the main flow of the script. In order to solve that you need to **ForkThread()** the function where you used **WaitSeconds()** or just the part where you're using **WaitSeconds()** 

Usually it occurs in the cinematics, then you need to **ForkThread()** the whole function, or in some part of the code where you're using **while** cycle.