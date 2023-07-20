---
title: Mapping
description: Map creation for Forged Alliance (Forever)
published: true
date: 2023-07-20T07:19:34.647Z
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

- [FA-Forever-Map-Editor *The modern editor provided by Ozonex et al.*](/en/Development/Mapping/FA-Forever-Map-Editor)
{.links-list}

### GPG editor
The [GPG-Map-Editor](/en/Development/Mapping/GPG-Map-Editor) is the editor released by GPG studios and was their internal tool for map development. Note that you require a copy of Supreme Commander (which is *not* Supreme Commander *forged alliance*) to run this editor, as it is dependent on some of the core game files.
- [GPG-Map-Editor *The legacy editor provided by GPG studios*](/en/Development/Mapping/GPG-Map-Editor)
{.links-list}

## Terrain generation tools
In map-making, terrain heightmaps are typically crafted using manual brush tools (provided by the editor) to sculpt terrain features by hand, offering map-makers precise control over the landscape. However, for those seeking alternative approaches or aiming for more expansive and intricate terrains, specialized terrain generation tools present valuable options to streamline and enhance this process beyond the limitations of traditional hand-sculpting methods.. 

Two prominent tools in this domain are WorldMachine and Gaea. Both WorldMachine and Gaea are specialized software that empowers map-makers to generate realistic and detailed terrains procedurally, employing algorithms to simulate natural geological processes like erosion, weathering, and tectonic movements. These tools allow you to quickly generate and manipulate vast landscapes with a wide range of features like mountains, valleys, and rivers.

