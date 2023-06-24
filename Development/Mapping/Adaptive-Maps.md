---
title: Adaptive Maps
description: An overview of adaptive maps, the features of the script, and the setup required.
published: true
date: 2023-06-24T21:04:59.132Z
tags: mapping
editor: markdown
dateCreated: 2021-08-31T09:41:55.475Z
---

### Note there is an Updated Version of this guide [Here](/map-development/Adaptive-Mapping-2021)


Without these maps it was common practice to upload multiple versions of the same map, only to change/add some resources (e.g. Canis 4v4, Canis 5v5,...). That belongs to the past now. Thanks to the adaptive map script by CookieNoob and KeyBlue (modified by svenni_badbwoi), several similar versions of a map can be combined into a single map. Therefore advanced map settings become available that allow you to adjust the map itself and how it will play out directly from the game lobby. The purpose of the adaptive map series is a customizable map experience. It allows you e.g. to adapt the given map resources to the player count  (Dynamic Spawn Of Resources) and to add/remove resources as well as units/wrecks.

Depending on the map up to 16 players are supported, keep in mind that the map can be played with any player count. From 1v1 to 8v8 any matchup is possible. However, due to the map size and the available space, it is not recommended to use all available slots on all maps. The amount of spawn points allows for more flexibility on where the teams are located and thus you can even play some maps from completely different (and unusual) directions (i.e. Adaptive Wonder Open or Adaptive Sand Box in a top right vs bottom left match instead of top left vs bottom right). 

If you intended to play a 4v4, but 10 people are in the game lobby, just open more slots and the resources will automatically adapt to 5v5. You don't need to switch the map to a larger version anymore 

## Adaptive map features

All features are optional and can be adjusted in the "Advanced" part of the game options (scroll down). By hiding unchanged game options you can see the changes on the map options most easily (the small checkbox below the map preview).

![advanced_options.png](/images/mapping/advanced_options.png)

### Lobby features

Use "close" to remove the resources for that spot (if a spot is not used, the resources won't spawn, it isn't required to close the spot as well). Use "close - spawn mex" to spawn the resources on empty spots (and their mirrors).

![close_spawn_mex.png](/images/mapping/close_spawn_mex.png)

NOTE: If you like to play random spawn and if the number of players is less than the possible spawn points, close the remaining slots.

### Resource features

#### Dynamic Spawn Of Resources
Determine which mexes & hydros should be spawned.
- Mirror Slots: Spawn resources for the player & mirror slot (balanced resources).
- Used Slots: Only spawn resources for players on used slots (unbalanced resources).
- No Mirror = No resources: Only spawn resources if the mirror slot is also occupied by a player (not recommended, but it can make uneven matches fairer).
- XvX setup: Don't adjust for player & spawn resources for XvX.

#### Crazyrush
Activate different types of crazy rush for the spawned mexes. Building a mex on a mass point will always create new adjacent mass points to build on.
- crazy rush forward mexes: Activate crazy rush only for some mexes. All other mexes will behave normally.
- crazyrush 1 core mex: Activate crazyrush & spawn only 1 core mex per active slot (the mex needs to be bound to ARMY_X).
- crazyrush: Activate crazyrush for all spawned mexes.

#### Regrowing Trees
Regrow reclaimed/destroyed trees when other trees are nearby. Regrow is faster if more trees are close. Note that the performance of this option heavily depends on the number of trees on the map.

#### Natural Reclaim Values
Change mass & energy values of rock & tree props.

### Scale resources


#### Extra Hydros
Spawn additional hydros.

#### Extra Mexes
Spawn additional mexes.

#### Middle Mexes
Configure the number of mexes in the middle of the map.

#### Side Mexes
Configure the number of mexes at the sides of the map.

#### Underwater Mexes
Configure the number of underwater mexes.

#### Island Mexes
Configure the number of mexes on the island.

#### Expansion Mexes
Configure the number of mexes at the expansion.

### Scale base resources

#### Core Mexes
Spawn e.g. 3 or 4 core mexes.

#### Extra Base Mexes
Spawns additional mexes for each player in the starting base (further away from core mexes).

