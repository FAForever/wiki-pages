---
title: FAF version - Mapping Guidelines
description: GPG, unknown & inactive author map rework
published: false
date: 2023-07-13T18:24:01.549Z
tags: mapping, guidelines, advanced, faf_version
editor: markdown
dateCreated: 2023-06-19T22:22:31.122Z
---

# 1 Introduction {#sec-1}
The goals of the `FAF version` maps are fair / balanced gaming conditions and an improved / up-to-date gaming experience. To ensure the goals are met for every `FAF version` map, these `Mapping Guidelines` were created to empower authorized `FAF version` map maker. These guidelines are based on the `FAF version` maps created by svenni_badbwoi.

> **IMPORTANT NOTES:**
> - **Map upload of approved content stays in the hands of <span style="background-color: yellow"> authorized `FAF version` map maker</span>! Don't upload any `FAF version` map without authorization!**
> - **If you can’t meet the requirements mentioned in this document, regardless of your authorization status, you are not qualified / allowed to create and upload a `FAF version` map!**
> - **Adaptive maps and maps with individual assets are even harder to rework and require a total understanding of all dependencies.**

## 1.1 Released FAF Version Maps & Change Documentation {#sec-1-1}
`FAF version` maps that have been released already can be found in the `FAF vault` if you search for the suffix ` - FAF version`. Please download the latest map version `.v000X` for the best in game experience.

