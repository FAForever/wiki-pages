---
title: Mapping
description: Map creation for Forged Alliance (Forever)
published: true
date: 2024-05-08T23:57:34.208Z
tags: mapping, basic
editor: markdown
dateCreated: 2023-06-30T13:08:23.704Z
---

# Introduction
[![luminarysmaller.png](/images/mapping/gaea/basics/luminarysmaller.png){.align-right}](/en/images/mapping/gaea/basics/luminarybreakdown.jpg)

Welcome to the FAF Mapping Wiki, a comprehensive resource dedicated to equip aspiring map-makers with the essential knowledge and techniques to create new and interesting maps for supreme commander: Forged Alliance Forever.

Custom maps play a vital role in enriching the FAF gaming experience. They provide a steady stream of new content, keeping the gameplay fresh and exciting for long-time players. Additionally, custom maps offer diverse challenges, catering to different playstyles and skill levels, enhancing the game's replayability.

Within these pages, we delve into the intricacies of FAF map-making, from the fundamentals of terrain generation to the strategic placement of key assets. We hope that these tutorials make the map-making process more accessible and provide you with the necessary tools, best practices, and know-how to become a skilled FAF mapper.

We believe the collaborative environment fosters growth, inspires innovation, and drives the continual improvement of map-making within the FAF community. As such, this tutorial draws upon the accumulated expertise of experienced map-makers who have generously shared their wisdom. We endeavor to create an accessible and enjoyable learning experience, suitable for newcomers and seasoned mappers alike. 

If any of these tutorials leave you with questions or remarks, do not hesitate to join us on the FAF forums or on the FAF discord, where we discuss and exchange feedback, tips, and techniques. 

## Terminology
In tutorials and converstations with other mappers we use specific words to refer to specific elements of map making. However, some terms in these contexts may lack precise or consistent definitions, leading to potential misunderstandings and ambiguity. For others, the meaning may be unclear at first glance, making it difficult for beginning mappers to understand what is meant. In order to provide a clear and concise reference for essential concepts in FAF mapping, the [Terminology](/en/Development/Mapping/Terms) page present a list of key terms and their definitions.

- [Terminology *Commonly used terms and their definitions*](/en/Development/Mapping/Terms)
{.links-list}

## The basics of mapping
At the most basic level, maps consist of the following elements:
|-|-|
|Terrain|The geometry of your map. Consisting of a greyscale image, either created inside the editor or imported from an external source|
|Textures|The tiled colour images that turn your blank terrain into sandy beaches, grassy fields, and stone cliffs|
|Texture Masks|The greyscale images that dictate where which texture is made visible. Created in the editor or imported from an external source.|
|Spawn and resource markers|Markers that dictate where players spawn, and how mexes and hydros are placed|  
|Props|The 3D models that populate your map, such as reclaimable rocks and trees| 

On top of that, more detail and character can be introduced by adding decals—smaller images that may be freely positioned, scaled, and rotated on the map—civilian AI units, and wrecks. 

The exact use of all these elements gives you a lot of room for creativity, although the large amount of freedom might at first feel somewhat overwhelming. However, do try not to be put off by this: the whole process of creating maps looks at first to be more difficult that it really is. Nonetheless, it is adviced that for your first map, you limit yourself to a 5KM map, as the amount of time required to complete a map increases significantly as the size increases.

A comprehensive tutorial series on the basics of map making is available on youtube, and is highly recommended material for any mapper. 