### Scale intentional uneven resources
This functionality is used on Wonder Open to determine the number of mexes in the corners separately. It is possible to add a warning message at the start of the game when the map is unbalanced due to this (i.e. the teams are distributed such that the corner with more mex is easier reachable for one team. This requires a little bit of coding (most of this code is already prepared and just needs to be slightly adjusted).

#### Top Side Mexes
Adjust the number of mexes in the middle of the side spots on the top side.

#### Bottom Side Mexes

Adjust the number of mexes in the middle of the side spots on the bottom side.

### Unit features

Add the desired groups to ARMY_17 and add units. The group names need to be identical in the editor (save.lua) and script.lua file.

#### Wreckage

Scale amount of unit wrecks (e.g. T1 wrecks, T2 wrecks, T3 wrecks and T4 wrecks).

#### Naval Wreckage

Scale amount of naval unit wrecks (e.g. T1 wrecks, T2 wrecks, T3 wrecks and T4 wrecks).

#### Middle Wreckage

Scale the number of unit wrecks in the middle of the map. 
#### Faction Wreckage

Add wrecks to the desired position on the map. The faction of these wrecks is dependent on the faction of the player close by. There is a preset to spawn either UEF or Cybran unit wrecks which can be easily adjusted.

#### Civilian Base

Spawn civilian base at the desired position of the map (e.g. disabled, wreckage or operational).

#### Civilian Defenses

Spawn civilian defences at the desired position of the map (e.g. disabled, T1 wrecks (PD+AA), T2 wrecks (PD+TMD), T3 wrecks (PD+AA), T1 operational (PD+AA), T2 operational (PD+TMD), T3 operational (PD+AA)).

#### Jamming

Add Seraphim jamming crystals to the desired position of the map, to create false radar signals.

### Expand Map Area

Start the map not entirely expanded, but reduced to a certain size (you need to define two areas in the editor, one for the initial size and one for the final size). The option determines how long the playable area is restricted. The map area expands if a certain criterium is met (e.g. time passed, percentage of mexes build). There is a function prepared to expand the map automatically at the start of the game if a player spawns in the restricted area (this requires you to uncomment the code in the expand map part of the script and adjust the player numbers, depending on which army is outside of the initial playing area). 

## How to make an adaptive map

To create an adaptive map you can either use the FAF map editor (the adaptive map files are available as a preset option) or download them directly from the GitHub repository. Adaptive map files: <https://github.com/CookieNoob/Adaptive-Maps-forged-alliance>

As a starting point, it is highly recommended that you watch the tutorial video which presents a step-by-step manual on how to create an adaptive map. Youtube tutorial: <https://www.youtube.com/watch?v=VVxEhCuc53g&feature=youtu.be>

If you need more help you can post in the adaptive map forum topic. Forum thread: <http://forums.faforever.com/viewtopic.php?f=53&t=13014> or: - ask CookieNoob (Author of the adaptive map script) - ask svenni_badbwoi (rewrote parts of the script to make it easier to understand) - ask Blue_Owl (made a few adaptive maps) 

While filling the table file is easy with the FAF editor, not all changes can be directly done from there. You still have to add/change the following files to make your map adaptive.

### _scenario.lua

Add "Adapti veMap = true," to the file. The original editor will delete the line when saving, make sure to add it again. This will enable the "close - spawn mex" option in the lobby (in addition to the normal "close slot"). Don't forget to add "NEUTRAL_CIVILIAN" as army to the scenario file (even if you don't add civilians), they are required by the phantom-X mod for the meteor function. If you use the adaptive map files, please credit the author in your map description. 
```lua
version = 3
ScenarioInfo = {
		name =  "Adaptive Map-Name",
    description = "...."
    preview = '',
    type = 'skirmish',
    starts = true,
    size = {512, 512},
    AdaptiveMap = true,
    map_version = 2,
    map = '/maps/adaptive_map-name.v0002/adaptive_map-name.scmap',
    save = '/maps/adaptive_map-name.v0002/adaptive_map-name_save.lua',
    script = '/maps/adaptive_map-name.v0002/adaptive_map-name_script.lua',
    norushradius = 60.0000000,
    Configurations = {
    		['standard'] = {
        		teams = {
            		{
                		name = 'FFA',
                    armies = {'ARMY_1','ARMY_2','ARMY_3','ARMY_4','ARMY_5','ARMY_6','ARMY_7','ARMY_8','ARMY_9','ARMY_10','ARMY_11','ARMY_12','ARMY_13','ARMY_14','ARMY_15','ARMY_16'}
                },
            },
            customprops = {
            		['ExtraArmies'] = STRING( 'ARMY_17 NEUTRAL_CIVILIAN; ),
            },
        },
    },
},       
```
NOTE: The name depends on the map status!

The test version of your map should be called "Map Name Ultimate".

When the desired features are implemented and no known bugs remain, re-upload the release/final version of the map under the name "Adaptive Map Name" and ask a moderator (or someone from the Map and Mod team) to hide your old version of the map in the vault.