The documentation of the map-related changes can be found here:
 - [Forum (svenni_badbwoi)](https://forum.faforever.com/topic/398/faf-version-gpg-unknown-inactive-author-map-rework)
 - [Forum (MadMax)](https://forum.faforever.com/topic/5869/faf-version-maps)

> **Note:**  The [Indivudual Map Issue Documentation](https://ethercalc.net/kkn2yatyf4wq) provides an overview of all reported isses and deails on how these issues have been resolved in specific map versions. This documentation is intended for authorized `FAF version` map makers to track and resolve open reported map-related issues as well as individual issues that arise during the map creation process.
<span style="background-color: yellow">(This documentation should be replaced and merged into the future ticket system data base enties, with similar requirements / columns)</span> 


## 1.2 Report New Map Issues (Community Support) {#sec-1-2}
Have you ever found yourself frustrated by unbalanced heightmaps or unevenly distributed marker, props and units in the following maps:
- [Gas Powered Games (GPG) maps](https://ethercalc.net/0ds9j65h5wrr) <span style="background-color: yellow">Add Link to GPG Editor "Original Maps" table - need a cross- reference at "Original Maps" section - or copy table to this article? https://wiki.faforever.com/en/Development/Mapping/GPG-Map-Editor</span>
  - Supreme Commander and Forged Alliance stock maps included in the original game
- Unknown author maps
- Inactive author maps

If the issue has not already been resolved (see [1.1](#sec-1-1)), please feel free to inform us about any map-related issues here:
- [Ticket System]() <span style="background-color: yellow">Add Link</span>


# 2 Preparations

## 2.1 Required Tools {#sec-2-1}

### 2.1.1 Text-Editor {#sec-2-1-1}
Get `Visual Studio Code`, the recommended text editor of the [FAF development guide](https://github.com/FAForever/fa/blob/deploy/fafdevelop/setup/setup-english.md#development-environment), which can format and highlight the LUA file structure.

### 2.1.2 GPG-Editor {#sec-2-1-2}
The GPG-Editor can only read and save Supreme Commander `v56` map versions.

> **Notes:**
> - If the GPG-Editor is unable to load the map, place the map folder in the default Supreme Commander maps path (see [3.1.1](#sec-3-1-1)).
> - If the GPG-Editor crashes while loading, try re-saving the map in `v56` format via FAF-Editor and try again.
> - The GPG-Editor needs a no-rush radius value (see [2.2.2](#sec-2-2-2)), otherwise it will crash during loading.

**FAF content**
The GPG-Editor does not include the latest FAF changes.

**Map preview**
The GPG-Editor can create a 100% realistic Supreme Commander and Forged Alliance map `preview`. Meaning the map `preview` gets rendered like in game, except for the recent [FAF water shader changes](https://github.com/FAForever/fa/pull/4391).

> **Note:** One could copy over the shader files into the vanilla `gamedata` folder to achieve a 100% realistic map preview, but there's no written guide on that yet.

**Minimap**
The GPG-Editor DOES NOT color the land and water areas in the `minimap` differently.

**Skybox**
The GPG-Editor DOES NOT support the export and import of `skybox` files.

**Reclaim**
The GPG-Editor REMOVES the `reclaim` value from `_scenario.lua`.

> **Note:** The `reclaim` value is a feature of the FAF-Editor.

### 2.1.3 FAF-Editor {#sec-2-1-3}
The FAF-Editor can read and save Supreme Commander `v56` and Forged Alliance `v60` map versions.

> **Note:** FAF-Editor can be used to save a `v60` map in `v56` format to be able to edit the map in the GPG-Editor. Keep in mind that the `skybox` and other content gets lost while re-saving a `v60` map as `v56` format.

**FAF content**
The FAF-Editor includes the latest FAF changes.

**Map preview**
The map `preview` created in the FAF-Editor DOES NOT look 100% realistic. The textures and water get rendered differently.

**Minimap**
The FAF-Editor colors the land and water areas in the `minimap` differently.

**Skybox**
The FAF-Editor supports the export and import of `skybox` files.

**Reclaim**
The FAF-Editor adds / writes the `reclaim` value to `_scenario.lua`.

### 2.1.4 MapTransformer (by Sheikah) {#sec-2-1-4}
The `MapTransformer` by Sheikah is the recommended tool to recreate the map based on the `source map version` and `source` area or angle. You can request the latest version of the `MapTransformer` from Sheikah through a personal message. Usage see [3.5.1](#sec-3-5-1).

> **Credit:** Huge thanks to Sheikah for creating the `MapTransformer`.
> **Note:** If you encounter any issues or have questions, don't hesitate to reach out to Sheikah for assistance.


## 2.2 Understand Map File Content {#sec-2-2}

To make precise and efficient map modifications, it's crucial to understand the content of each map file in order to determine which files and changes should be used and which can be ignored safely (see [3.4](#sec-3-4)).

### 2.2.1 .scmap {#sec-2-2-1}

It's a non-text binary file. Changes need to be performed in a map editor or binary / hex editor. The file will be changed / rewritten when a map gets saved in a map editor.

The file holds the following information:
- **preview**
- **minimap**
- **heightmap**
- **strata / layer** (mask and path)
- **props** (position and path)
- **decals** (position and path)
- **skybox** (`v60` maps only)

> **Note:** The only difference between `v56` and `v60` map formats is the content of the `.scmap` file. The other map files can be used across all map formats.

#### Individual Assets {#sec-2-2-1-1}

Individual assets such as paths to prop or decal are hard-coded in the `.scmap` file. The path / version needs to be adapted, otherwise assets are missing or only loading when the original map is still in the maps folder.

- **Changed map name / path**
  - Change path in map editor or replace asset

- **Changed map version**
  - Open `.scmap` file in binary / hex editor (Visual Studio Code, Okteta, ...) and change version `.v000X`
  
> **Note:** Like GPG maps, the majority of maps do not contain individual assets. However, there are a community maps that incorporate individual assets.  
  

### 2.2.2 _scenario.lua {#sec-2-2-2}
It's a plain text file that contains LUA code. Changes can be performed with a text or map editor. Except for the `reclaim` value, there is no need to use a `_scenario.lua` that gets created while saving the map in the editor, you can simply modify the old file in a text editor.

> **Note:** Once you have a working `_scenario.lua` file with all the relevant information it can be placed in the `Master Map Version` folder. No further changes are needed.

The file holds the following information:
- **name** - Name of your map that will be displayed in game lobby.
- **description** - Description of your map that will be displayed in the game lobby.
- **type** - Set map type to `skirmish`.
- **starts** - Set it to `true`.
- **preview** - Keep this empty to have a working map preview in the FAF lobby.
<span style="background-color: yellow">Are custom previews from map folder not working?</span>
- **reclaim** – Value is generated by FAF-Editor / value will be lost in GPG-Editor.
- **size** - Size of the map (set in map editor), do not change it.
- **map_version** - Current version number of the map.
- **map** - Path to `.scmap` file.
- **save** - Path to `_save.lua` file.
- **script** - Path to `_script.lua` file.
- **norushradius** – Radius used if no rush is enabled.
- **norushoffset** – Offset that is used to move the no rush radius of every army (e.g. to ensure same mex/hydro amount).
- **armies configuration** - Playable `Armies` and `ExtraArmies` of the map. Check dependency in `_save.lua` (see [2.2.3](#sec-2-2-3)).
  - Ensure that `ARMY_9` or `ARMY_17` as well as `NEUTRAL_CIVILIAN` are added to `ExtraArmies`.
    - GPG maps need `ARMY_9` and `NEUTRAL_CIVILIAN`. The player count was limited to 8 `Armies`.
      ```lua
      armies = {'ARMY_1', 'ARMY_2', 'ARMY_3', 'ARMY_4', 'ARMY_5', 'ARMY_6', 'ARMY_7', 'ARMY_8'}
      ['ExtraArmies'] = STRING( 'ARMY_9 NEUTRAL_CIVILIAN' )
      ```
    - Other maps need `ARMY_17` and `NEUTRAL_CIVILIAN`. The player count is limited to 16 `Armies`.
      ```lua
      armies = {'ARMY_1', 'ARMY_2', 'ARMY_3', 'ARMY_4', 'ARMY_5', 'ARMY_6', 'ARMY_7', 'ARMY_8' ,'ARMY_9', 'ARMY_10', 'ARMY_11', 'ARMY_12', 'ARMY_13', 'ARMY_14', 'ARMY_15', 'ARMY_16'}
      ['ExtraArmies'] = STRING( 'ARMY_17 NEUTRAL_CIVILIAN' )
      ```
      <span style="background-color: yellow">Or should it be ARMY_17 in GPG map rework as well?</span>
#### Result / Settings (FAF-Editor) {#sec-2-2-2-1}
![faf_version_scenario.png](/images/faf-version/faf_version_scenario.png)   ![faf_version_armies_configuration.png](/images/faf-version/faf_version_armies_configuration.png)

#### Example _scenario.lua {#sec-2-2-2-2}
```lua
version = 3 -- Lua Version. Dont touch this
ScenarioInfo = {
    name = 'Setons Clutch - FAF version',
    description = 'Dozens of battles have been fought over the years across Setons Clutch. A patient searcher could find the remains of thousands of units resting beneath the earth and under the waves. - FAF version of the original Forged Alliance map "SCMAP_009": Ensures symmetrical heightmap, textures, decals, marker, props and units. Contains improved AI marker. - Modified by FAF Creative: https://forum.faforever.com/topic/398/faf-version-gpg-unknown-inactive-author-map-rework',
    preview = '',
    map_version = 1,
    type = 'skirmish',
    starts = true,
    size = {1024, 1024},
    reclaim = {55561.41, 336980.6},
    map = '/maps/setons_clutch_-_faf_version.v0001/setons_clutch_-_faf_version.scmap',
    save = '/maps/setons_clutch_-_faf_version.v0001/setons_clutch_-_faf_version_save.lua',
    script = '/maps/setons_clutch_-_faf_version.v0001/setons_clutch_-_faf_version_script.lua',
    norushradius = 70.000000,
    norushoffsetX_ARMY_1 = 15.000000,
    norushoffsetY_ARMY_1 = 40.000000,
    norushoffsetX_ARMY_2 = -15.000000,
    norushoffsetY_ARMY_2 = -40.000000,
    norushoffsetX_ARMY_3 = 12.000000,
    norushoffsetY_ARMY_3 = 38.000000,
    norushoffsetX_ARMY_4 = -12.000000,
    norushoffsetY_ARMY_4 = -38.000000,
    norushoffsetX_ARMY_5 = -40.000000,
    norushoffsetY_ARMY_5 = -15.000000,
    norushoffsetX_ARMY_6 = 40.000000,
    norushoffsetY_ARMY_6 = 15.000000,
    norushoffsetX_ARMY_7 = -10.000000,
    norushoffsetY_ARMY_7 = -10.000000,
    norushoffsetX_ARMY_8 = 10.000000,
    norushoffsetY_ARMY_8 = 10.000000,
    Configurations = {
        ['standard'] = {
            teams = {
                {
                    name = 'FFA',
                    armies = {'ARMY_1', 'ARMY_2', 'ARMY_3', 'ARMY_4', 'ARMY_5', 'ARMY_6', 'ARMY_7', 'ARMY_8'}
                },
            },
            customprops = {
                ['ExtraArmies'] = STRING( 'ARMY_9 NEUTRAL_CIVILIAN' ),
            },
        },
    },
}
```


### 2.2.3 _save.lua {#sec-2-2-3}

It's a plain text file that contains LUA code. Changes need to be performed in a map editor. The file will be changed / rewritten when a map gets saved in a map editor.

The file holds the following information:
- marker (position, group and path)
  - `ARMY_X`
  - `ExtraArmies`
    - `ARMY_9` or `ARMY_17`
    - `NEUTRAL_CIVILIAN`
  - **Units & Structures**
    - `INITIAL` – living (not moving)
    - `WRECKAGE` – dead
    - `PlatoonBuilders`– living (moving) with hard-coded purpose
  - **Resources**
  - **AI marker**

> **Note:** Changes to scripted maps like adaptive maps, require an understanding of all scripted dependencies e.g. army related mex spawning in `_tables.lua` and adaptive `_options.lua`.

#### NEUTRAL_CIVILIAN {#sec-2-2-3-1}

Living `NEUTRAL_CIVILIAN` units and structures should be placed in `INITIAL` group. They need a radar and enough power to work properly. Dead units and structures should be placed in `WRECKAGE` group.

#### Armies & ExtraArmies {#sec-2-2-3-2}

Every playable `ARMY_X` needs an `INITIAL` Group at `Units`. `ExtraArmies` like `ARMY_9` or `ARMY_17`  and `NEUTRAL_CIVILIAN` need an `INITIAL` & `WRECKAGE` Group at `Units`. Check dependency in `_scenario.lua` (see [2.2.2](#sec-2-2-2)).

> **Note:** This is needed for some mods to work. <span style="background-color: yellow">Is that true?</span>

#### Results / Settings (FAF-Editor)
![faf_version_save.png](/images/faf-version/faf_version_save.png)

### 2.2.4 _script.lua {#sec-2-2-4}

It's a plain text file that contains LUA code. Changes can be performed with a text editor.

The file holds the following information:
- <span style="background-color: yellow">how the map starts / behaves</span>

> **Note:**
> - There is no need to change the file content (except filename) while reworking GPG (Supreme Commander and Forged Alliance) maps.
> - Some maps (e.g. adaptive maps) have a map folder and file reference in the `_script.lua`. Make sure to update the path as well.

#### Example _script.lua {#sec-2-2-4-1}
```lua
local ScenarioUtils = import('/lua/sim/ScenarioUtilities.lua')

function OnPopulate()
	ScenarioUtils.InitializeArmies()
end

function OnStart(self)
end
```

## 2.3 Map Issues {#sec-2-3}

A lot of map-specific issues are already documented or fixed (see [1.1](#sec-1-1)). Get familiar with the open map-specific issues for optimal map rework results.

### 2.3.1 Issues In Game {#sec-2-3-1}

Check the issues in game.

### 2.3.2 Issues In Editor {#sec-2-3-2}

Check the issues in GPG or FAF Editor.

## 2.4 Check Other FAF Version Maps {#sec-2-4}

Download other `FAF version` maps from the `FAF vault` and get familiar with the requirements.


# 3 Create FAF version {#sec-3}
The primary focus of this section is to guide the creation of a balanced and optimized FAF version map while preserving its original essence and improving specific aspects.

## 3.1 Get Source Map Version {#sec-3-1}

**If the `source map version` of the `FAF version` is a GPG (Supreme Commader and Forged Alliance) map, Forged Alliance `v60` maps should always be used. The Forged Alliance `v60` maps are further developed (e.g. skybox, different units, ...) compared to the Supreme Commander `v56` ones (see [3.1.1](#sec-3-1-1), [3.1.2](#sec-3-1-2) and [3.1.4](#sec-3-1-4)).** 

In case of `unknown author` and `inactive author` maps, the `source map version` can be downloaded from the `FAF Vault` and will then be accessible in the Forged Alliance Forever maps path (see [3.1.3](#sec-3-1-3)).

> **Note:**
> GPG named the map folder and files differently than the map `name`. The map `name` is only visible in game or in the `_scenario.lua` file.
> - **GPG Skirmish Maps**
>   - `SCMP_0XX` are official Supreme Comander `v56` and Forged Alliance `v60` skirmish map folder and files
>   - `X1MP_0XX` are additional official Forged Alliance `v60` skirmish map folder and files
>   
> - **GPG Campain Maps**
>   - `SCCA_XXX` are official Supreme Commander `v56` campain map folder and files
>   - `X1CA_0XX` are official Forged Alliance `v60` campaign map folder and files

### 3.1.1 Supreme Commander (v56 | GPG-Editor) maps path {#sec-3-1-1}
Default GPG path: `\Gas Powered Games\Supreme Commander\maps`  
Default Stream path: `/steam/steamapps/common/Supreme Commander/maps`

### 3.1.1 Forged Alliance (v60) maps path {#sec-3-1-2}
Default GPG path: `\THQ\Gas Powered Games\Supreme Commander - Forged Alliance\maps`
Default Stream path: `/steam/steamapps/common/Supreme Commander Forged Alliance/maps`

### 3.1.3 Forged Alliance Forever (v56 and v60) maps path {#sec-3-1-3}
Needed for testing or if a map from unknown or inactive author has been downloaded from the `FAF Vault` as `source map version`.

Default FAF path: `/My Games/Gas Powered Games/Supreme Commander Forged Alliance/maps/`

### 3.1.4 Example GPG Source Map Version {#sec-3-1-4}

Different units/structure placement and count between Supreme Commander `v56` and Forged Alliance `v60` map versions. 
![faf_version_source_map_version.jpg](/images/faf-version/faf_version_source_map_version.jpg)
*Image: Theta Passage – Supreme Commander `v56` (left) VS Forged Alliance `v60` map version (right)*

## 3.2 Find Source Area Or Angle {#sec-3-2}

For a balanced `FAF version` of the map, it is crucial to correctly identify the `source` area or angle. The `source` marks the map content that will be used for the `FAF version` rework. If the map issue doesn't dictate a specific `source` area or angle (e.g. remove heightmap difference at map bottom > `source = TOP`), the `source` area or angle needs to be found/discussed.

> **Note:** In some cases, a different `source` area or angle was used to rework the heightmap and props differently.

### 3.2.1 Prepare Discussion {#sec-3-2-1}

To prepare the discussion, one of the following steps is advisable:
- Export `heightmap.raw` and create a 360° rotation/mirror video to discuss the `source` area or angle.
    - Worldmachine Template <span style="background-color: yellow">add</span>
- Create and test a few `source` area or angle options on the correct `source map version` with the `MapTransformer` and compare the results.
    - Terrain issues at `source` area or angle.
    - Changes in `prop value` and `marker` placement, ...

### 3.2.2 Discuss Source Area Or Angle / Map Issues / Requirements {#sec-3-2-2}

Engage in discussions with the ladder team, Team Match Maker (TMM), and the issue reporter to determine the optimal `source` area or angle based on the open individual map issues (see [1.1](#sec-1-1)), [preparations](#sec-3-2-1) and other map specific requirements. Please create a thread in the following channel on Discord:
- Official Forged Alliance Forever Discord
    - [Matchmaker-submissions](https://discord.com/channels/197033481883222026/832707438443626596)

> **Note:** It is recommended for authorized `FAF version` map makers to engage in discussions regarding open questions and unexpected issues that arise during the map rework process.

### 3.2.3 Example {#sec-3-2-3}

In the case of the `Setons Clutch – FAF version`, we agreed on a `source` angle of 115° (white area was used). See [forum post](https://forum.faforever.com/topic/398/faf-version-gpg-unknown-inactive-author-map-rework) for more examples.
![faf_version_source_angle.png](/images/faf-version/faf_version_source_angle.png)

## 3.3 Set up new map name, files, version, folder & file path {#sec-3-3}

While creating a new map, it is important to set up the folder, files, and file path according to the map name (see [Example](#sec-2-2-2-2) `_scenario.lua` and already uploaded `FAF version` maps). Copy the `source map version` folder to the `Master Map Version` directory (see [3.4](#sec3-4)) and make the following adjustments manually.

> **Note:** Manual adjustment is recommended at this step to ensure that the changes are made correctly. Re-saving the map with a different `name` will change the original content!

### 3.3.1 New Map Name {#sec-3-3-1}

Derive the new map name from the original map `name` in `_scenario.lua` and change it accordingly:
- Capitalize the first letters of the original map `name`.
- Special characters (except `-`) are not allowed.
    - Also see:
        - Map `name` and `_scenario.lua` content validation [page](https://api.faforever.com/maps/validate).
        - [FAF Vault Rules](https://wiki.faforever.com/en/Development/Vault/Rules).
- Add the suffix ` - FAF version` to get the final map name.
<span style="background-color: yellow">Should “FAF Version” be allowed as well?</span>

#### Examples
```lua
name = 'map name',
name = 'Map Name - FAF version',
```
```lua
name = 'Seton’s Clutch',
name = 'Setons Clutch - FAF version',
```


### 3.3.2 New Map File Names {#sec-3-3-2}

Derive the `FILE_NAME` from the new map `name` and change the map file names accordingly:
- All characters need to be lowered (`A` becomes `a`).
- White-spaces (` `) need to be replaced with an underscore (`_`).


#### Example
```lua
--INPUT
name = 'Setons Clutch - FAF version'
FILE_NAME = 'setons_clutch_-_faf_version'
```
```lua
--RESULT
scmap = 'setons_clutch_-_faf_version.scmap'
scenario = 'setons_clutch_-_faf_version_scenario.lua'
save = 'setons_clutch_-_faf_version_save.lua'
script = 'setons_clutch_-_faf_version_script.lua'
```

### 3.3.3 New Map Version {#sec-3-3-3}

Add the correct `map_version` to the `_scenario.lua` file. The value `map_version` was implemented by FAF and is needed for versioning/upload.

> **Note:** The first version of a map should be number `1`.

#### Example
```lua
--RESULT
map_version = 1,
```

### 3.3.4 New Map Folder Name {#sec-3-3-4}

Create `FOLDER_NAME` (from `FILE_NAME` and `map_version`) and rename the map folder accordingly.

#### Pattern
```
FOLDER_NAME = FILE_NAME + MAP_VERSION_STRING
```

#### Example
```lua
official_folder_name = 'SCMP_009'
map_version = 1,
MAP_VERSION_STRING = '.v0001'
FILE_NAME = 'setons_clutch_-_faf_version'
```
```lua
--RESULT
FOLDER_NAME = 'setons_clutch_-_faf_version.v0001'
```

### 3.3.5 New File Path {#sec-3-3-5}

Set the path according to the new map `FILE_NAME` and `FOLDER_NAME` in the `_scenario.lua` file.

> **Note:** Some maps (e.g. adaptive maps) have a map file reference in the `_script.lua`. Make sure to update that path as well.

#### Pattern
```lua
map = '/maps/FOLDER_NAME/FILE_NAME.scmap',
save = '/maps/FOLDER_NAME/FILE_NAME_save.lua',
script = '/maps/FOLDER_NAME/FILE_NAME_script.lua'
```

#### Example
```lua
--INPUT
FILE_NAME = 'setons_clutch_-_faf_version'
FOLDER_NAME = 'setons_clutch_-_faf_version.v0001'
```
```lua
--RESULT
map = '/maps/setons_clutch_-_faf_version.v0001/setons_clutch_-_faf_version.scmap',
save = '/maps/setons_clutch_-_faf_version.v0001/setons_clutch_-_faf_version_save.lua',
script = '/maps/setons_clutch_-_faf_version.v0001/setons_clutch_-_faf_version_script.lua'
```

### 3.3.6 Validate Map Metadata {#sec-3-3-6}

Use the validate map metadata [web-page](https://api.faforever.com/maps/validate) to validate the map `name` and `_scenario.lua` content.

### 3.3.7 Test Map {#sec-3-3-6}

Test the map in-game before you proceed with the next step.


## 3.4 Create Editor & Master Map Version Folder {#sec-3-4}

To streamline the process and maintain backups of the latest changes, it is recommended to create an `Editor Map Version` and `Master Map Version` in different directories. This ensures that only necessary and tested changes/files are transferred to the final version of the `FAF version` map.

> **Note:** To ensure that work is always being done on the latest version of the map, it's important to regularly replace the `Editor Map Version` with the `Master Map Version` folder.

### 3.4.1 Editor Map Version – FAF Maps Folder {#sec-3-4-1}

The `Editor Map Version` folder represents the work in progress as well as test version of the map. The `Editor Map Version` folder needs to be placed in the required map folder (simply copy the folder created in [3.3](#sec-3-3) into the required directory, see [3.1](#sec-3-1)). The benefits of the `Editor Map Version` are, it can be edited, saved, destroyed or deleted without affecting the `Master Map Version` backup. 

> **Note:** All changes that require the map editor or `MapTransformer` should be made in the `Editor Map Version` folder.

### 3.4.2 Master Map Version - Project Folder {#sec-3-4-2}

The `Master Map Version` folder is used to store, test and discuss final results and during the Map Upload Process. The `Master Map Version` should be placed in a separate project directory outside the FAF environment. The content of the `Master Map Version` will be updated by copying the tested necessary files (e.g. `.scmap` or `_save.lua`) from the `Editor Map Version` folder and replacing the files in the `Master Map Version` folder. This way, only relevant changes are transferred and the `Master Map Version` serves as a backup of the latest version of the map. It is not recommended to overwrite all files or to save the `Master Map Version` in a map editor, as this could result in unintended changes to the original content. Simply copy & replace `.scmap` if a new map preview was created / `_save.lua` if marker where changed (see [2.2](#sec-2-2)).

> **Notes:**
> - [Git](https://en.wikipedia.org/wiki/Git) is the recommended tool for committing final results in the `Master Map Version` folder.
> - The `_scenario.lua` content as well as the default quotation mark settings will be changed while using different map editors. It's good practice to finalize the `_scenario.lua` in the `Master Map Version` folder.



## 3.5 Implement Source Area / Angle {#sec-3-5}

After completing all the necessary preparation steps, it is now time to implement the `source` area or angle (see [3.2](#sec-3-2)) based on the `Editor Map Version`.

**Automating the implementation of the `source` area or angle using the `MapTransformer` by Sheikah is highly recommended. This ensures consistency and accuracy in the process, while also saving time and effort.** If you need to manually implement or recreate map assets, such as mirroring decals, refer to the documented steps at [3.5.2](#sec-3-5-2).

### 3.5.1 Automated Rotation / Mirror² (MapTransformer) {#sec-3-5-1}

The `MapTransformer` is a java command line tool. The `MapTransformer` rotates and mirrors² the map content based on the `symmetry` and `source` settings of the input map. Content that does not belong to the `source` gets deleted and repopulated according to the `symmetry` settings. Changes can be done separately or `--all` at once. .

> **Notes:**  
> - The `symmetry` settings (rotation, mirror) derive from the original `source map version`.
> - The `--all` option should be used to ensure a balanced `FAF version` map.
> - The `MapTransformer` does not create AI markers / preserve connections.
> - ² The `MapTransformer` is currently unable to mirror decals, see b2ag’s [scmap_mirror_tool](https://github.com/b2ag/scmap_mirror_tool) to mirror `.scmap` content.

#### Preparations & Usage

1. Install `Java 17` (minimum requirement)
2. In the directory where the `MapTransformer-17.jar` file is placed:
   1. Create `TransformedMaps` folder
   2. Create `InputMaps` folder
   3. Place the map folder (`Editor Map Version`) in the `InputMaps` folder
3. Adjust the code examples (`in-folder-path`, `symmetry` and `source` area or angle) to your needs
4. Run terminal in the directory where the `MapTransformer-17.jar` file is placed
5. Run code in terminal
6. Open `TransformedMaps` to access the modified map

#### Terminal options
The options can be seen by running `java -jar MapTransformer-17.jar –help`.

```java
--help		        // produce help message
--in-folder-path  // arg	required, set the input folder for the map
--out-folder-path // arg	required, set the output folder for the transformed map
--symmetry        // arg	required, set the symmetry for the map
    • POINT2      // 180° rotation
    • POINTN      // 360°/N rotation
    • X           // mirror / flip
    • Z           // mirror / flip
    • XZ          // mirror / flip
    • ZX					// mirror / flip
--source					// arg  required, set which half to use as base for forced symmetry
    • ANGLE
    • TOP
    • BOTTOM
    • LEFT
    • RIGHT
    • TOP_LEFT
    • TOP_RIGHT
    • BOTTOM_LEFT
    • BOTTOM_RIGHT
    • ALL
--all							// optional, force symmetry for all components
--spawns					// optional, force spawn symmetry
--resources				// optional, force mex symmetry
--props						// optional, force prop symmetry
--decals					// optional, force decal symmetry
--wrecks					// optional, force wreck symmetry
--civilians				// optional, force civilian symmetry
--terrain					// optional, force terrain symmetry
--debug						// optional, turn on debugging options
```

#### Rotation Code Examples
```java
java -jar MapTransformer-17.jar --debug --in-folder-path "InputMaps/setons_clutch_-_faf_version.v0001" --out-folder-path TransformedMaps --symmetry POINT2 --source 115 –all
```
```java
java -jar MapTransformer-17.jar --debug --in-folder-path "InputMaps/the_ditch_-_faf_version.v0001" --out-folder-path TransformedMaps --symmetry POINT2 --source BOTTOM_LEFT –all
```
#### Mirror Code Example
```java
java -jar MapTransformer-17.jar --debug --in-folder-path "InputMaps/serenity_desert_small_-_faf_version.v0002" --out-folder-path TransformedMaps --symmetry ZX --source TOP_LEFT –all
```


### 3.5.2 Manual Rotation / Mirror {#sec-3-5-2}

#### Preparations

- Create rotation/mirror strata/layer mask of `source` area or angle for usage in map editor.
- Create rotation/mirror setup for `source` area or angle in Worldmachine.

#### Heightmap

1. Export map `heightmap.raw`.
2. Rotate/mirror and heightmap in Worldmachine, Image editing Software.
   - Keep terrain issues at `source` area or angle axis in mind.
3. Import rotated/mirrored `heightmap.raw`.

#### Props (GPG-Editor)

1. Import rotation/mirror mask of `source` area or angle as strata/layer in map editor.
2. Delete props at opposite side of `source` area or angle.
3. Export props.
4. Import props.
   - Set the correct angle (opposite of `source` area or angle) while importing.
5. Realign props to terrain.
   - Use `STRG+A` to select all props, then delete them and press `STRG+Z` to undo it.

#### Marker (FAF-Editor)

1. Import rotation/mirror mask of `source` area or angle as strata/layer in map editor.
2. Set the correct symmetry in FAF-Editor. Select the marker on the `source` side and adjust the marker on the opposite side to the correct/marked position.
> **Note:** Marker refers to the content of the `_save.lua` file (see [2.2.3](#sec-2-2-3)).

![faf_version_manual_marker.jpg](/images/faf-version/faf_version_manual_marker.jpg)
*Image: [Seton's Clutch](https://forum.faforever.com/topic/398/faf-version-gpg-unknown-inactive-author-map-rework/5) - Manual marker rework.*

#### Strata / Layer

1. Export all map strata/layer.
2. Rotate/mirror strata/layer in Worldmachine, Image editing Software.
   - Keep coloring issues at `source` area or angle axis in mind.
3. Import rotated/mirrored strata/layer.

#### Decals (GPG-Editor)

1. Import rotation/mirror mask of `source` area or angle as strata/layer in map editor.
2. Delete decals at opposite side of `source` area or angle.
3. Export decals.
4. Import decals.
   - Rotate manually to the correct angle (opposite of `source` area or angle) after import while the decals are still selected.

> **Note:** Decals can currently only be mirrored with b2ag’s [scmap_mirror_tool](https://github.com/b2ag/scmap_mirror_tool).


## 3.6 Polish Map Files Content {#sec-3-6}

After implementing the `source` area or angle, it is necessary to polish the map files to eliminate issues and provide an up-to-date gaming experience.

> **Note:** Issues could be introduced while implementing the `source` area or angle. Pay special attention to the rotation/mirror axis.


### 3.6.1 .scmap {#sec-3-6-1}

Also see [2.2.1](#sec-2-2-1).

#### Map Preview (GPG-Editor)

After using the `MapTransformer`, it's necessary to create a new map `preview` because the changes are based on the `source` area or angle and not on the correct perspective and lighting. Saving the map will overwrite the `.scmap` file and generate a new map `preview`.

> **Notes:**
> - To preserve the original look of the map `preview`, it's recommended to save the `.scmap` file in the GPG-Editor `v56` map format (see [2.1.2](#sec-2-1-2)).
> - If the map contains a `skybox`, it is a Forged Alliance `v60` map. In this case, it's recommended to save the `.scmap` file only in the FAF-Editor as `v60` map format. Otherwise, the `skybox` content will be lost (see [2.1.3](#sec-2-1-3)). All Forged Alliance maps contain a individual `skybox`.

#### Heightmap (FAF-Editor)

Check/fix terrain issues at the rotation/mirror axis of the `source` area or angle.
- Example: The heightmap of [Forbidden Pass – FAF version](https://forum.faforever.com/topic/398/faf-version-gpg-unknown-inactive-author-map-rework/10) needed a terrain fix at the rotation line.

#### Strata / Layer (FAF-Editor)

Check/fix strata/layer mask issues at the rotation/mirror axis of the `source` area or angle.

- Example: The layer of [Forbidden Pass – FAF version](https://forum.faforever.com/topic/398/faf-version-gpg-unknown-inactive-author-map-rework/10) needed a strata/layer fix at the rotation line.

#### Props

Check/fix prop issues at the rotation/mirror axis of the `source` area or angle.

> **GPG-Editor Note:** If props need to be realigned to the terrain, follow step 3. If props need to be submerged and realigned to the terrain, follow steps 1-4:
> 1. Make note of the current water level.
> 2. Set the water level to `0`.
> 3. Realign props to terrain.
>    - Use `STRG+A` to select all props, then delete them and press `STRG+Z` to undo it.
> 4. Set the water level to its original value.

#### Decals (GPG-Editor)

Check/fix decal issues at the rotation/mirror axis of the `source` area or angle.

For a consistent visual experience, set the same `Cutoff Distance` value for all decals. This will ensure that they blend in and out at the same time. Use `STRG+A` to select all decals, then change the value according to map size:

| Map Size | Cutoff Distance	|
| ----------- | ----------- |
| 5x5 km | 1000 |
| 10x10 km | 2000 |
| 20x20 km | 3000 |
| 40x40km | 4000 |

> **Note:** See [2.2.1.1](#sec-2-2-1-1) Individual Assets.

### 3.6.2 _scenario.lua {#sec-3-6-2}

Also see [2.2.2](#sec-2-2-2).

#### Description

Add a similar `description` with a link to the forum channel:

```lua
description = "Dozens of battles have been fought over the years across Seton's Clutch. A patient searcher could find the remains of thousands of units resting beneath the earth and under the waves. - FAF version of the original FA map 'SCMAP_009': Ensures symmetrical heightmap, textures, decals, marker, props, and units. Contains improved AI marker. - Modified by FAF Creative: https://forum.faforever.com/topic/398/faf-version-gpg-unknown-inactive-author-map-rework"
```
```lua
description = "FAF version of the unknown author map 'Loki': Ensures symmetrical marker and props. Contains new AI marker. - Modified by FAF Creative: https://forum.faforever.com/topic/398/faf-version-gpg-unknown-inactive-author-map-rework"
```

<span style="background-color: yellow">What should be written instead of "FAF creative" in the future?</span>

#### Norush Radius

Add a reasonable `norushradius` if the value is `0`.

#### Norush Radius Offset

Adapt the `norushoffsetX/Y_ARMY_X` to changes.

> **Note:** The `norushoffsetX/Y_ARMY_X` can be deleted if the offset value is `0`.

#### ExtraArmies

See [2.2.2](#sec-2-2-2).


### 3.6.3 _save.lua {#sec-3-6-3}

Also see [2.2.3](#sec-2-2-3).

#### Marker (FAF Editor)

Check/fix marker issues at the rotation/mirror axis of the `source` area or angle.
Add, optimize and improve the AI marker.  <span style="background-color: yellow">Should AI marker be add, even if they get generated automatically now?</span>
> **Note:** Marker refers to the content of the `_save.lua` file (see [2.2.3](#sec-2-2-3)).

**Units and structures**
Pay special attention to the reclaim value, as well as the quantity of structures and units located at the rotation/mirror axis or in the middle of the map. Take note of the reclaim value, as well as the quantity of structures and units used in the original `source map version`. Ensure the units and structures are placed as closely as possible to the original in the `FAF version`. Try to ensure they match in reclaim value, placement, type and quantity, while considering the new `source` area or angle.

> **Note:** If a radar belongs to the `INITIAL` `NEUTRAL_CIVILIAN` group, ensure it has sufficient power to operate effectively.

![faf_version_syrtis_mid_structures_compare.png](/images/faf-version/faf_version_syrtis_mid_structures_compare.png)
*Image: [Syrtis Major](https://forum.faforever.com/topic/398/faf-version-gpg-unknown-inactive-author-map-rework/6) - Middle base*

![faf_version_units_structures_compare_arctic_refuge.jpg](/images/faf-version/faf_version_units_structures_compare_arctic_refuge.jpg)
*Image: [Arctic Refuge](https://forum.faforever.com/topic/398/faf-version-gpg-unknown-inactive-author-map-rework/36) - Middle base*

![faf_version_setons_mid_units_compare.png](/images/faf-version/faf_version_setons_mid_units_compare.png)
*Image: [Seton's Clutch](https://forum.faforever.com/topic/398/faf-version-gpg-unknown-inactive-author-map-rework/5) - Special middle units rework.*


#### Armies & ExtraArmies

See [2.2.3](#sec-2-2-3).

### 3.6.4 _script.lua {#sec-3-6-4}

See [2.2.4](#sec-2-2-4).

# 4 Test “Master Map Version” {#sec-4}
Testing the `Master Map Version` is a crucial step in ensuring its quality and functionality.

1. Once all changes are final, remove the `Editor Map Version` from the FAF maps path.
2. Copy the `Master Map Version` to the FAF maps path.
3. Test the created `Master Map Version` thoroughly in game to ensure:
   - That the map is working like intended.
   - That all map-related `issues` have been resolved (see [1.1](#sec-1-1)) and no new `issues` have been introduced.
     - Open the `Moho Log` by pressing `F9` and check for any additional issues.
   - That all `FAF version`-related requirements have been met (see [3](#sec-3)).
   - That structures can be built on every `resource marker`.
   - That `AI Markers` are working.
4. If necessary, make changes based on testing results and restart the process from step 1.


# 5 Review, Approval & Change Documentation {#sec-5}
Reviewing and documenting changes are essential steps in ensuring transparency and effective communication within the community


## 5.1 Document Prop Value Changes {#sec-5-1}

Use the FAF-Editor to retrieve the `prop values` for mass and energy of the original `source map version` and the `FAF version` map. Calculate the difference for discussion and documentation.

| Seton's Clutch - Prop Value | Mass	| Energy |
| ----------- | ----------- | ----------- |
| SCMP_009 (original v60 source map version) | 36.525,34 | 333.853,70 |
| FAF version (v0001, 115° source angle) | 37.814,32 | 336.974,80 |
| Difference | 288,98| 3.121,10 |

## 5.2 Review & Approval {#sec-5-2}

Present the `FAF version` to the ladder team, Team Match Maker (TMM), and the issue reporter to review and test the changes (see [3.2](#sec-3-2)). Before proceeding, ensure that you have received approval for the following:
Changes in prop value and marker placement, ...
- changes in `prop value` (see [5.1](#sec-5-1))
- changes in `marker` placement
- requirements of [4.3](#sec-4)

> **Note:** To make the map accessible prior to uploading it to the `FAF Vault`, create a zip file from the `Master Map Version` folder and upload the zip file to the Matchmaker-submissions Discord channel (see [3.2.2](#sec-3-2-2)). This allows others to access and review the map before it is officially uploaded.

## 5.3 Change Documentation {#sec-5-3}
Comprehensive documentation is crucial for maintaining a record of changes and facilitating future issue tracking.

1. **Individual Map Issue Documentation**
Document version related changes in `Individual Map Issue Documentation` for future documentation and issue tracking (see [1.1](#sec-1-1)).
<span style="background-color: yellow">Where should it be documented in the future, currently i got [this](https://ethercalc.net/kkn2yatyf4wq).</span>
2. **Forum Post**
Explain map changes in one [forum post](https://forum.faforever.com/topic/398/faf-version-gpg-unknown-inactive-author-map-rework) in a clear and concise manner for documentation (in case issues arise from changes) and to inform the community about the changes made to the map. Provide detailed and issue-related information about the values that have been changed. This ensures that the community is fully informed about the changes made to the map and can provide feedback accordingly.

> **Note:** Keep the `Individual Map Issue Documentation` and the corresonding `Forum Post` up to date whenever a new map version is uploaded the the `FAF Vault`.

# 6 Map Upload Process {#sec-6}
The map upload process is the final step in making the `FAF version` map available to the FAF community. It involves preparing the map files, adjusting the folder and file paths and uploading the map to the `FAF Vault`.

To prevent the occurrence of the `DOUBLE MAP_VERSION_STRING` (see [6.1.](#sec-6-1)) error, it is essential to remove the `.v000X` from both the folder and file paths prior to uploading. This is because the map file paths for all map files will be automatically generated during the upload process, using the selected `FOLDER_NAME` and the `map_version` specified in the `_scenario.lua` file.
<span style="background-color: yellow">Is that true or is the name from the scenario.lua used? If FOLDER_NAME, would it be enough, to only change the folder name and leave the map file path unchanged?</span>


1. Copy the final `Master Map Version` folder to a separate directory.
2. Remove the `MAP_VERSION_STRING` `.v000X` from the `FOLDER_NAME`.
```lua
--INPUT
MAP_VERSION_STRING = '.v0001'
FOLDER_NAME = 'setons_clutch_-_faf_version.v0001'
```
```lua
--RESULT
FOLDER_NAME = 'setons_clutch_-_faf_version'
```
3. Remove the `MAP_VERSION_STRING` `.v000X` from the map file path in `_scenario.lua` and `_script.lua` (if present).

> **Note** The `.scmap` file does not require any modifications. It remains unchanged throughout the upload process. <span style="background-color: yellow">Is that true?</span>

```lua
--INPUT
MAP_VERSION_STRING = '.v0001'
map = '/maps/setons_clutch_-_faf_version.v0001/setons_clutch_-_faf_version.scmap',
save = '/maps/setons_clutch_-_faf_version.v0001/setons_clutch_-_faf_version_save.lua',
script = '/maps/setons_clutch_-_faf_version.v0001/setons_clutch_-_faf_version_script.lua',
```
```lua
--RESULT
map = '/maps/setons_clutch_-_faf_version/setons_clutch_-_faf_version.scmap',
save = '/maps/setons_clutch_-_faf_version/setons_clutch_-_faf_version_save.lua',
script = '/maps/setons_clutch_-_faf_version/setons_clutch_-_faf_version_script.lua',
```
4. Select the renamed folder with the adapted file path during the upload process.
5. If the upload is successful, delete the `Editor Map Version` or `Master Map Version` from the FAF map path.
6. Download the newly uploaded map.
7. Test the map to ensure it is working as intended (see [4](#sec-4)).


## DOUBLE MAP_VERSION_STRING ERROR {#sec-6-1}
When the `MAP_VERSION_STRING` `.v000X` is not removed from both the folder and file paths before uploading, it triggers the `DOUBLE MAP_VERSION_STRING` error. This results in the duplication of the `MAP_VERSION_STRING` (`.v000X.v000X`), leading to an incorrect file path and an unplayable map version.

### Bad GPG Map Senario Example {#sec-6-1-2}
```lua
--INPUT
FOLDER_NAME = 'setons_clutch_-_faf_version.v0001'
map_version = 1
MAP_VERSION-STRING = '.v0001'
map = '/maps/setons_clutch_-_faf_version.v0001/setons_clutch_-_faf_version.scmap',
save = '/maps/setons_clutch_-_faf_version.v0001/setons_clutch_-_faf_version_save.lua',
script = '/maps/setons_clutch_-_faf_version.v0001/setons_clutch_-_faf_version_script.lua',
```
```lua
--RESULT AFTER UPLOAD ('.v0001.v0001')
version = 3 -- Lua Version. Dont touch this
ScenarioInfo = {
    name = 'Setons Clutch - FAF version',
    ...
    map_version = 1,
    ...
    map = '/maps/setons_clutch_-_faf_version.v0001.v0001/setons_clutch_-_faf_version.scmap',
    save = '/maps/setons_clutch_-_faf_version.v0001.v0001/setons_clutch_-_faf_version_save.lua',
    script = '/maps/setons_clutch_-_faf_version.v0001.v0001/setons_clutch_-_faf_version_script.lua',
```

### Bad Adaptive Map Script Example {#sec-6-1-2}
```lua
--INPUT
FOLDER_NAME = 'adaptive_monument_valley.v0005'
map_version = 5
MAP_VERSION-STRING = '.v0005'
local Tables = import('/maps/adaptive_monument_valley.v0005/adaptive_monument_valley_tables.lua')
```
```lua
--RESULT AFTER UPLOAD ('.v0005.v0005'):
------------------------------------------------------------------------
----- Script by CookieNoob and KeyBlue (modified by svenni_badbwoi)-----
------------------------------------------------------------------------
...
local Tables = import('/maps/adaptive_monument_valley.v0005.v0005/adaptive_monument_valley_tables.lua')
...
```















   