- [FAF Map Development*Official video tutorial series*](https://www.youtube.com/playlist?list=PL0nxuIUIjpFvM-lU3h6ROtWsoC_ikkaAs)
{.links-list}

# Tools and software
Aside from the editor, you may want to use several other external tools, such as image editing software and terrain generation tools. Below follows short descriptions and links to tutorials for the most commonly used tools. 
## Editors
### Ozonex Editor
The [FA-Forever-Map-Editor](/en/Development/Mapping/FA-Forever-Map-Editor) is a new map editor developed for FAF by ozonex. Although perpetually stuck in an unfinished alpha stage, which means the editor is in its testing phase and lacks some of the features of the GPG editor, it is considered in many ways a significant improvement over the GPG editor. Generally, this editor is the recommended editor to use.

It is a powerful tool for creating custom maps in Supreme Commander: Forged Alliance, but like with any software, you might encounter various technical issues that can prevent you from creating maps that meet your vision. These issues can range from minor annoyances to serious problems that make it impossible to complete your map. [In the troubleshooting page](/en/Development/Mapping/faf-map-editor-troubleshooting), we'll cover some common technical issues you might encounter while working with the map editor and related files.

- [FA-Forever-Map-Editor *The modern editor provided by Ozonex et al.*](/en/Development/Mapping/FA-Forever-Map-Editor)
{.links-list}

### GPG editor
The [GPG-Map-Editor](/en/Development/Mapping/GPG-Map-Editor) is the editor released by GPG studios and was their internal tool for map development. Note that you require a copy of Supreme Commander (which is *not* Supreme Commander *forged alliance*) to run this editor, as it is dependent on some of the core game files.
- [GPG-Map-Editor *The legacy editor provided by GPG studios*](/en/Development/Mapping/GPG-Map-Editor)
{.links-list}

## Terrain generation tools
In map-making, terrain heightmaps are typically crafted using manual brush tools (provided by the editor) to sculpt terrain features by hand, offering map-makers precise control over the landscape. However, for those seeking alternative approaches or aiming for more expansive and intricate terrains, specialized terrain generation tools present valuable options to streamline and enhance this process beyond the limitations of traditional hand-sculpting methods.. 

Two prominent tools in this domain are WorldMachine and Gaea. Both WorldMachine and Gaea are specialized software that empowers map-makers to generate realistic and detailed terrains procedurally, employing algorithms to simulate natural geological processes like erosion, weathering, and tectonic movements. These tools allow you to quickly generate and manipulate vast landscapes with a wide range of features like mountains, valleys, and rivers.

### WorldMachine
- [Using Worldmachine and the GPG editor to make a map*A video tutorial series by Lionhardt*](https://www.youtube.com/playlist?list=PLLKHtCMTwATBTx6vrN1ty6xFAByQgh5B-)
- [World machine tutorial: Basic shapes*A video tutorial on the basics of WorldMachine*](https://www.youtube.com/watch?v=nlWssphJMkY)
{.links-list}

### Gaea {#Gaea}
[<img align="right" src="/images/mapping/gaea/gaea_general.png" width="20%">](/en/Development/Mapping/Gaea)

Gaea is a terrain generation tool not unlike WorldMachine, though significantly more modern. The free version of Gaea allows you to create heightmaps up to a 1K resolution, which corresponds to a maximum map size of 20x20KM. 

A tutorial series on using Gaea for FAF mapping was written by IndexLibrorum (AKA Prohibitorum) and introduces the basics of Gaea, how to create terrain, how to create stratum masks, how to texture with Gaea, and how to create map-wide assets.
- [A tutorial series on using Gaea for FAF mapping*An extensive tutorial series on Gaea by IndexLibrorum*](/en/Development/Mapping/Gaea)
{.links-list}

## Other tools
### Image-editing tools
To create custom assets or customize existing ones, you will require some kind of image-editing tool. Photoshop will be able to do nearly anything you need, and comes highly recommended. If you do not have access to photoshop you may take a look at free alternatives, such as GIMP (a Linux based image manipulation program) or Photopea (an online photoshop-clone).

- [GIMP *Free-to-use image editor software*](https://www.gimp.org/)
- [Photopea *Free-to-use Online photoshop clone*](/en/https://www.photopea.com/)
{.links-list}

### Encoding tools
Assets like custom textures and decals need to be exported or encoded as a particular type of .DDS file. Plugins exist to allow photoshop and GIMP to open and export .DSS, but it is recommended to use the ImageMagick converter tool as this tool has proven to be more effective at compressing files when encoding as .DDS.

- [ImageMagick *Recommended tool to encode images to DDS*](https://imagemagick.org/index.php)
{.links-list}

# The map creation process
## Terrain
<img align="right" src="/images/mapping/heightmaskdemo.png" width="35%">
The most important element of a map is the heightmap, which defines the elevation and topographical features, determining the shape and contours of the landscape. Once the heightmap is ready, it forms the foundation upon which other map elements are integrated.

In essence, a heightmap is a grayscale image where different shades of gray represent varying elevations. Darker areas correspond to lower points, such as valleys and depressions, while lighter areas represent higher elevations, such as hills and mountains. 

To create a heightmap, various methods can be used. The most basic approach involves using the [brushes provided by either of the two editors](https://wiki.faforever.com/en/Development/Mapping/FA-Forever-Map-Editor#heightmap-brush), which allow you to manually sculpt the terrain. Alternatively, map-makers can craft heightmaps manually using graphic editing software like Adobe Photoshop or GIMP. An advanced approach involves  specialized terrain generation software like WorldMachine or [Gaea](#Gaea), which use algorithms to simulate natural geological processes, generating realistic and organic terrains. 

You can import heightmaps that you made using external programs into the editor, as long as you provide the editor with an image of the right filetype and size. Heightmaps must be encoded as a .raw file and with a resolution—the size of the image in pixels—that corresponds to the size of your map. It's important to remember that while assets such as masks, textures, and decals are usually provided to the editor in resolutions of powers of 2 (256, 512, 1024, 2048, etc.) heightmaps require you to take the size of your map in pixels, plus one. This means that a 5KM map, which is 256 by 256 pixels, requires a heightmap of 257 by 257 pixels. Similarly, a 10KM map is 512 pixels, but requires a heightmap of 513 by 513 pixels. 


- [Creating a map: Heightmaps*Part of the official video tutorial series on mapmaking*](https://www.youtube.com/watch?v=UNajB0EOKnM&list=PL0nxuIUIjpFvM-lU3h6ROtWsoC_ikkaAs)
- [Ozonex editor heightmap tools *Detailed explanation of the tools available in the editor, including water and terrain-type settings*](/en/Development/Mapping/FA-Forever-Map-Editor)
- [ Mountains | GPG editor*A video tutorial on making mountains in the GPG editor*](https://www.youtube.com/watch?v=nm5NVD17kvw)
- [Mountains | Ozonex editor*A video tutorial on making mountains in the Ozonex editor*](https://www.youtube.com/watch?v=h26369gnTEo)
{.links-list}

## Water
The placement of water in a map is directly influenced by the terrain's elevation. Water is set as a flat plane at a specific height, and any part of the terrain with an elevation below that set height will be submerged by the water. As you sculpt the terrain, the varying elevations defined directly impact where the water will be placed. When the terrain's elevation is lower than the set water height, that portion of the map will become submerged, creating lakes, rivers, or other bodies of water. 

[Water settings](/en/Development/Mapping/FA-Forever-Map-Editor#water) can be adjusted to enhance the visual representation of water, such as its transparency, color, or reflections. These settings, in conjunction with the terrain, contribute to the overall aesthetics of the water within the map.

To get the most out of the water settings, do the following:
Firstly, use the same min and max for the water lerp, otherwise there will be weird effects close to the shore, because that setting actually paints the surface of the water. Instead, the water ramps should be used to color the ground of the terrain to your liking. This also ensures that units underwater will get shaded as expected.
A small but >0 value for the water lerp in combination with a dark gray surface color is recommended to simulate the light that gets lost when it gets reflected on the surface, i.e. units and terrain under the water line should immediately look a tad darker.
You should mainly control the look of the water by adjusting the water ramp. Unfortunately these settings are only available in the gpg editor. There you can select one of the water ramp textures that the game provides.
If you don't like the presets, you can also edit the water ramp manually in an image editor. The alpha value of the water ramp texture represents the depth. The color is the color of the water at that depth. For safest results the color should be the same everywhere and the alpha value should linearly increase from 0 to 1. The first pixel has to have an alpha value of 0 or your whole map will be tinted. For more artistic freedom you can play around with a color gradient. When you start the game with diskwatch enabled, you can edit your water ramp and whenever you save it, the game will immediately load it. Use the gradient tool in e.g. GIMP together with this trick to work with super fast iterations when experimenting with the water.
If you made a water ramp that works well, please share it in a game dev channel on discord, so we can integrate it in the repository. This way we will over time have a bigger and better collection of water ramps that mappers can choose from and be done with it without manual edits.

You can use higher quality wave textures by using the ones provided by FAF in the textures/engine directory. Either unpack the textures.nx2 archive or get them from [here](https://github.com/FAForever/fa/tree/deploy/fafdevelop/textures/engine)

If you want the sun to be properly reflected in the water you need to set the sun direction for the water to the sun direction the rest of the map uses. Set the sun color to Pi (3.14...) times the sun color you defined for the terrain. (For point lights the light intensity has to be multiplied with Pi to get correct reflection results in our shading model. Without going into details, there is a mathematical reason for this. In the terrain shader we can do it in the shader code, but because the water shader is the same for all maps, you have to do it manually here.)
Lastly, you should adjust the SunShininess to a greater value to make the reflection sharper.
As the map editor doesn't allow you to edit these values, you have to export the water settings, change the appropriate values and import the file again.

- [About water: Introduction*Pt.1 of the forum post series on water by Jip*](https://forum.faforever.com/topic/59/about-water-introduction)
- [About water: Water settings*Pt.2 of the forum post series on water by Jip*](https://forum.faforever.com/topic/64/about-water-settings)
- [About water: Wave generation*Pt.3 of the forum post series on water by Jip*](https://forum.faforever.com/topic/71/about-water-wave-generation)
- [About water: Brushes*Pt.4 of the forum post series on water by Jip*](https://forum.faforever.com/topic/73/about-water-brushes)
- [About water: Ramps*Pt.5 of the forum post series on water by Jip*](https://forum.faforever.com/topic/65/about-water-water-ramps)
- [About water: Environment maps*Pt.6 of the forum post series on water by Jip*](https://forum.faforever.com/topic/72/about-water-environment-maps)
- [About water: Waves and normal maps*Pt.7 of the forum post series on water by Jip*](https://forum.faforever.com/topic/74/about-water-waves-and-normal-maps)
- [About water: Pixelated water*Pt.8 of the forum post series on water by Jip*](https://forum.faforever.com/topic/48/about-water-pixelated-water)
{.links-list}
 
## Texture stratums
Textures play a pivotal role in transforming the terrain into distinct types, such as deserts, grass fields, and rocky cliffs. Achieving this effect involves the carefull application of textures to specific areas of the terrain using masks. Masks are greyscale images wherein varying shades of gray denote different levels of texture opacity. Darker regions reveal less of the texture, while lighter regions expose more of it. Similar to heightmaps, masks may be either created by hand using the [brush tools](en/Development/Mapping/FA-Forever-Map-Editor#painting) in the editor, or may be generated by external software such as WorldMachine or [Gaea](#Gaea).

These textures, together with their corresponding masks, are organized as layers, known as [stratums](/en/Development/Mapping/FA-Forever-Map-Editor#texture-layers). A stratum encompasses essential settings, including the selected texture, its accompanying normal map, zoom levels for both the texture and its normal map, and the associated mask. Up to nine stratums can be used, with one designated as the 'base' stratum. This base stratum does not accept a mask and acts as the foundation on which subsequent stratums are layered.

When creating a map, choosing the right textures and placing them carefully is very important. Textures not only determine how your map looks, but also help players understand the terrain. It's crucial that rough, uneven, or areas that units cannot cross are easily recognizable. To achieve this, it's a good idea to use a specific texture for cliffs, which are steep areas units cannot cross, and another texture for slopes, which are inclined areas that units might have trouble crossing or where buildings cannot be constructed. By using different textures for these terrain features, players can quickly understand which areas are passable and which are not.

Lastly, you are able to define specify the [terrain type](/en/Development/Mapping/FA-Forever-Map-Editor#terrain-type) of specific areas of your terrain. Terrain type primarily affects the interaction between units and the terrain visually, generating specific dust patterns when units move over the terrain. However, there are some *blocking-type* terrain types available that will prohibit units from moving over areas marked as such.

- [Creating a map: Stratum layers pt. 1*Part of the official video tutorial series on mapmaking*](https://www.youtube.com/watch?v=cVb_w0-REZc&list=PL0nxuIUIjpFvM-lU3h6ROtWsoC_ikkaAs&index=4)
- [Creating a map: Stratum layers pt. 2*Part of the official video tutorial series on mapmaking*](https://www.youtube.com/watch?v=lWWdLS2a5VU&list=PL0nxuIUIjpFvM-lU3h6ROtWsoC_ikkaAs&index=5)
- [Texture painting*Video tutorial on how to blend textures in the Ozonex editor*](https://www.youtube.com/watch?v=nzTnDc2vKU4)
{.links-list}

## Lighting
In the lighting tab of the FAF editor, you can adjust various lighting and atmospheric settings. These settings affect the strength of the sun and its placement in the sky: both its height and its direction can be changed. Other settings can be changed to adjust the colour of the sunlight, the colour of the shadows, and the colour of the ambient light. These settings can have a significant effect on the aesthetics of your map.

The light settings are a bit confusing because the shadow color exists and because the code for factoring in the shadow color in the game is a bit convoluted it actually affects not only the shadows, but the entire map. So the recommended workflow is to just set the shadow color to 0.
Use the ambient color to adjust the look of the shadows and then tune the sun color after that. If you later want to make the whole map brighter or darker you can use the light multiplier. This makes it easier to reason about your lighing settings and which value you should tune to reach a certain effect.

Part of the lighting settings are environment maps. They determine the reflection on shiny parts of the units. Only the gpg editor exposes these settings. The environment map should be chosen by selecting a texture that is close to the colors that your map uses to create the illusion that the units actually reflect the ground and the sky.
For optimal results you need to provide two environment maps. One for the land units and one for the navy units. The one for navy units needs to be specified as `<water>`. Ideally the default one is non-mirrored i.e. it has a sky and land and the water one is mirrored, to simulate the sky reflection on the water surface.

Aside from light settings, other settings include those for Fog and the skybox, allowing you to further adjust the environment of your map.

- [Creating a map: Lighting*Part of the official video tutorial series on mapmaking*](https://www.youtube.com/watch?v=7TXHY1_smwU&list=PL0nxuIUIjpFvM-lU3h6ROtWsoC_ikkaAs&index=11)
{.links-list}

## Clouds
- [About weather: Generating clouds*A forum tutorial on cloud generation by Jip*](https://forum.faforever.com/topic/277/about-weather-generating-clouds)
{.links-list}

## Skyboxes

Todo

## Markers
Every map contains places for players to spawn, spots where mass extractors can be built, and often spots for hydro generators as well. To place these on your map, the editor uses markers. There are specific markers for spawn locations and resources, and more advanced markers that help  AI opponents understand how your map should be played.

### Spawns and resources
Placing your spawns, mexes, and hydros should be done with carefull consideration, as aside from the the terrain, this layout is the most critical to how your map will be played. A common mistake for beginner mappers is to provide either too many or too few mexes. Generally maps can be organized in three zones, and mexes should be placed accordingly. The figure below shows these zones marked on the map *Project Dust*.

* [<img align="right" src="/images/mapping/projectdustmexzones.png" width="25%">](/images/mapping/projectdustmexzones.png)The first zone (green) consists of *core* or *safe* mexes. These include the mexes directly in range of the player upon spawning, and those slightly further removed. These mexes may be expected to remain safe throughout the game, and losing these usually signifies that player has lost control of their portion of the map.
* The second zone (yellow) consist of *expansion* mexes, and are those mexes that players expand towards after establishing their first factories. These mexes are similarly under the control of their respective player for most of the game, and are often used to establish frontline factories or firebases around.
* The third zone (red) consists of *contestable* mexes, and include both the mexes in the middle of the map, often where players meet and most battles are fought, as well as the mexes scattered along the edges of the map, if present. Ownership of these mexes changes often, as these mexes are harder to defend and highly raidable. 

Although certainly affected by personal preference, it is considered good map design to carefully balance the number of contestable mexes. On the one hand, too few contestable mexes leads to stale gameplay, favouring the defence of expansion mexes and disfavouring active raiding. On the other hand, too many contestable mexes may lead to a situation where one team achieves control of slightly more than half of the map, but a significant larger amount of mexes. 

The layout of these zones highly depends on the terrain of your map, and must be reconsidered with each map. By changing the location of the expansion mexes and contestable mexes, you influence in what direction players develop. Commanders commonly move towards expansion mexes first, and may then fight over contestable mexes. Playtesting is highly recommended to evaluate if your mex placements are functional, and it is not uncommon to go through several revisions based on playtesting and player feedback.

- [Creating a map: Resources*Part of the official video tutorial series on mapmaking*](https://www.youtube.com/watch?v=s4-DGucm9eQ&list=PL0nxuIUIjpFvM-lU3h6ROtWsoC_ikkaAs&index=2)
{.links-list}

### AI markers
Artificial Intelligence (AI) provide players with computer-controlled opponents of different skill levels. This feature has garnered significant popularity within the FAF community, with over half of the player base actively participating in AI games. By providing players with the opportunity to challenge intelligent computer opponents, AI enhances the richness and diversity of gameplay options, catering to a wide range of preferences and skill levels. Consequently, maps should aim to be AI compatible, and be designed with AI in mind.

For a comprehensive understanding of how AI functions in FAF, you may refer to the main page on AI. Relevant information in the context of mapping is provided by this tutorial on [best practises to create AI friendly maps](/en/Development/Mapping/ai-friendly-maps). It is recommended to follow these guidelines to ensure your maps are compatible with for AI.

- [About markers: AI markers*Pt.1 of the forum post series on AI markers by Jip*](https://forum.faforever.com/topic/145/about-markers-ai-markers)
- [About markers: Movement and pathing markers*Pt.2 of the forum post series on AI markers by Jip*](https://forum.faforever.com/topic/343/about-markers-movement-pathing-markers)
- [Adding AI markers using the GPG editor*A video tutorial by Plasia*](https://www.youtube.com/watch?v=KDO8zf2afhc)
{.links-list}

## Props
While a map becomes technically playable once the terrain and resources are set, it is not truly complete until it is populated with props. Props, such as trees and rocks, play a crucial role in both enhancing the map's aesthetics and influencing the players' strategies. Most props are reclaimable, meaning they can be gathered for resources, though some exceptions exist.

Strategic placement of props can guide players' development and decision-making. Rocks with high reclaim value become valuable targets for expanding engineers, and their positioning can influence the routes taken by engineers and early raiding units. Trees, on the other hand, offer a welcomed source of energy, helping players avoid energy shortages if they haven't built enough power generators.

Props come in various styles and themes, and it's important to choose ones that match the terrain's overall design. For instance, if the map depicts a desert landscape, opting for sandy-colored rocks and cactus plants would be a fitting choice. Thoughtfully incorporating props that harmonize with the map's theme will greatly improve the quality of your map. The page on the FAF editor explains [how props can be added to the map](https://wiki.faforever.com/en/Development/Mapping/FA-Forever-Map-Editor#props).

- [Creating a map: Trees and rocks*Part of the official video tutorial series on mapmaking*](https://www.youtube.com/watch?v=6oDs1brYB_0&list=PL0nxuIUIjpFvM-lU3h6ROtWsoC_ikkaAs&index=3)
{.links-list}

## Decals
Similar to props, [<img align="right" src="/images/mapping/luminarynodecals.png" width="20%">](/images/mapping/luminarynodecals.png)decals play a significant role in enhancing the aesthetics of your map, although they are technically optional. Decals are images that can be freely positioned, scaled, and rotated on the map, contributing to its visual appeal. There are two common types of decals: Albedo decals and Normal decals.

Albedo decals are full-color images and include images of sandy and rocky patches, moss, and sooty explosions. They serve various purposes, such as enhancing textures, creating visual contrast in specific areas, and supporting other map elements. By strategically placing Albedo decals, map-makers can draw attention to certain features and add intricate details to the terrain.

On the other hand, Normal decals appear as orange patterning on a green background and utilize a technique called bump mapping. [<img align="right" src="/images/mapping/luminarywithdecals.png" width="20%">](/images/mapping/luminarywithdecals.png)This technique allows them to influence how light interacts with the terrain. They create the illusion of terrain deformations, even in areas where there are no actual changes in height. This is particularly useful for adding intricate details to areas with limited resolution on the heightmap, making terrain more visually appealing without affecting unit pathing. Normal decals are especially beneficial for highlighting ramps and uneven terrain, aiding players in identifying critical landscape features during gameplay.

More advanced techniques use [custom decals](#CA), some of which include decals that are made to match the exact terrain of the map. Such map-wide decals can be used to add shadows, weathering, and colour correction. The images on the right show the effect decals can achieve, with the first image showing the map without any decals, and the second image showing the map with all the decals, including a map-wide shadow decal, map-wide normal decal, and map-wide albedo decal.

- [Creating a map: Decals pt.1*Part of the official video tutorial series on mapmaking*](https://www.youtube.com/watch?v=YhDyCTf8cyI&list=PL0nxuIUIjpFvM-lU3h6ROtWsoC_ikkaAs&index=6)
- [Creating a map: Decals pt.2*Part of the official video tutorial series on mapmaking*](https://www.youtube.com/watch?v=vRAvQIP3NoI&list=PL0nxuIUIjpFvM-lU3h6ROtWsoC_ikkaAs&index=7)
{.links-list}



## Units and wrecks
Similar to props, you can bring extra detail and reclaim to your map by including units and wrecks. Units placed on the map are generally placed as either neutral or hostile civilians. Neutral civilian buildings can be captured or reclaimed by players with little effort. In contrast, any offensive unit or building, such as tanks or point deffence, belonging to hostile civilians will shoot all players that enter their range. By default, none of the civilian units will move, although this behaviour can be modified by scripts.

Unit wrecks, unlike civilian units and buildings, will not spawn as an intact unit but as its reclaimable wreck. These can be placed on maps to imply earlier battles fought or to simulate a crashed transport, for example. 

Just as with props, it is important to place units and wrecks with care. The reclaim provided by these units change how players approach the map, and it is generally discouraged to place large patches of reclaim in the middle of the map, as this often leads to extremely volatile gameplay. As a consequence, units and wrecks should be placed in moderation and with careful consideration.

- [Creating a map: (Wrecked) Civilians*Part of the official video tutorial series on mapmaking*](https://www.youtube.com/watch?v=16zuZ60XHbk&list=PL0nxuIUIjpFvM-lU3h6ROtWsoC_ikkaAs&index=12)
{.links-list}

## The map vault
The FAF map vault is the official database containing the community-created maps, making it easy for any player to find and download new maps. Once (the first version of) your new map is ready for playing, you should submit your map to the vault so that you can host a lobby with your map. While you could host a private lobby for yourself if you do not share the map to the vault, for other players to download your map and join your lobby, the map must be uploaded to the vault. 

As you work on your map, you will likely need to test half-finished versions of your map before you feel comfortable uploading the finished product to the vault. For such tests, it is recommended that for such tests you do not upload your map to the vault, but rather [test the map without uploading](https://www.youtube.com/watch?v=EQbP_mXER7M).

By uploading to the vault, you agree to [the vault guidelines](/en/Development/Vault/Guidelines) and [vault rules](/en/Development/Vault/Rules). Upon uploading, you are asked whether you wish to mark your map as a ranked map. Ranked maps impact players' global ratings upon playing matches—winning teams see rating increases, while losing teams experience decreases. If you wish your map to be marked as ranked, it is critical that the map is symmetrical, so as not to give any one team an unfair advantage.

Nonadherence to the vault rules is a bannable offence, and although the rules are fairly self-explanatory, it is recommended that you read the rules carefully.

If you wish to make changes to your map once it has been uploaded to the vault, it is necessary that you create [a new version](https://forum.faforever.com/topic/459/about-the-versioning-system) of your map. The old version of your map should remain on the vault, as this is required to watch replays, but may be hidden.

- [Maptesting without uploading*A tutorial video on how to test a map without having to upload it to the vault*](https://www.youtube.com/watch?v=EQbP_mXER7M)
- [About the versioning system *A forum post by Jip on how to make a new version of your map*](https://forum.faforever.com/topic/459/about-the-versioning-system)
{.links-list}

# Further Information
## Increasing the quality of your map
While the definition of a good map can vary based on individual taste and playstyle, there exists a consensus on certain aspects that distinguish great maps from the merely good ones. Throughout this guide, we have already touched upon some of these standards while discussing various map elements. However, additional tutorials are presented here to offer further insights and knowledge.

Should you find yourself seeking clarification or are looking to discuss different mapping aspects, we encourage you to join the official FAF discord community. There, you can interact with other passionate map-makers and enthusiasts, sharing your thoughts, ideas, and questions in the Mapping-general channel. This collaborative space serves as an invaluable resource, providing opportunities to learn from experienced map-makers, exchange ideas, and refine your mapping skills.

Remember that map-making is a dynamic and creative process, and continuous learning and improvement are integral to crafting exceptional maps. Embrace the community's collective knowledge, explore new techniques, and experiment with innovative ideas. By actively participating in the FAF mapping community, you are helping to keep this old game stay active and interesting for thousands of players worldwide.

- [What makes a bad map?*Video tutorial explaining guidelines for map design by TheDuelist*](https://www.youtube.com/watch?v=PqHBJkqqf38)
- [Forum post | Making bad maps better*A lengthy forumpost with images by Biass*](https://forums.faforever.com/viewtopic.php?f=53&t=18647)
{.links-list}

### Tips
- Searching for concept art and reference images could help with getting inspiration for new maps. You can find a selection of images [here](https://forum.faforever.com/topic/6304/reference-and-inspiration-thread)
- Color theory should be applied to make maps visually appealing.
- Color grading of textures (i.e. editing their hue in an image editor) should be used to create a coherent look of the map and to make textures visally fit into your map that you otherwise couldn't use.
- The color ramp for water can be edited in an image editor as well.

### Checklist of often overlooked settings
- Did you adjust the fog settings?
- Did you use terrain types?
- Did you play around with water ramps?
- Did you adjust the skybox?
- Did you set fitting environment maps?
- For the water as well?
- Did you try out different wave textures?
- Did you align the sun direction in the water settings to create a proper sun reflection?
- Did you put a sun decal or other decals in your skybox?

## Using a different terrain shader
FAF provides additional terrain shaders. These alter how the game renders the map and provide opportunity to improve the visual fidelity of the map. As this is pretty new, the tools for dealing with them are not really there yet, so the process is not as streamlined as the rest of mapmaking.

To change the shader of the map you have to use a software to edit binary files like Hex-Editor MX. With this you open the scmap file in your map folder. Then you search for the string TTerrainXP. This is the name of the standard shader that the map uses. You can change this to make the map use one of the shaders that are explained below. Save the file afterwards.
You may have to set up your map settings differently depending on what the shader expects as inputs. This is explained in detail in the following sections.
  
  
### Utility texture
All the new shaders use a new utility texture to provide custom normals and terrain shadows. Previously this could be faked with decals, but the decals could sometimes flicker and it would lead to double shadows when units are standing in the terrain shadow. The new shaders resolve these problems by properly incorporating the texture into the rendering pipeline. This eliminates flickering and units standing in the shadow will not cast an additional shadow.
The normal channels can be used to add additional details or to just correct the calculations that the game does. The calculations of the normal vector for the terrain by the game are a bit off, so it makes sense to provide your own.
Providing the water depth with a texture is necessary because of technical limitations with the shader code of the game, but it also allows us to provide a higher resolution of the water depth texture than the game would generate internally.
Shadow and normal maps can be produced with the help of world machine or gaea. The map generator will soon be able to generate the utility texture in one go.

The texture channels are read like this:
red: normals x
green: normals z
blue: water depth
alpha: shadow

The normals in x direction should look like a light is shining on the map from the right hand side.
The normals in z direction should look like a light is shining on the map from the bottom.
If these directions are not correct, then the normal calculations in the game will be incorrect and you will get unexpected lighting results.
The water depth is a normalized depth, this means it needs to be 0 at and above the water surface and 1 at the abyss depth and below, with a linear interpolation for terrain heights between these two heights.
The shadow texture needs to be 1 where the sun reaches and 0 where shadow is. The resolution of the texture needs to be a power of two and should sensibly be at least the ogrid resolution of the map, but it can be higher. Just keep in mind that an extremely big texture also consumes a lot of memory.
The texture needs to be loaded in the upper albedo texture slot. The editor will show the texture like any other texture because the editor doesn't yet feature support for this. You can just hide the texture layer if you find it distracting.

To enable proper usage of this texture you need to set the scale of the upper albedo texture to a value bigger than the size of the map in ogrids (e.g. >513 for a 10x10 map). A value of 10000 will work for any map size.

### Exponential water absorption
The new terrain shaders can simulate exponential absorption of light as it travels through the water. Originally the game uses linear absorption which works somewhat but is not great because exponential falloff is the physically correct one.
The game calculates the absorption on units in a different file, so we have to give it a hint to trigger exponential water absorption on the units as well. To do this, set the lighting multiplier to 2.2 or greater. You can tune down the sun and ambient color accordingly to not mess up your lighting. If you skip setting the light multiplier, the color of the sea floor and submerged units will not match, breaking the illusion.
After this change you might want to edit the water ramp you are using, because the appearance of the water will change.

### Mapwide albedo texture
Some of the new shaders use the stratum 7 albedo slot (layer 8 in ozonex editor) as a mapwide albedo texture. It works similar to the macrotexture as in the alpha channel controls the transparency directly. It doesn't react to the scale anymore and always perfectly covers the whole map.

### Roughness maps
Some shaders feature improved sun reflection that can be controlled with roughness maps. This is achieved by implementing physically based rendering. This means you can use the roughness maps that you can find when you search online for PBR materials. The terrain will now react to light in a physically plausible way, in contrast to the rudimentary specular reflections that the game originally features.
To use this, you need to provide a texture atlas with the roughness maps in the normal texture slot of layer 8. This texture atlas can be automatically generated with a mapgen tool.

### Advanced splatting
TODO

### Biplanar mapping
TODO

### Rotated sampling
This is for breaking up the texture repetition.
TODO

### Naming scheme
The new shaders are organized by a naming scheme to make it easier to select the one you want and to add even more shaders in the future. All shaders are named 'Terrain' followed by a three-digit number. The numbers are used as follows

The first digit shows the main category
- Terrain0XX for shaders that don't use roughness maps or advanced splatting
- Terrain1XX for shaders using roughness maps
- Terrain2XX for shaders using advanced splatting
- Terrain3XX for shaders using roughness maps and advanced splatting

The second digit gives info about some technical properties of the shader with the range being divided into two halfes:
- TerrainX0X to TerrainX4X for shaders with half mask range
- TerrainX5X to TerrainX9X for shaders using the full mask range

Due to an oversight by the original developers, the stratum masks in the standard shaders only work in the 128 to 255 value range and have no effect in the lower half. Annoyingly this only affects the albedo textures, the according normal textures interpret the masks in the full 0 to 255 range.
This shader fixes this inconsistency by making both interpret the 128 to 255 value range (half range) or the 0 to 255 value range (full range) as 0 to 100%.
We provide both options because this bug has been around for so long that many tools and mapmakers assume half range to be used, so this makes upgrading to a different shader easier.

We can then use individual digits for different properties:
- TerrainX0X and TerrainX5X for shaders without any additional properties
- TerrainX1X and TerrainX6X for shaders using biplanar mapping
- TerrainX2X and TerrainX7X for shaders using additional rotated sampling
- TerrainX3X and TerrainX8X for shaders using biplanar mapping and additional rotated sampling

This leaves us with the third digit to have enough room to create multiple shader variations of the same category.

### Available shaders

#### Terrain001
Terrain001 is designed as a drop-in replacement for TTerrainXP that solely introduces the exponential water absorption and map-wide normals and shadows. That's why it also keeps the half mask range for albedo layers and full mask range for normal layers.

#### Terrain002 and Terrain052
These are very similar to Terrain001. The only difference is that they change how the texture masks get read for the stratum normals.

#### Terrain003 and Terrain053
These additionally use the mapwide albedo texture and the red channel of the normal slot of layer 8 controls the amount of specular reflection. The other channels of the normal slot are unused.

#### Terrain101 and Terrain151
The normal map scales are controlled by the albedo scales to ensure that they use the same values.
The layer mask of layer 8 acts as a roughness multiplier with 0.5 as the neutral value.
They also use the mapwide albedo texture.

#### Terrain301 and Terrain351
The normal map scales are controlled by the albedo scales to ensure that they use the same values.
The layer mask of layer 8 acts as a roughness multiplier with 0.5 as the neutral value.
Height processing happens at two scales, the albedo scales control the near scale and the normal scales control the far scale.
They also use the mapwide albedo texture.


## Custom assets {#CA}
The game provides you with a decently large selection of textures to use in your maps. However, if you want to give your map an unique look, or if you just cannot find a texture that works well for your map, you may choose to use custom textures. There are many beautiful custom textures available for download online, and they are often available in higher resolution than the stock textures.

Custom textures, and decals, need to be encoded to a .DDS file format, specifically the (DXT3) BCT2 compression format. Several tutorials on the topic are available.

- [Custom textures*Video tutorial on how to add custom textures by Morax*](https://www.youtube.com/watch?v=_wXK0aYnz70)
- [About decals: Introduction*Pt. 1 of the forum post series on decals by Jip*](https://forum.faforever.com/topic/24/about-decals-introduction-part-1)
- [About decals: Converting normal maps*Pt. 2 of the forum post series on decals by Jip*](https://forum.faforever.com/topic/245/about-decals-converting-normal-maps)
- [About decals: WorldMachine templates*Pt. 3 of the forum post series on decals by Jip*](https://forum.faforever.com/topic/1090/about-decals-world-machine-templates)
- [About decals: Generating map-wide normal texture*Pt. 4 of the forum post series on decals by Jip*](https://forum.faforever.com/topic/785/about-decals-generating-a-map-wide-normal-texture)
- [About decals: Generating a map-wide lighting texture*Pt. 5 of the forum post series on decals by Jip*](https://forum.faforever.com/topic/786/about-decals-generating-a-map-wide-lighting-texture)
{.links-list}
- [About custom decals and stratums*A forum post by Jip*](https://forum.faforever.com/topic/19/about-custom-decals-and-stratums)

## Adaptive mapping
Prior to the introduction of adaptive maps, it was a common practice to upload multiple versions of the same map, each modified with slight resource variations (e.g., Canis 4v4, Canis 5v5). However, with the advent of the adaptive map script developed by CookieNoob and KeyBlue (with further modifications by svenni_badbwoi), this is no longer required. Adaptive maps enable the consolidation of several similar map versions into a single map, offering advanced map settings directly accessible from the game lobby. Such settings may allow players to adjust map resources dynamically based on the number of players, as well as add or remove resources, units, and wrecks. Two tutorials, [one legacy tutorial](/en/Development/Mapping/Adaptive-Maps) and [one updated tutorial](/en/Development/Mapping/Adaptive-Mapping-2021) are available.

## Creating maps for the matchmaker pool
The [matchmaker map pool](/en/Play/Client/tmm) consists of a selection of high quality maps selected by the [matchmaking team](/en/Infrastructure/FAF-Teams). To be eligable for inclusion in the map pool, maps have to meet several [technical](/en/Development/Matchmaker/matchmaker-technical-requirements) and [practical](/en/Development/Matchmaker/matchmaker-practical-requirements), as well as quality standards. Maps submitted for review are reviewed according to a [semi-automated reviewing process](/en/Development/Matchmaker/matchmaker-review).

## Campaigns
Experienced mappers may want to attempt creating a campaign. Campaigns are cooperative (Coop) games where up to four players can play together to complete a mission or storyline. Using the FAF launcher, players can play the original campaigns from Supreme Commander and Supreme Commander: Forged Alliance, as well as new community-made Coop maps, using FAF's balanced gameplay.

Coop missions are scripted, with key events, such as unlocking new regions of the map, having been prepared in advance by the campaign designer. This allows campaign designers to tell their own stories, with their own aethestics. Despite its seemingly straightforward nature, the Coop feature has become seriously popular among players. Similarly to AI games, campaigns are the perfect game mode to play with some friends, along with providing a unique challenge otherwise not seen in normal skirmish-type games.

However, creating campaigns maps is significantly more involved than creating a normal map, and requires an understanding of [mission scription.](/en/Development/Missions/Mission-Scripting). To provide new campaign designers with the required information to get started, Speed2 has released a [tutorial series](https://www.youtube.com/playlist?list=PLTEDjzjPnGIrFqmrj_yvOI2icU3dEV_Sc). Furthermore, the official FAF discord has made a channel available for discussing campaign development, where you may find more information.

- [Coop mission making*A video tutorial series by Speed2*](https://www.youtube.com/playlist?list=PLTEDjzjPnGIrFqmrj_yvOI2icU3dEV_Sc)
{.links-list}

## The Scenario file
The scenario file contains ... and provides information to the game on ...
Manual editing of this file is generally not recommended, but may be necessary in some circumstances. [Information on changes to the scenario file is provided here.](/en/Development/Mapping/Further-changes-to-the-scenario-file)

# Mapping Tournaments
Periodically, the FAF community comes together to organize mapping tournaments with the aim of fostering creativity and inspiring mappers to produce exceptional works. These tournaments serve as exciting platforms that challenge map-makers to push the boundaries of their skills and showcase their ingenuity in crafting remarkable and immersive maps. Depending on the tournament, participants may presented with unique challenges and themes, encouraging them to explore innovative concepts and provide an avenue for recognition and celebration of outstanding map-making achievements, as well as encourages collaboration, knowledge sharing, and the evolution of map-making techniques. 

As some map-making competitions place a strong emphasis on thorough documentation of the map creation process and encourage peer review, studying the works of fellow mappers becomes an invaluable means of honing one's own map-making skills. You may find an overview of recent tournaments below.

## 'Princess Burke' mapping tournament

## Legacy forum tournaments

# Other resources
## Discord
## Community-made Assets and other tools
Jip's map-wide decal templates
Klutz's brushes
- [World Heightmapper tool*An online tool to render a section of earth as a heightmap*](https://tangrams.github.io/heightmapper/)
{.links-list}
### Presets from official maps
[Skyboxes, texture layers, lighting, and water presets](https://goo.gl/oA5Xcg)
{.links-list}
### Additional brushes
- [About the Ozonex Editor: Adding custom brushes *A forum tutorial on custom brushes by Jip*](https://forum.faforever.com/topic/277/about-weather-generating-clouds)
{.links-list}
## Veteran mapper workflows and forum threads
Many of the veteran mappers have compiled maps, research notes, and comments on workflow and map design in various forum threads, both on the old and new forum. As much can be learnt from studying how others approach map making, links to these forum threads are provided here.
- [IndexLibrorum's maps and tutorials*A collection of posts on maps, workflows, and Gaea tutorials*](https://forum.faforever.com/topic/6066/index-librorum-s-maps-assorted-projects-and-gaea-tutorials)
- [Svenni_badbwoi's maps*A collection of posts on maps and workflows*](https://forums.faforever.com/viewtopic.php?f=53&t=14976#p153007)
- [MadMax's maps page*A collection of posts on maps made by MadMax*](https://forum.faforever.com/topic/4192/madmax-s-maps-page)
- [Jip's maps and others*A collection of posts on maps and other project by Jip*](https://forum.faforever.com/topic/497/jip-s-maps-and-others)
{.links-list}

## Mapping guidelines for creating FAF versions of existing maps
Todo