NOTE: Organise your armies in such a way that ARMY_2 is the mirror/enemy of ARMY_1. Otherwise, you have to change the script.lua file.

### _table.lua

Enter the desired mex/hydro numbers to the according ARMY and/or feature. Also, enter the value for the maximum number of slots on the map (maxPlayerOnMap). You have to do it manually if you use the original editor, but you can easily fill the tables with the FAF editor. 
``` lua
-- line number is 10 + armynumber for the mexs in the table
spwnMexArmy = {	 {},			-- ARMY_1
									{},			-- ARMY_2
                  {},			-- ARMY_3
                  {},			-- ARMY_4
                  {},			-- ARMY_5
                  {},			-- ARMY_6
                  {},			-- ARMY_7
                  {},			-- ARMY_8
                  {},			-- ARMY_9
                  {},			-- ARMY_10
                  {},			-- ARMY_11
                  {},			-- ARMY_12
                  {},			-- ARMY_13
                  {},			-- ARMY_14
                  {},			-- ARMY_15
                  {},			-- ARMY_16

exampleMexes = {{1,2},{3,4},{5,6}},
exampleMexes = {{a},{b},{c}},
		option key=1 : removes a+b+c
    option key=2 : spawn a, removes b+c
    option key=3 : spawn a+b, removes c
    option key=4 : spwan a+b+c
    
exampleMexes = {{1,2}}
exampleMexes = {{a}}
		option key=1 : removes a
    option key=2 : spwan a
```

### _options.lua

Adapt the text to explain your features and set the default key. There are several prototype options in the bottom part of the file which are ready to use. These options are already implemented and will work directly by filling out the appropriate table. If you want to use one of these options, move them to the part of the file which is not commented out.

```lua
{
		default = 1,
    label = "Example Mexes",
    help = "Spawn additional example mexes.",
    key = 'example_mexes',
    pref = 'example_mexes',
    values = {
    		{ text = "0", help = "No example mexes.", key = 1,},
        { text = "2", help = "Spawn 2 example mexes.", key = 2,},
        { text = "4", help = "Spawn 4 example mexes.", key = 3,},
        { text = "6", help = "Spawn 6 example mexes.", key = 4,},
		},
},
```
### _script.lua

At the top of the file are the default key values of the options. The default is set in a way that nothing should break, but most likely you want to choose a different default value for some options. Change the defaults to match the option.lua default keys. The script also needs the path for the tables file to be set appropriately (also on the top of the file).
```lua
local Tables = import ('/maps/mapfolder/mapname_tables.lua')

-- Enter the maximum possible player count
local maxPlayerOnMap = 16

-- IMPORT: options.1ua settings
-- chosen key or default key

local dynamic_spawn = ScenarioInfo.Options.dynamic_spawn or 1
local crazyrush_mexes = ScenaricInfo.Options.crazyrush_mexes or 1
local extra_hydros = ScenarioInfo.Options.extra_hydros or 1
local extra_mexes = ScenarioInfo.Options.extra_mexes or 1
local middle_mexes = ScenaricInfo.Options.middle_mexes or 1
local side_mexes = ScenaricInfo.Options.side_mexes or 1
local underwater_mexes = ScenarioInfo.Options-underwater_mexes or 1
local islend_mexes = ScenaricInfo.Options.islend_mexes or 1
local expansion_mexes = ScenarioInfo.Options.expansion_nmexes or 1
local core_mexes = ScenaricInfo.Options.core_mexes or 1
local extra_base_mexes = ScenaricInfo.Options.extra_base_mexes or 1
local top_side_nexes = ScenaricInfo.Options.top_side_mexes or 1
local bottom_side_mexes = ScenaricInfo.Options.bottom_side_mexes or 1
-- Units
local optional_vreckage = ScenarioInfo.Options.optional_vreckage or 1
local optional_naval_vreckage = ScenarioInfo.0ptions.optional_naval_vreckage or 1
local optional_wreckage_middle = ScenarioInfo.0ptions.optional_vreckage_middle or 1
local optional_adaptive_faction_wreckage = ScenarioInfo.Options.optional_adaptive_faction_wreckage or 1
local optional_civilien_base = ScenarioInfo.Options.optional_civilian_base or 1
local optional_civilien_defenses = ScenaricInfo.Options.optional_civilian_defenses or 1
local jamming = ScenarioInfo.0ptions.jamming or 1
```
### Map Editor

To make the wreckages and civilians adjustable, you have to create unit groups in the editor. They should be named in the same way as in the script (or adjust the names in the script). 

![army_17_adaptive_unit_groups.png](/images/mapping/army_17_adaptive_unit_groups.png)