For both these tools several tutorials have been made available, the links of which you may find below, under the [Advanced tutorials](#AT) section.

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

# Basic Tutorials
## Heightmaps, terrain, and water
The most important element of a map is the heightmap, which defines the elevation and topographical features, determining the shape and contours of the landscape. Once the heightmap is ready, it forms the foundation upon which other map elements are integrated.

In essence, a heightmap is a grayscale image where different shades of gray represent varying elevations. Darker areas correspond to lower points, such as valleys and depressions, while lighter areas represent higher elevations, such as hills and mountains. By manipulating the grayscale values, map-makers can create intricate landscapes with diverse topographical features.

To create a heightmap, various methods can be used. The most basic approach involves using the [brushes provided by either of the two editors](https://wiki.faforever.com/en/Development/Mapping/FA-Forever-Map-Editor#heightmap-brush), which allow you to manually sculpt the terrain. Alternatively, map-makers can craft heightmaps manually using graphic editing software like Adobe Photoshop or GIMP. By painting the grayscale values, you can sculpt the terrain according to your creative vision. An advanced approach involves  specialized terrain generation software like WorldMachine or [Gaea](#Gaea), which use algorithms to simulate natural geological processes, generating realistic and organic terrains. 

The placement of water in a map is directly influenced by the terrain's elevation. Water is set as a flat plane at a specific height, and any part of the terrain with an elevation below that set height will be submerged by the water. As you sculpt the terrain, the varying elevations defined directly impact where the water will be placed. When the terrain's elevation is lower than the set water height, that portion of the map will become submerged, creating lakes, rivers, or other bodies of water. 

[Water settings](/en/Development/Mapping/FA-Forever-Map-Editor#water) can be adjusted to enhance the visual representation of water, such as its transparency, color, or reflections. These settings, in conjunction with the terrain, contribute to the overall aesthetics of the water within the map.

Lastly, you are able to define specify the [terrain type](/en/Development/Mapping/FA-Forever-Map-Editor#terrain-type) of specific areas of your terrain. Terrain type primarily affects the interaction between units and the terrain visually, generating specific dust patterns when units move over the terrain. However, there are some *blocking-type* terrain types available that will prohibit units from moving over areas marked as such.

## Tabs {.tabset}
### Terrain
- [Creating a map: Heightmaps*Part of the official video tutorial series on mapmaking*](https://www.youtube.com/watch?v=UNajB0EOKnM&list=PL0nxuIUIjpFvM-lU3h6ROtWsoC_ikkaAs)
- [Ozonex editor heightmap tools *Detailed explanation of the tools available in the editor, including water and terrain-type settings*](/en/Development/Mapping/FA-Forever-Map-Editor)
- [ Mountains | GPG editor*A video tutorial on making mountains in the GPG editor*](https://www.youtube.com/watch?v=nm5NVD17kvw)
- [Mountains | Ozonex editor*A video tutorial on making mountains in the Ozonex editor*](https://www.youtube.com/watch?v=h26369gnTEo)
{.links-list}

### Water
- [About water: Introduction*Pt.1 of the forum post series on water by Jip*](https://forum.faforever.com/topic/59/about-water-introduction)
- [About water: Water settings*Pt.2 of the forum post series on water by Jip*](https://forum.faforever.com/topic/64/about-water-settings)
- [About water: Wave generation*Pt.3 of the forum post series on water by Jip*](https://forum.faforever.com/topic/71/about-water-wave-generation)
- [About water: Brushes*Pt.4 of the forum post series on water by Jip*](https://forum.faforever.com/topic/73/about-water-brushes)
- [About water: Ramps*Pt.5 of the forum post series on water by Jip*](https://forum.faforever.com/topic/65/about-water-water-ramps)
- [About water: Environment maps*Pt.6 of the forum post series on water by Jip*](https://forum.faforever.com/topic/72/about-water-environment-maps)
- [About water: Waves and normal maps*Pt.7 of the forum post series on water by Jip*](https://forum.faforever.com/topic/74/about-water-waves-and-normal-maps)
- [About water: Pixelated water*Pt.8 of the forum post series on water by Jip*](https://forum.faforever.com/topic/48/about-water-pixelated-water)
{.links-list}

 
## Stratums, textures, and masks

- [Texture painting*Video tutorial on how to blend textures in the Ozonex editor*](https://www.youtube.com/watch?v=nzTnDc2vKU4)
- [Creating a map: Stratum layers pt. 1*Part of the official video tutorial series on mapmaking*](https://www.youtube.com/watch?v=cVb_w0-REZc&list=PL0nxuIUIjpFvM-lU3h6ROtWsoC_ikkaAs&index=4)
- [Creating a map: Stratum layers pt. 2*Part of the official video tutorial series on mapmaking*](https://www.youtube.com/watch?v=lWWdLS2a5VU&list=PL0nxuIUIjpFvM-lU3h6ROtWsoC_ikkaAs&index=5)
{.links-list}
### Custom textures
- [Custom textures*Video tutorial on how to add custom textures*](https://www.youtube.com/watch?v=_wXK0aYnz70)
{.links-list}
### Mask generation

## Markers and resources
- [Creating a map: Resources*Part of the official video tutorial series on mapmaking*](https://www.youtube.com/watch?v=s4-DGucm9eQ&list=PL0nxuIUIjpFvM-lU3h6ROtWsoC_ikkaAs&index=2)
{.links-list}

## Props
- [Creating a map: Trees and rocks*Part of the official video tutorial series on mapmaking*](https://www.youtube.com/watch?v=6oDs1brYB_0&list=PL0nxuIUIjpFvM-lU3h6ROtWsoC_ikkaAs&index=3)
{.links-list}

  
### Custom props

## Decals
- [Creating a map: Decals pt.1*Part of the official video tutorial series on mapmaking*](https://www.youtube.com/watch?v=YhDyCTf8cyI&list=PL0nxuIUIjpFvM-lU3h6ROtWsoC_ikkaAs&index=6)
- [Creating a map: Decals pt.2*Part of the official video tutorial series on mapmaking*](https://www.youtube.com/watch?v=vRAvQIP3NoI&list=PL0nxuIUIjpFvM-lU3h6ROtWsoC_ikkaAs&index=7)
{.links-list}

## Lighting
- [Creating a map: Lighting*Part of the official video tutorial series on mapmaking*](https://www.youtube.com/watch?v=7TXHY1_smwU&list=PL0nxuIUIjpFvM-lU3h6ROtWsoC_ikkaAs&index=11)
{.links-list}

## Units
- [Creating a map: (Wrecked) Civilians*Part of the official video tutorial series on mapmaking*](https://www.youtube.com/watch?v=16zuZ60XHbk&list=PL0nxuIUIjpFvM-lU3h6ROtWsoC_ikkaAs&index=12)
{.links-list}

## The map vault
Finished maps need to be uploaded to the map vault. By uploading to the vault, you agree to [the vault guidelines](/en/Development/Vault/Guidelines) and [vault rules](/en/Development/Vault/Rules).

- [Maptesting without uploading*A tutorial video on how to test a map without having to upload it to the vault*](https://www.youtube.com/watch?v=EQbP_mXER7M)
{.links-list}
## Other basic tutorials
- [What makes a bad map?*Video tutorial explaining guidelines for map design by TheDuelist*](https://www.youtube.com/watch?v=PqHBJkqqf38)
- [Forum post | Making bad maps better*A lengthy forumpost with images by Biass*](https://forums.faforever.com/viewtopic.php?f=53&t=18647)
{.links-list}

# Advanced tutorials {#AT}
## Map files and scripts
### The Scenario file
The scenario file contains ... and provides information to the game on ...
Manual editing of this file is generally not recommended, but may be necessary in some circumstances. [Information on changes to the scenario file is provided here.](/en/Development/Mapping/Further-changes-to-the-scenario-file)

### Changing the map version manually
Although the Ozonex editor allows you to quickly create a new version of your map, the GPG editor requires some additional steps.
- [Making a new map version guide for 2018*A forum post tutorial by Biass*](https://forums.faforever.com/viewtopic.php?f=53&t=16397#p165578)
{.links-list}

### Scripts
## Custom assets
- [About decals: Introduction*Pt. 1 of the forum post series on decals by Jip*](https://forum.faforever.com/topic/24/about-decals-introduction-part-1)
- [About decals: Converting normal maps*Pt. 2 of the forum post series on decals by Jip*](https://forum.faforever.com/topic/245/about-decals-converting-normal-maps)
- [About decals: WorldMachine templates*Pt. 3 of the forum post series on decals by Jip*](https://forum.faforever.com/topic/1090/about-decals-world-machine-templates)
- [About decals: Generating map-wide normal texture*Pt. 4 of the forum post series on decals by Jip*](https://forum.faforever.com/topic/785/about-decals-generating-a-map-wide-normal-texture)
- [About decals: Generating a map-wide lighting texture*Pt. 5 of the forum post series on decals by Jip*](https://forum.faforever.com/topic/786/about-decals-generating-a-map-wide-lighting-texture)
{.links-list}
- [About custom decals and stratums*A forum post by Jip*](https://forum.faforever.com/topic/19/about-custom-decals-and-stratums)
- [Adding custom textures to FAF*A video tutorial by Morax*](https://www.youtube.com/watch?v=_wXK0aYnz70)
## WorldMachine
- [Using Worldmachine and the GPG editor to make a map*A video tutorial series by Lionhardt*](https://www.youtube.com/playlist?list=PLLKHtCMTwATBTx6vrN1ty6xFAByQgh5B-)
- [World machine tutorial: Basic shapes*A video tutorial on the basics of WorldMachine*](https://www.youtube.com/watch?v=nlWssphJMkY)
{.links-list}

## Gaea {#Gaea}
[<img align="right" src="/images/mapping/gaea/gaea_general.png" width="20%">](/en/Development/Mapping/Gaea)

Gaea is a terrain generation tool not unlike WorldMachine, though significantly more modern. The free version of Gaea allows you to create heightmaps up to a 1K resolution, which corresponds to a maximum map size of 20x20KM. 

A tutorial series on using Gaea for FAF mapping was written by IndexLibrorum (AKA Prohibitorum) and introduces the basics of Gaea, how to create terrain, how to create stratum masks, how to texture with Gaea, and how to create map-wide assets.
- [A tutorial series on using Gaea for FAF mapping*An extensive tutorial series on Gaea by IndexLibrorum*](/en/Development/Mapping/Gaea)
{.links-list}

## AI
Artificial Intelligence (AI) provide players with computer-controlled opponents of different skill levels. This feature has garnered significant popularity within the FAF community, with over half of the player base actively participating in AI games. By providing players with the opportunity to challenge intelligent computer opponents, AI enhances the richness and diversity of gameplay options, catering to a wide range of preferences and skill levels. Consequently, maps should aim to be AI compatible, and be designed with AI in mind.

For a comprehensive understanding of how AI functions in FAF, you may refer to the main page on AI. Relevant information in the context of mapping is provided by this tutorial on [best practises to create AI friendly maps](/en/Development/Mapping/ai-friendly-maps). It is recommended to follow these guidelines to ensure your maps are compatible with for AI.

- [About markers: AI markers*Pt.1 of the forum post series on AI markers by Jip*](https://forum.faforever.com/topic/145/about-markers-ai-markers)
- [About markers: Movement and pathing markers*Pt.2 of the forum post series on AI markers by Jip*](https://forum.faforever.com/topic/343/about-markers-movement-pathing-markers)
- [Adding AI markers using the GPG editor*A video tutorial by Plasia*](https://www.youtube.com/watch?v=KDO8zf2afhc)
{.links-list}

## Clouds
- [About weather: Generating clouds*A forum tutorial on cloud generation by Jip*](https://forum.faforever.com/topic/277/about-weather-generating-clouds)
{.links-list}

## Skyboxes

## Adaptive mapping
Prior to the introduction of adaptive maps, it was a common practice to upload multiple versions of the same map, each modified with slight resource variations (e.g., Canis 4v4, Canis 5v5). However, with the advent of the adaptive map script developed by CookieNoob and KeyBlue (with further modifications by svenni_badbwoi), this is no longer required. Adaptive maps enable the consolidation of several similar map versions into a single map, offering advanced map settings directly accessible from the game lobby. Such settings may allow players to adjust map resources dynamically based on the number of players, as well as add or remove resources, units, and wrecks. Two tutorials, [one legacy tutorial](/en/Development/Mapping/Adaptive-Maps) and [one updated tutorial](/en/Development/Mapping/Adaptive-Mapping-2021) are available.

## Campaigns
Experienced mappers may want to create a campaign. This requires an understanding of [mission scription.](/en/Development/Missions/Mission-Scripting). Some maps are already available for [adaption to campaign-related content](/en/Development/Mapping/campaign-ready-maps).
- [Coop mission making*A video tutorial series by Speed2*](https://www.youtube.com/playlist?list=PLTEDjzjPnGIrFqmrj_yvOI2icU3dEV_Sc)
{.links-list}

## Creating maps for the matchmaker pool
The [matchmaker map pool](/en/Play/Client/tmm) consists of a selection of high quality maps selected by the [matchmaking team](/en/Infrastructure/FAF-Teams). To be eligable for inclusion in the map pool, maps have to meet several [technical](/en/Development/Matchmaker/matchmaker-technical-requirements) and [practical](/en/Development/Matchmaker/matchmaker-practical-requirements), as well as quality standards. Maps submitted for review are reviewed according to a [semi-automated reviewing process](/en/Development/Matchmaker/matchmaker-review).

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

## Troubleshooting
The map editor is a powerful tool for creating custom maps in Supreme Commander: Forged Alliance, but like with any software, you might encounter various technical issues that can prevent you from creating maps that meet your vision. These issues can range from minor annoyances to serious problems that make it impossible to complete your map. [In the troubleshooting section](/en/Development/Mapping/faf-map-editor-troubleshooting), we'll cover some common technical issues you might encounter while working with the map editor and related files.