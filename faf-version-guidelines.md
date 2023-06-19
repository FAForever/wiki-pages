---
title: FAF version - Mapping Guidelines
description: GPG, unknown & inactive author map rework
published: true
date: 2023-06-19T22:22:31.122Z
tags: mapping, guidelines, advanced, faf_version
editor: markdown
dateCreated: 2023-06-19T22:22:31.122Z
---

# 1 Introduction {#sec-1}
Greetings everybody,
the goals of the `FAF version` maps are fair / balanced gaming conditions and an improved / up-to-date gaming experience. To ensure the goals are met, these `Mapping Guidelines` were created.

> **IMPORTANT NOTES:**
> - **Map upload of approved content stays in the hands of <span style="background-color: yellow">FAF Creative staff / authorized FAF map maker</span>! Don't upload any `FAF version` map without authorization!**
> - **If you can’t meet the requirements mentioned in this document, you are not qualified / allowed to create and upload a `FAF version` map.**
> - **Adaptive maps and maps with individual assets are even harder to rework and require a total understanding of all dependencies.**

## 1.1 Community Support {#sec-1-1}
Have you ever found yourself frustrated by unbalanced heightmaps or unevenly distributed marker, props and units in the following maps:
- [Gas Powered Games (GPG) maps](https://ethercalc.net/0ds9j65h5wrr)
- Supreme Commander and Forged Alliance stock maps included in the original game
- Unknown author maps
- Inactive author maps


You are welcome to inform us about map issues here:
- [Forum (svenni_badbowi)](https://forum.faforever.com/topic/398/faf-version-gpg-unknown-inactive-author-map-rework)
- [Ticket System]() <span style="background-color: yellow">Add Link to ticket system</span>


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
The GPG-Editor REMOVES the `reclaim` value from `_scenario.lua`. The `reclaim` value is a feature of the FAF-Editor.

### 2.1.3 FAF-Editor {#sec-2-1-3}
The FAF-Editor can read and save Supreme Commander `v56` and Forged Alliance `v60` map versions.

> **Note:**FAF-Editor can be used to save a `v60` map in `v56` format to be able to edit the map in the GPG-Editor. Keep in mind that the `skybox` and other content gets lost while re-saving a `v60` map as `v56` format.

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
The `MapTransformer` by Sheikah is the recommended tool to recreate the map based on the `source` map version and `source` area or angle. You can request the latest version of the `MapTransformer` from Sheikah through a personal message. Usage see [3.5.1](#sec-3-5-1).

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

#### Individual Assets

Individual assets such as paths to prop or decal are hard-coded in the `.scmap` file. The path / version needs to be adapted, otherwise assets are missing or only loading when the original map is still in the` maps folder.

- **Changed map name / path**
  - Change path in map editor or replace asset

- **Changed map version**
  - Open `.scmap` file in binary / hex editor (Visual Studio Code, Okteta, ...) and change version `.v000X`
  
  

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
      ```
      armies = {'ARMY_1', 'ARMY_2', 'ARMY_3', 'ARMY_4', 'ARMY_5', 'ARMY_6', 'ARMY_7', 'ARMY_8'}
      ['ExtraArmies'] = STRING( 'ARMY_9 NEUTRAL_CIVILIAN' )
      ```
    - Other maps need `ARMY_17` and `NEUTRAL_CIVILIAN`. The player count is limited to 16 `Armies`.
      ```
      armies = {'ARMY_1', 'ARMY_2', 'ARMY_3', 'ARMY_4', 'ARMY_5', 'ARMY_6', 'ARMY_7', 'ARMY_8' ,'ARMY_9', 'ARMY_10', 'ARMY_11', 'ARMY_12', 'ARMY_13', 'ARMY_14', 'ARMY_15', 'ARMY_16'}
      ['ExtraArmies'] = STRING( 'ARMY_17 NEUTRAL_CIVILIAN' )
      ```
      <span style="background-color: yellow">Or should it be ARMY_17 in GPG map rework as well?</span>
#### Result / Settings (FAF-Editor) {#sec-2-2-2-1}
<span style="background-color: yellow">Add Image</span>

#### Example _scenario.lua {#sec-2-2-2-2}
```
version = 3 -- Lua Version. Dont touch this
ScenarioInfo = {
    name = 'Setons Clutch - FAF version',
    description = 'Dozens of battles have been fought over the years across Seton's Clutch. A patient searcher could find the remains of thousands of units resting beneath the earth and under the waves. - FAF version of the original Forged Alliance map "SCMAP_009": Ensures symmetrical heightmap, textures, decals, marker, props and units. Contains improved AI marker. - Modified by FAF Creative: https://forum.faforever.com/topic/398/faf-version-gpg-unknown-inactive-author-map-rework',
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

> **Note:** Changes to scripted maps like adaptive maps, require an understanding of all scripted dependencies e.g. army related mex spawning in `_options.lua`.

#### NEUTRAL_CIVILIAN {#sec-2-2-3-1}

Living `NEUTRAL_CIVILIAN` units and structures should be placed in `INITIAL` group. They need a radar and enough power to work properly. Dead units and structures should be placed in `WRECKAGE` group.

#### Armies & ExtraArmies {#sec-2-2-3-2}

Every playable `ARMY_X` needs an `INITIAL` Group at `Units`. `ExtraArmies` like `ARMY_9` or `ARMY_17`  and `NEUTRAL_CIVILIAN` need an `INITIAL` & `WRECKAGE` Group at `Units`. Check dependency in `_scenario.lua` (see [2.2.2](#sec-2-2-2)).

> **Note:** This is needed for some mods to work. <span style="background-color: yellow">Is that true?</span>

#### Results / Settings (FAF-Editor)
<span style="background-color: yellow">Add Image</span>

### 2.2.4 _script.lua {#sec-2-2-4}

It's a plain text file that contains LUA code. Changes can be performed with a text editor.

The file holds the following information:
- <span style="background-color: yellow">how the map starts / behaves</span>

> **Note:**
> - There is no need to change the file content (except filename) while reworking GPG (Supreme Commander and Forged Alliance) maps.
> - Some maps (e.g. adaptive maps) have a map folder and file reference in the `_script.lua`. Make sure to update the path as well.

#### Example _script.lua {#sec-2-2-4-1}
```
local ScenarioUtils = import('/lua/sim/ScenarioUtilities.lua')

function OnPopulate()
	ScenarioUtils.InitializeArmies()
end

function OnStart(self)
end
```

## 2.3 Map Issues {#sec-2-3}

A lot of map-specific issues are already documented. Get familiar with the open map-specific issues for optimal map rework results.

### 2.3.1 Documented Issues

Check what issues are already documented or fixed.
- [Forum (svenni_badbwoi)](https://forum.faforever.com/topic/398/faf-version-gpg-unknown-inactive-author-map-rework)
- [Forum (new)]() <span style="background-color: yellow">add link</span>

### 2.3.2 New Issues

If the issue is not documented or fixed yet, add a [new ticket]() (<span style="background-color: yellow">add ticket system link</span>) for later tracking and documentation.

### 2.3.3 Issues In Game

Check the issues in game.

## 2.4 Check Other FAF Version Maps {#sec-2-4}

Download other `FAF version` maps maps from the vault and get familiar with the requirements.

> **Note:**
> `FAF version` maps created by svenni_badbwoi are based on this Mapping Guidelines.


## 3 Create FAF version {#sec-3}

### 3.1 Get Source Map Version {#sec-3-1}

**If the source of the `FAF version` is a GPG map, Forged Alliance `v60` maps should always be used. The Forged Alliance `v60` maps are further developed (e.g. skybox, different units, ...) compared to the Supreme Commander `v56` ones.**

- skirmish maps
Official GPG skirmish map folder and files are called `SCMP_0XX` (`v56` and `v60`). `X1MP_0XX` are additional Forged Alliance `v60` skirmish maps.
- campain maps
`SCCA_XXX` are Supreme Commander `v56` and `X1CA_0XX` are Forged Alliance `v60` campaign maps.

> **Note:**
> GPG named the map folder and map name differently.

#### 3.1.1 Supreme Commander (v56 | GPG-Editor) maps path

Default GPG path: `\Gas Powered Games\Supreme Commander\maps`  
Default Stream path: `/steam/steamapps/common/Supreme Commander/maps`

#### 3.1.2 Forged Alliance (v60) maps path

Default GPG path: `\THQ\Gas Powered Games\Supreme Commander - Forged Alliance\maps`
Default Stream path: `/steam/steamapps/common/Supreme Commander Forged Alliance/maps`
https://api.faforever.com/maps/validate
#### 3.1.3 Forged Alliance Forever (v56 and v60) maps path

Needed for testing or if a map from unknown or inactive author has been downloaded from the FAF Vault as the source map.

Default FAF path: `/My Games/Gas Powered Games/Supreme Commander Forged Alliance/maps/`

#### 3.1.4 Example source map version

Different units/structure placement and count between Supreme Commander `v56` and Forged Alliance `v60` map versions.
<span style="background-color: yellow">add image</span>



## 3 Create FAF version {#sec-3}

### 3.2 Find Source Area / Angle {#sec-3-2}

For a balanced `FAF version` of the map, it is crucial to correctly identify the `source` area or angle. The `source` marks the map content that will be used for the `FAF version` rework.
If the map issue doesn't dictate a specific `source` area or angle (e.g. remove heightmap difference at map bottom > `source = TOP`), the `source` needs to be found/discussed.

> **Note:** In some cases, a different `source` area or angle was used to rework the heightmap and props differently.

#### 3.2.1 Prepare Discussion {#sec-3-2-1}

To prepare the discussion, one of the following steps is advisable:
- Export `heightmap.raw` and create a 360° rotation/mirror video to discuss the `source` area or angle.
    - Worldmachine Template
- Create and test a few `source` area or angle options with the `MapTransformer` and compare the results.
    - Terrain issues at `source` area or angle.
    - Differences in `prop` count and `marker` placement, ...

#### 3.2.2 Discuss Source Area / Angle {#sec-3-2-2}

Discuss/Collaborate with the ladder team, Team Match Maker (TMM), and the issue reporter to determine the optimal `source` area or angle based on the preparations (see [3.2.1](#sec-3-2-1)). Please create a thread in the following channel on Discord:
- Official Forged Alliance Forever Discord
    - [Matchmaker-submissions](https://discord.com/channels/197033481883222026/832707438443626596)

#### 3.2.3 Example {#sec-3-2-3}

In the case of the `Setons Clutch – FAF version`, we agreed on a `source` angle of 115°(white area was used). See [forum post](https://forum.faforever.com/topic/398/faf-version-gpg-unknown-inactive-author-map-rework) for more examples.
<span style="background-color: yellow">add image</span>

### 3.3 Set up new map name, files, version, folder & file path {#sec-3-3}

While creating a new map, it is important to set up the folder, files, and file path according to the map name (see `_scenario.lua` Example and already uploaded `FAF version` maps). Copy the `source map version` folder to the `Master Map Version` folder (see [3.4](#sec3-4)) and make the following adjustments manually.

> **Note:** Manual adjustment is recommended at this step to ensure that the changes are made correctly. Re-saving the map with a different `name` will change the original content!

#### 3.3.1 New Map Name {#sec-3-3-1}

Derive the new map name from the original map `name` in `_scenario.lua` and change it accordingly:
- Capitalize the first letters of the original map `name`.
- Special characters (except `-`) are not allowed.
    - Also see:
        - Map `name` and `_scenario.lua` content validation [page](https://api.faforever.com/maps/validate).
        - [FAF Vault Rules](https://wiki.faforever.com/en/Development/Vault/Rules).
- Add the suffix ` - FAF version` to get the final map name.
<span style="background-color: yellow">Should “FAF Version” be allowed as well?</span>

##### Examples
```
name = 'map name',
name = 'Map Name - FAF version',

name = 'Seton’s Clutch',
name = 'Setons Clutch - FAF version',
```


#### 3.3.2 New Map File Names {#sec-3-3-2}

Derive the `FILE_NAME` from the new map `name` and change the map file names accordingly:
- All characters need to be lowered (`A` becomes `a`).
- White-spaces (` `) need to be replaced with an underscore (`_`).


##### Example
```
name = 'Setons Clutch - FAF version'
FILE_NAME = 'setons_clutch_-_faf_version'

scmap = 'setons_clutch_-_faf_version.scmap'
scenario = 'setons_clutch_-_faf_version_scenario.lua'
save = 'setons_clutch_-_faf_version_save.lua'
script = 'setons_clutch_-_faf_version_script.lua'
```

#### 3.3.3 New Map Version {#sec-3-3-3}

Add the correct `map_version` to the `_scenario.lua` file. The value `map_version` was implemented by FAF and is needed for versioning/upload.

> **Note:** The first version of a map should be number `1`.

##### Example
```
map_version = 1,
```

#### 3.3.4 New Map Folder Name {#sec-3-3-4}

Create `FOLDER_NAME` (from `FILE_NAME` and `map_version`) and rename the map folder accordingly.

##### Pattern
`FOLDER_NAME` = `FILE_NAME` + `MAP_VERSION_STRING`

##### Example
```
official_folder_name = 'SCMP_009'
map_version = 1,
MAP_VERSION_STRING = '.v0001'
FILE_NAME = 'setons_clutch_-_faf_version'

FOLDER_NAME = 'setons_clutch_-_faf_version.v0001'
```

#### 3.3.5 New File Path {#sec-3-3-5}

Set the path according to the new map `FILE_NAME` and `FOLDER_NAME` in the `_scenario.lua` file.

> **Note:** Some maps (e.g. adaptive maps) have a map file reference in the `_script.lua`. Make sure to update that path as well.

##### Pattern
```
map = '/maps/FOLDER_NAME/FILE_NAME.scmap',
save = '/maps/FOLDER_NAME/FILE_NAME_save.lua',
script = '/maps/FOLDER_NAME/FILE_NAME_script.lua'
```

##### Example
```
name = 'Setons Clutch - FAF version',
map_version = 1,

map = '/maps/setons_clutch_-_faf_version.v0001/setons_clutch_-_faf_version.scmap',
save = '/maps/setons_clutch_-_faf_version.v0001/setons_clutch_-_faf_version_save.lua',
script = '/maps/setons_clutch_-_faf_version.v0001/setons_clutch_-_faf_version_script.lua'
```

#### 3.3.6 Validate Map Metadata {#sec-3-3-6}

Use the validate map metadata [web-page](https://api.faforever.com/maps/validate) to validate the map `name` and `_scenario.lua` content.

#### 3.3.7 Test Map {#sec-3-3-6}

Test the map in-game before you proceed with the next step.


### 3.4 Create Editor & Master Map Version Folder {#sec-3-4}

To streamline the process and maintain backups of the latest changes, it is recommended to create an `Editor Map Version` and `Master Map Version` in different directories. This ensures that only necessary and tested changes/files are transferred to the final version of the `FAF version` map.

> **Note:** To ensure that work is always being done on the latest version of the map, it's important to regularly replace the `Editor Map Version` with the `Master Map Version` folder.

#### 3.4.1 Editor Map Version – FAF Maps Folder {#sec-3-4-1}

The `Editor Map Version` folder represents the work in progress as well as test version of the map. The `Editor Map Version` folder needs to be placed in the required map folder (simply copy the folder created in [3.3](#sec-3-3) into the required directory, see [3.1](#sec-3-1)). The benefits of the `Editor Map Version` are, it can be edited, saved, destroyed or deleted without affecting the `Master Map Version` backup. 

> **Note:** All changes that require the map editor or `MapTransformer` should be made in the `Editor Map Version` folder.

#### 3.4.2 Master Map Version - Project Folder {#sec-3-4-2}

The `Master Map Version` folder is used to store, test and discuss final results and during the Map Upload Process. The `Master Map Version` should be placed in a separate project directory outside the FAF environment. The content of the `Master Map Version` will be updated by copying the tested necessary files (e.g. `.scmap` or `_save.lua`) from the `Editor Map Version` folder and replacing the files in the `Master Map Version` folder. This way, only relevant changes are transferred and the `Master Map Version` serves as a backup of the latest version of the map. It is not recommended to overwrite all files or to save the `Master Map Version` in a map editor, as this could result in unintended changes to the original content. Simply copy & replace `.scmap` if a new map preview was created / `_save.lua` if marker where changed (see [2.2](#sec-2-2)).

> **Note:** The `_scenario.lua` content as well as the default quotation mark settings will be changed while using different map editors. It's good practice to finalize the `_scenario.lua` in the `Master Map Version` folder.










   
