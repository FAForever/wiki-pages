---
title: FA-Forever-Map-Editor
description: 
published: true
date: 2021-10-07T20:18:35.671Z
tags: 
editor: markdown
dateCreated: 2021-08-31T09:42:58.014Z
---

![faf_mapeditor_logo.png](/faf_mapeditor_logo.png)
## Introduction
**FA Forever Map Editor** is a new map editor developed for FAF by ozonex. It is currently in **alpha**, which means the editor is in its testing phase, and some features are still lacking. However, ozonex expects to release a beta version soon.

FA Forever Map Editor Github [Issuse's](https://github.com/ozonexo3/FAForeverMapEditor/issues).

### Download

You can download the current version [here](https://github.com/ozonexo3/FAForeverMapEditor/releases).

### Video tutorials

[Spy Emanciator Map Editor Playlist](https://www.youtube.com/playlist?list=PLcbl0rrn9re5hsfVOayFJAT-05OAUvz7Q) (does not include AI Marker Tutorial)

## Setting up the editor

Before using the editor you need to set up your preferences.

![faf_mapeditor_preferences.png](/faf_mapeditor_preferences.png)

### Preferences
Before loading any map you must specify the paths to your game and maps folder.

- **Sup Com Forged Alliance installation path** - Path to where the game is installed. It will also work with vanilla Supreme Commander, but always use Forged Alliance to get access to all the new assets. Use **"..."** to open folder browser. When using **Default** button editor will try to find the path by itself.
- **Maps folder path** - Path to where all maps are stored. The Alpha version can only load maps from that folder, so if you have maps in a different folder, you need to change this path or move the maps to the specified folder.
- **Backup folder** - Path where backups of old maps files will be moved. If empty, backups will be saved in *FAForeverMapEditor_Data/MapsBackup/*.
- **Undo steps** - Maximum number of steps saved in memory for Undo and Redo.
- **Play map** - Settings for using *File/Play map*. You can select a **faction** and disable **Fog of war**.
- **Markers 2D** - This will scale markers up when they camera is away. Use this feature to better see all markers on the map. 
- **Heigtmap brush Clamp** - This will not allow for painting higher or lower than 50 units from lowest/highest point on the map to prevent "black plane bug". This bug has been fixed for FAF so this is no longer required
- **UI Scale** - Change scale of editors UI

### Editor LOG

When the editor crashes or behaves in strange way it may be useful to send log to the developer. You can find them here:

`   C:/Users/[user]/AppData/LocalLow/ozonexo3/FAF Map Editor/`

### Custom brushes

You can create or modify existing brushes used by the FAF Map Editor. Brushes need to be 512px x 512px grayscale PNG without an alpha channel. When opened, the editor will load all brushes from that folder. Brushes are sorted alphabetically.

You can find them in:

`   [FAForeverMapEditor.exe path]/FAForeverMapEditor_Data/Structure/brush/`

### Symmetry

The editor supports several symmetry options for editing maps. You need to select the right one before making changes to the map, because everything you do will be symmetrical based on selected settings. To open symmetry settings go to *Symmetry/Symmetry settings...*.

Tolerance is how far in game units the editor will search for symmetrical objects when selected. Matching objects will be selected as orange. If it can't find a matching object it will display a gray selection where it should be.

| Setting                            | Symmetry effect                                                                                                                                                                                                                                                                                                                                                                              |
|------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| X                                  | Mirrors items on the left side of the map to the right side                                                                                                                                                                                                                                                                                                                                  |
| Z                                  | Mirrors items on the top of the map to the bottom of the map                                                                                                                                                                                                                                                                                                                                 |
| X + Z                              | Mirrors top to bottom and left to right (or the reverse)                                                                                                                                                                                                                                                                                                                                     |
| Diagonal (Top Left + Bottom Right) | Mirrors the top left to bottom right (and reverse)                                                                                                                                                                                                                                                                                                                                           |
| Diagonal (Bottom Left + Top Right) | Mirrors the bottom left to top right (and reverse)                                                                                                                                                                                                                                                                                                                                           |
| Diagonal + Diagonal                | Similar to X+Z except it mirrors on the diagonals/                                                                                                                                                                                                                                                                                                                                           |
| Center by angle (2-16)             | This mirrors directly to the opposite side through the middle of the map. Rotation steps indicates how many units will be placed. For example, 2 will only place the one you have and one mirrored. 4 will place the one you have and three more. For example, with a rotation of 4: If you place a unit in the South East, it will place one in the North East, South West, and North West. |
|                                    |                                                                                                                                                                                                                                                                                                                                                                                              |


## Useful shortuts

| Key                   | Function                                                                                                                           |
|-----------------------|------------------------------------------------------------------------------------------------------------------------------------|
| W                     | ![faf_mapeditor_movetool.png](/faf_mapeditor_movetool.png) Switch to Move tool         |
| E                     | ![faf_mapeditor_rotatetool.png](/faf_mapeditor_rotatetool.png) Switch to Rotate tool |
| R                     | ![faf_mapeditor_scaletool.png](/faf_mapeditor_scaletool.png) Switch to Scale tool     |
| T                     | ![faf_mapeditor_snaptogrid.png](/faf_mapeditor_snaptogrid.png) Toggle snap to grid   |
| Left Control + C      | Copy selection                                                                                                                     |
| Left Control + V      | Paste copied content                                                                                                               |
| Left Control + D      | Duplicate selected objects                                                                                                         |
| Left Shift            | Smooth brush, Add selection                                                                                                        |
| Left Alt              | Invert brush, Erase, Unselect                                                                                                      |
| B + LMB or W + LMB    | Dragging over terrain will change brush size                                                                                       |
| V + LMB or S + LMB    | Dragging over terrain will change brush strength                                                                                   |
| Q or +                | Increase brush target value                                                                                                        |
| A or -                | Decrease brush target value                                                                                                        |
| TAB                   | Next brush type                                                                                                                    |
| 1, 2, 3, 4            | Select brush type                                                                                                                  |
| CTRL + LMB            | Sample target height for heightmap brush (pipette)                                                                                 |
| CTRL + RMB            | Sample minimum height for heightmap brush (pipette)                                                                                |
| CTRL + MMB            | Sample maximum height for heightmap brush (pipette)                                                                                |
| Shift + Select        | Add to selection                                                                                                                   |
| Left Alt + Select     | Remove from selection                                                                                                              |
| Home                  | Restart camera                                                                                                                     |
| Delete                | Remove seleted objects                                                                                                             |
| C                     | Connect selected AI Markers                                                                                                        |
| D                     | Disconnect selected AI Markers                                                                                                     |
| H                     | Hide selected decal types                                                                                                          |
| Shift + H             | Unhide selected decal types                                                                                                        |
| Left alt + V/H button | Toggle visibility of other layer/decal                                                                                             |
| P                     | Parent selection to group                                                                                                          |

## Create a new map
To create new map use *File/New Map*.
![faf_mapeditor_newmap.png](/faf_mapeditor_newmap.png)

- **Name** - Name of the map. This will be also used to name folders and files. See below for correct map naming conventions.
- **Description** - Long description of the map. You can describe the history of the map here.
- **Texture set** - Set of stratum textures loaded to new map. If you know how do you want your map to look like, then select best set.
- **Type** - Type of map. Use Skirmish for Multiplayer maps
- **Width** / **Height** - Size of the map. When selected sizes are not square editor will create square map and clip it using Area.
- **Initial height** - Initial height of whole heightmap. Try to use the lowest value possible, but remember to leave some space if you want to have water on the map.
- **Water** - Toggle it on if you want to have water on your map. This can be changed later if you change your mind.
	- **Water Elevation** - the height at which the water level is.
	- **Depth Elevation** - the height at which the water is darker.
	- **Abyss Elevation** - the height at which the water is very dark.

New map created in FAF Map Editor will be saved as:

`[MapsFolder]/[MapName].v0001/[files]`

**How you should you name maps:**

Editor fix map folder and file names, but you should still remember how that works.

Ignoring your map folder name, after uploading to vault, the map folder will be renamed according to the map name, but with spaces replaced with '_'. For example: A map's name is "Yet Another Gap". And map files are named "yetanothergap_scenario.lua", etc. The map will be uploaded to the vault and will be playable, but every time someone tries to host it from FAF, not from lobby settings, the Four-Corners map will be hosted instead. This bug will annoy people and prevent your map from being added to ladder pool. It happens because the mapbfolder will be renamed to "yet_another_gap.v0666" and FAF will search for yet_another_gap_scenarion.lua.

So a proper map should be named like this:
*maps/good_map.v0001/good_map_scenario.lua*

## Basic map settings
![fafmapeditor_map_scenario.png](/fafmapeditor_map_scenario.png)
Can be found in *Map/Scenario* menu.

- **Name** - Map name displayed in game
- **Description** - Long description of the map. You can describe the history of the map here. Displayed in game when selecting maps.
- **Version** - Version of the map. Should not be changed manually. To create next version, for upload to vault, click *File/Save as new version*.

### Edit Armys Spawn IDs

Tool for changing order of existing armies. Army order is also order of spawn points. Tool also have Auto-Team preview. To switch armies click on box with army number and then select other army from dropdown list.

### File version

Scmap file format exist in 2 versions:

- **v56** - Vanilla Supreme Commander map. Most old maps are in this format, because this is how the official map editor saves them.
- **v60** - Forged Alliance map. This is a new format version containing additional procedural skybox. Can't be opened by old tools or by the vanilla Supreme Commander game.

If you need to open **v60** map in vanilla or old tools, you can export skybox data to file and save it as **v56**. When done, you can import the skybox again and save as **v60**.

## Terrain Heightmap

The heightmap is the base of whole terrain. It defines height for every place on the map. You can use built-in tools to edit it, or export/import to work with other software. 

### Heightmap brush
![fafmapeditor_terrain_heightmap_brush.png](/fafmapeditor_terrain_heightmap_brush.png)
- **Brush size** - Size of the brush that we want to paint with. You can change it by holding down the **B** key and dragging over ''game view'.
- **Brush strength** - Strength with which brush changes are applied to terrain. You can change it by holding down the **V** key and  dragging over ''game view'.

There are 4 types of brush

-   **Standard** - Simple brush for increasing or decreasing terrain height
-   **Flatten** - Finds the average height under brush and moves terrain to that height. Best used as a strong blur.
-   **Blur** - Smooths the terrain. Good for removing sharp edges and softening the terrain.
-   **Sharpen** - Increase difference in height.

Additional values

-   **Target height** - Target terrain height for Standard brush. When painting it will change height into the target height. Useful for smooth translation into chosen height.
-   **Min height** - Minimum terrain height allowed by the brush. Terrain will be clipped when it's under that value.
-   **Max height** - Maximum terrain height allowed by the brush. Terrain will be clipped when it's above that value.
-   **Rotation** - Rotation of brush texture. Useful for some custom brushes like mountains.

Brush **shape** are brush images loaded from Structure/Brush folder. Read more here: [Custom brushes](FA_Forever_Map_Editor#Custom_brushes "wikilink")

### Heightmap tools
![fafmapeditor_terrain_heightmap_brush.png](/fafmapeditor_terrain_heightmap_brush.png)
-   **Set terrain height** - Change height of whole terrain to the chosen value.
-   **Add height** - Move heightmap up or down by the chosen value. Positive value will move it up, negative will move it down.
-   **Export in size** - Will export heightmap in different width and height. Useful for transfering heightmap between maps of different Size. It can also scale height values when selecting **Scale Height**.

### Export & Import

You can export and import heightmap as \*.raw file. It's 16bit texture, that can be edited in many graphic programs like Photoshop. There is also support for **\*.r16** files from **World Machine** (and other apps that supports this format like **Krita**) You can also import **\*.bmp** images, but they are usually 8 bit, so they lost data. Heightmap resolution should be always *MapSize* + 1, because it require one more vertex data, to create grid cell. For example 256x256 map will have heightmap with resolution 257x257. The correct settings for importing into Photoshop is channel count 1, Depth 16-bits, and byte-order IBM PC.

### Black plane bug

In Forged Alliance there is known bug, that lower parts of your map will become black. It happen, when height difference between the lowest and the highest point is bigger than 50.

There are 2 ways to fix it:
-   Reduce mountains height or depth of water
-   Add very deep hole somewhere in the map

## Water

Water settings can be found under **Terrain/Water** menu.

You can turn water on or off on your map. If you don't want to have water, then try to remember to disable it.

Water level is defined by **Water Elevation** value. **Abyss Elevation** define where water will have the darkest color. These 2 valus are the main water settings you need to remember about. **Depth Elevation** don't do much, but need to be between Water and Abyss elevation.

**Surface Color** allow you to change colors of the water. **Sun Color** is color of sun reflections on the surface.

### Water Material

-   Water color depth - Change of water depth for water color. The deeper the water is, the strongest color it has.
-   Water color lerp - How strong water color is applied. 
-   Sun Shininess - Secularity of the sun
-   Fresnel Power - Distribution of on what angle water will lets out the light thru under it, and when block it by reflected light. Low values will give low transparency of the water.
-   Fresnel Bias - Offset of dept for fresnel
-   Refraction scale - How strong refract light
-   Unit Reflection - How strong units reflect from surface of the water
-   Sky Reflection - Strength of sky reflection

## Terrain Type

Terrain types can be painted by going into the TERRAIN \> TYPE menu.

Terrain type is definition of what kind of terrain is over each areas. This is used for particle effect like dirt under walking units. Some layers (like lava) don't allow units to walk there, so can be used to block movement over certain areas.

To change area first select area you want to paint from the list on the left and then just paint it. You can change brush size. Types can't be blended together, only one type can be chosen per 1 game unit cell.

## Terrain Textures

Textures define colors of your map. Game allows you to chose from many textures for many different biomes. Remember that the appearance of the texture depends on the lighting setting.

### Texture layers
![fafmapeditor_textures_layers.png](/fafmapeditor_textures_layers.png)
There are total of 10 layers
-   Lower - is the lowest, base layer, that is visible, when nothing else is painted
-   Layers 1-4 - Default painting layers. You can assign same textures like for Lower and paint them over terrain
-   Layers 5-8 - Additional layers. They work only on XP shader. To enable them go to **Settings** tab and select **TTerrainXP** shader.
-   Upper - Overall layer with transparent noise texture. Don't change it if you don't know what you are doing!

Small **V** button allow you to temporary hide texture from. It will change to **H** if layer is hidden.

Always start texturing from the bottom. Begin from selecting lower stratum, and then go up staring from layer 1.

Textures can be found using **Resource Browser**. When browsing textures you can see small colored box at bottom right. It shows how texture will look at distance (Mip-Maps).

Every layer has 2 textures that can be assigned:

-   Albedo - Color texture.
-   Normal - Texture of the surface bumps, roughness for lighting. It's usually blue or orange and have "normals" in the name.

You can adjust their scale over map using scale sliders under each texture.

### Painting

When you selected one of the layers from 1 to 8, you can paint them into terrain by going to **Paint** tab.

**Paint** by dragging over terrain. To **erase** hold left alt and drag where you want.

Brush settings:

-   **Brush size** - Size of the brush that we want to paint with. You can change it by holding down the **B** key and dragging over ''game view'.
-   **Brush strenght** - Strength with witch brush changes are applied to layer mask. You can change it by holding down the **V** key and dragging over *game view*.
-   **Target value** - Target opacity, that brush will change mask into when painting, values can be from 0 to 1 and are linear
-   **Slope min** - Minimum terrain slope value for painting, allow for excluding flat surfaces from paint
-   **Slope max** - Maximum terrain slope value for painting, allow for excluding cliffs from paint
-   **Scattering** - Randomize brush position. It's great for blending textures and adding noisy details to flat terrain.

**Linear brush** is an improved brush behavior. Supcom terrain shader is not blending layer directly by mask, but it's converting it to be more contrasted. Selecting brush to be linear will compensate for that change, allow painting to be more smooth.

Mask conversion algorithm. You can see that its basically removing values *0 - 0.5* and use only range *0.5 - 1*. That's why on standard brush at beginning nothing happens.

` (mask * 2) - 1`

### Layers tools

\[TODO\]

## Lighting

Lighting can completelychange look of the map, so always remember to spend some time fine tuning lighting.

-   RA - Sun direction, for value 0 is from North, for 90 East, for 180 South and -90 West
-   DA - Sun height over horizon, at value 0 it at horizon, and for 90 is exactly on top. Usually values between 30 to 60 looks good.

### Sun, shadow and ambient

-   **Sun Color** - color at where the sun lights up. Thats the main lighting color. **Sun Multiplier** is how strong sun is, usually values 1.0-1.5 looks good.
-   **Ambient Color** - light color that is aplied everywhere - in lighted areas and in shadowed areas. This is usually light caused by sky, so you can set it to similar color as sky. Usually is blueish-gray color.
-   **Shadow Color** - Color at shadowed areas. It's not really physical correct, but if you feel that shadows are too dark, and you don't want to change sun and ambient colors, you can change shadow color.

### Fog

Fog in Supreme Commander maps is not a big deal. For most maps it is very light and visible only at far distances. **Start** and **End** are distances from camera, where fog begin to blend, and finish blending. End distance should not be too small, to not hide map at strategic zoom. For **Fog Color** the best is color of the atmosphere, horizon color. Something between sky color and land color visible from very far.

### Light Effects

Remember to not set **Bloom** to too big value. Even if you don't have it enabled in game, many users still like to play with it. **Specular** is color and strength of sun reflection from terrain. How specular is applied depend on used stratum textures and if TTerrainXP shader is used or not.

### Procedural skybox

This is new map feature that was added in Forged Alliance expansion. In previous versions of the map files, skybox was just a texture. In v60 scmap file version skybox is defined by few values that are stored in skybox data.

You can just export them from official Forged Alliance maps and import it to your map. Remember, that when saving map as v56, skybox data will be lost. v60 file format works only in Forged Alliance.

Color of the skybox is defined by Horizon color and Zenith color. They create gradient based on height values. Then cloud texture is applied with addional stars/planet/moons billboard textures.

-   **Position** - Updated automaticly by map editor, should be always center of the map.
-   **Horizon** - Height value, where horizon of sky dome will start.
-   **Horizon color** - Color of the horizon
-   **Zenith** - Height value, where will be zenith of sky dome.
-   **Zenith color** - Updated automaticly by map editor, should be always center of the map.

## Armies

Armies can be added, removed or edited by going into the MAP \> ARMIES menu.

For new maps editor create team FFA with all playable armies configured, and 2 extra armies NEUTRAL_CIVILIANS and ARMY_17, that is everything you really need for standard map.

### Multiplayer

Configuration for multiplayer should have 1 team named **FFA**. To add team press +**Team** button

Every playable army should be in this team, and its name should start with *ARMY_* and unique number between 1 and 16. Game support max 16 players. To add army press **+** button under team;

Remember that armies need to be in correct order, first on top of the list need to be always ARMY_1 and next numbers under it. Next army should always be number higher by 1.

For example if you have **ARMY_1** and **ARMY_3**, game will only find 1 army for multiplayer. It need to be **ARMY_1** and then **ARMY_2**.

Remember to rename army in **Extra Armies** if there is any with the name that you want to use for playable army. Older maps usually have **ARMY_9** for civilian defense structures or wreckage, so better is to always rename it to **ARMY_17**.

### Mission army settings

For campaign maps armies have some configuration. Note, that these will not be used in standard game, they are used only in missions.

-   Faction - What faction it is, (0 - UEF, 1 - Aeon, 2 - Cybran, 3 - Seraphim)
-   Color - Color of the army

### Extra armies

Extra armies, are armies, that are not assigned to any team and are not playable. Use these for civilians and for reclaimable wreckage. 

Army with civilians should be always named **NEUTRAL_CIVILIANS**

## Areas

Areas allow to define custom places on the map, that can be later used in custom scripts.

Editor displays them as yellow lines. You can also select area, that editor will render as playable area. By default it use the biggest area. You can also hide it if you need to see whole map.

### Playable area

By default editor creates **AREA_1** and will clip map to that area. That allows to make custom size of the maps. Just create bigger map, and reduce its playable area.

Area used for **Playable Area** is defined in *script.lua* file.

## Markers

Markers are objects, that define points of the map such as spawn point, mass ponts, hydrocarbon, spawn point, AI nodes, and many other custom points used by the game or scripts.

### Spawn points

Spawn point is just a **Blank Marker** that has the same name as the **Army**. When editor find, that name is correct, it change marker graphic to commander icon.

When you created an army in the Armies section of the wiki, notice that it will say, "Army marker not found!". This is intended. You then have to sync the army(ies) with blank markers.

Navigate to the **MARKERS** menu and add a blank marker. Deselect the **Blank Marker** button and click on the marker you just created. Rename it to the corresponding army name, for ex. "ARMY_1".

### Resources

There are 2 types of resource markers: **Mass** and **Hydrocarbon**. They define points, where there will be place for mass extractor and hydrocarbon on the map. Resources can be connected with army by **Adaptive** settings.

### AI

With 17 different types of markers, AI markers give information to AIs for them to function properly during the game.

-   Combat Zone - Points a potential conflict zone between armies. AIs will scout frequently and send units to fight if needed, treating it as low priority waypoint.
-   Defensive Point/Naval Defensive Point - When the zone is secure, AIs will build static defenses there.
-   Protected Experimental - An area where experimentals are being built.
-   Expansion Area - AIs will expand with a low amount of factories with some static defenses when the area is safe.
-   Large Expansion Area - Unlike the normal Expansion Area, Large Expansion Areas will use more factories and defenses as if it was an actual base. The area does still need to be secure.
-   Naval Area - Indicates where to build naval factories. Some defenses will come within the area.
-   Rally Point/Naval Rally Point - Rally Points for units coming from factories. Usually placed near expansion areas and start positions. 
-   Path Nodes - Markers that need to be connected to each others. They work as the path ways for AIs' units.
-   Transport Marker - Used for transports, when no proper node path can be found, to drop units there.
-   Objective - Used by mods to define and highlight positions of strategic interest to the AI, such as in king of the hill, or control point style victory conditions.

Markers Not used by Supreme Commander's standard AI or by Sorian AI:

-   Naval Link - Unknown
-   Island - Historical SupCom references state that the AI will not build expansion bases on an island unless this marker is there.

Tip on making amphibious markers: Note that you can export the land/sea marker position from the editor, open the exported script on notepad and replace all marker type entries to "MarkerType":17 and re-import those markers as amphibious, then you simply need to connect them on water-land areas.

For information on how to make decent markers, please refer to [Thisforumpost](https://forums.faforever.com/viewtopic.php?f=88&t=16606#p166915)

**Auto Path Node** is a marged marker made of Land, Amphibious and Naval path node markers. When editor load map that has more than 2 of them in the same place then they are displayed as AutoPathNode instead of separate nodes. When marker is on land it generate land and amphibious nodes, when on water generates amphibious and naval nodes. Connections between these nodes are preserved. They are exported as standard Land, Amphibious and Naval nodes.

### Chains

\[TODO\]

### Adaptive map

\[TODO\]

### Layers

Layers page allow you to hide or show markers of certain types. This is useful if you have a lot of different markers on the map, and don't want to see them all. This is most often used when creating connections for PathNodes for AI. You can just hide everything other and show marker connections, to see connection between all nodes.

**Spawn Range** are some predefined rings displayed for every spawn point to help you better see distances between resources and other spawn points. Editor display 4 ranges:

-   ACU build range 10 units Orange
-   T1 PD - 25 units Red
-   T2 PD - 50 units Red
-   T3 PD - 70 units Red

## Props

Props are just small objects on the map like trees and rocks, that can usually be reclaimed. They give mass and energy when reclaimed, so plan how you distribute them over your map, because it can change balance.

To create props click on **+** button or *Tools/Resource browser* to open the **Resource Browser**, and make sure that **Category** is changed to **Props**. Then just drag prop to the list on the left. You can put many props on the list, and when painting it will randomly chose one of them. You can also drop prop from browser into map to create it.

When props are selected, you can paint them by just draging mouse over map. You can modify brush size and strength buy UI slider on the left or by holding **B** or **M** keys on the keyboard.

**Left Alt** inverts brush, and allow you to **erase** props from the map. Strength value also works for erasing, so you can chose how fast it removes props.

If you want exact precision (for example for buildings) you can change brush size to 0 and use **Snap to grid**.

Props statistics show how much mass and energy can be reclaimed from all props on the map.

### Prop list values

-   **X button** - Remove prop from the list
-   **Rotation** - allow you to chose range of random rotation of each prop of that type. By default its
-   **Procent** - Chance painting prop. When you have more than one prop on the list, you can chose how often each type spawns when painting.

### Prop Tools

-   **Load brush set** - Import list of the props with their settings.
-   **Save brush set** - Export current prop list.

## Decals

Decals are just small texture decals that can be placed on terrain to give it much more detailed look. There are **Albedo** decals, that gives color, and **Normal** decals, that change surface shape for lighting.

### Decal list

Decal implementation in FAF Map Editor is little different that you can find in other tools. List of the decals is really a "color pallete" of decals, not the decals on the map. At beginning it might feel unintuitive, but it's very useful and speed up whole process. You don't need to find textures from list or find similar decal on the map to duplicate it. There are usually so many decals you can easily get lost in all of them. Instead you just select **Decal Type** from list, like a color from color palete, and just stamp it on the terrain.

### New Decal Type

To create new decal type just click **+** button on the bottom of decal type list. Editor will create and select new decal type. You need now select render type of that decal and assign textures to it.

For **Albedo** decal you need to select color texture.

For **Normal** decal you need to select normal texture (these strange blue or yellow textures).

Decal Types **can't be removed**. They only display last used decals, like last used colors on color palette. You can only remove decal instances from the map.

### Placement Mode

When you select **Decal Type** you want to place on terrain you can click **Place decals** button. Now just by clicking over terrain you place that decal. Remember to select proper symmetry setting before.

While you are in placement mode, you can use keyboard keys to rotate (**E**) and scale (**R**) decal before you place it. Cursor will show you how decal will look on the map.

## Units

To create civilian and wreckage units on your map you need to add them to Extra Armies. Map editor by default create **ARMY_17** and **NEUTRAL_CIVILIAN** armies.

Units and unit groups can be **re-parented** by pressing **P** key. Every selected will be now parented under main selected group (blue on the list).

### Unit groups

Units are stored inside groups. Every group can have other groups under it, so it create trees of groups like folders.

To create new group press **+ Group** button under army or other group.

To select units inside group double click on the group (not on the name). This can also be done with holding Shift or Alt to Add/Remove from existing selection.

To rename it double click on it's name.

**Prefix** is custom naming tag, that is then added to the group name. When you change prefix name, all groups inside that army with same prefix will also change own prefix. Thanks to that is easy to have multiple groups starting with same name, for easier management in the code.

### Wreckage

To create wreckage, create Unit Group named *WRECKAGE* under **ARMY_17** or **NEUTRAL_CIVILIAN**. Editor will automatically render them as wreckage and the game will place them as wreckage. The unit group can be made under any army (player or otherwise) and the game will still place them.

### Civilians

Any army defined under **Extra Armies** will behave as defined by the in game option for Civilians. If the **Civilians** option is set to Enemy they will hate everyone. If set to Neutral they will ignore everyone, but can be captured. This cannot be over-ridden in the editor settings for that army.

The exception to this is the **NEUTRAL_CIVILIAN** army which will ALWAYS be neutral, ignoring all editor and game options to say otherwise.

To create civilians on the map place them under **NEUTRAL_CIVILIAN** or **ARMY_17** in the group **INITIAL**. Civilian units will now spawn when they are enabled in game options.

For example if you want civilians that shoot at players, you must add them under ARMY_17 and have the in game option for **Civilians** set to **Enemy**

## Comand line arguments

**Render Preview Image** - If you want editor to only render preview image of map, then use this command. It allow to generate image with custom width and height. If you want image in png format, then image path need to end with "\*.png". In other cases it will save with JPG compression.

`-renderPreviewImage [Width] [Height] [ScenarioPath] [PngImagePath]`

## Custom resources

Map editor and game allows to have custom textures loaded from map folder. This works only for stratum textures and decals. Props can't be loaded, because game won't load blueprints from maps folder.

Create *env* folder in your map folder, and then inside create needed folders by their type. Note that **ResourceBrowser** will use
**Category** to load from proper folder 

-   layers - Stratum texture
-   props - Props assets. Editor will display and use them, but they will not work in game.
-   decals - Decal textures
-   splats - Splat decal textures

To find your resources in **ResourceBrowser** open select **Map folder** in **Type** dropdown.

## Making custom resources work in FAF

### Initial Map Upload

Editor fix all folder, file names and paths, so it should always work automatically, but you can read these steps if you have any issues with it.

Because the FAF server automatically renames your folder, it can break the paths of custom resources you've set up. To ensure this doesn't happen follow these steps:

-   Make sure the folder of your map has the same name as the .scenario file. For example */maps/New_Shiny_map.v0001/New_Shiny_map.scenario*

The server will rename your map folder into the scenario file name (at least it seems to) so if your scenario name differs from the folder name it will be renamed and broken.

-   Make sure you don't have any spaces in your folder/scenario names

Any spaces in scenario name will be replaced by underscore before being used as a map name so make sure there are none. Or alternatively you can have a map folder name with underscores and scenario file name with spaces but as a general rule it's easier to keep a habit of naming your folder and all the files inside of it exactly the same to minimize any potential issues.

-   Remember when somebody told you that you don't have to add ".v0001" to your map folder name anymore since the server does it automatically? Well forget about that because if you want your map to properly function in the editor and upon uploading to FAF you have to make sure you manually add a version counter corresponding to your current version to the end of your map folder as well as to the scenario file. For example from "*maps/New_Shiny_map/*" to "*maps/New_Shiny_map.v0001/*"

### Uploading a new version

FAF Map Editor have feature to prepare all files of new version for you. It will also update paths of custom assets and every path in scenario.lua. Just open the latest version of your map and click **File/Save as new version**. Files created like that can now be uploaded to Vault.

## New version of the map

If you want to upload new version of the same map, then use **File/Save as new version** in map editor. Editor will create and rename all files for you. When you upload that new version of the map into vault it will hide old versions, and show this one.

FAF vault don't allow to remove broken or old maps. Ask moderators for support on this if you can't upload new, fixed version of these maps.