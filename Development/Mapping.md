---
title: Mapping
description: Map creation for Forged Alliance (Forever)
published: true
date: 2023-07-18T08:42:57.476Z
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
In tutorials and converstations with other mappers we use specific words to refer to specific elements of map making. However, some terms in these contexts may lack precise or consistent definitions, leading to potential misunderstandings and ambiguity. For others, the meaning may be unclear at first glance, making it difficult for beginning mappers to understand what is meant. In order to provide a clear and concise reference for essential concepts in FAF mapping, the [Terminology](/en/Development/Mapping/Terms) section present a list of key terms and their definitions.

# The basics of mapping
Intro on what is needed to create a map. Quick overview of all elements, mention necessary skills if required. Explain where creativity becomes important and where there is room for new stuff.


>Anything below this point needs to be short on text and mostly link to other pages of the wiki. (Remove this note once the page is completed)
{.is-warning}
# Tools and software
## Editors
### Ozonex Editor
[<img align="right" src="/faf_mapeditor_logo.png" width="20%">](/en/Development/Mapping/FA-Forever-Map-Editor)

The [FA-Forever-Map-Editor](/en/Development/Mapping/FA-Forever-Map-Editor) is a new map editor developed for FAF by ozonex. Although perpetually stuck in an unfinished alpha stage, which means the editor is in its testing phase and lacks some of the features of the GPG editor, it is considered in many ways a significant improvement over the GPG editor. Generally, this editor is the recommended editor to use.

### GPG editor
[<img align="right" src="/images/gpgmapeditor/editor_splash.png" width="20%">](/en/Development/Mapping/GPG-Map-Editor)

The [GPG-Map-Editor](/en/Development/Mapping/GPG-Map-Editor) is the editor released by GPG studios and was their internal tool for map development. Note that you require a copy of Supreme Commander (which is *not* Supreme Commander *forged alliance*) to run this editor, as it is dependent on some of the core game files.

## Terrain generation tools
In map-making, terrain heightmaps are typically crafted using manual brush tools (provided by the editor) to sculpt terrain features by hand, offering map-makers precise control over the landscape. However, for those seeking alternative approaches or aiming for more expansive and intricate terrains, specialized terrain generation tools present valuable options to streamline and enhance this process beyond the limitations of traditional hand-sculpting methods.. 

Two prominent tools in this domain are WorldMachine and Gaea. Both WorldMachine and Gaea are specialized software that empowers map-makers to generate realistic and detailed terrains procedurally, employing algorithms to simulate natural geological processes like erosion, weathering, and tectonic movements. These tools allow you to quickly generate and manipulate vast landscapes with a wide range of features like mountains, valleys, and rivers.

For both these tools several tutorials have been made available, the links of which you may find below, under the [*Advanced tutorials*](#AT) section.

## Other tools
### Image-editing tools
Photoshop, gimp, photopea

### Encoding tools
Magick

# Basic Tutorials
Both text and video tutorials link from here
## How to use the editors
Link to related pages. Check if pages contain basics, including: Installation, use, hotkeys, changing map version, other map settings, difference between v60.
## Heightmaps, terrain, and water
## Stratums, textures, and masks
### Custom textures
### Mask generation
## Lighting
## Markers
## Props
### Custom props
## Decals
### Custom decals
## Units
## The map vault
Finished maps need to be uploaded to the map vault. By uploading to the vault, you agree to [the vault guidelines](/en/Development/Vault/Guidelines) and [vault rules](/en/Development/Vault/Rules).

# Advanced tutorials {#AT}
## Map files and scripts
### The Scenario file
The scenario file contains ... and provides information to the game on ...
Manual editing of this file is generally not recommended, but may be necessary in some circumstances. [Information on changes to the scenario file is provided here.](/en/Development/Mapping/Further-changes-to-the-scenario-file)

### Scripts

## WorldMachine

## Gaea
[<img align="right" src="/images/mapping/gaea/gaea_general.png" width="20%">](/en/Development/Mapping/Gaea)

Gaea is a terrain generation tool not unlike WorldMachine, though significantly more modern. The free version of Gaea allows you to create heightmaps up to a 1K resolution, which corresponds to a maximum map size of 20x20KM. 

[A tutorial series on using Gaea for FAF mapping](/en/Development/Mapping/Gaea) was written by IndexLibrorum (AKA Prohibitorum) and introduces the basics of Gaea, how to create terrain, how to create stratum masks, how to texture with Gaea, and how to create map-wide assets.

## AI
Artificial Intelligence (AI) provide players with computer-controlled opponents of different skill levels. This feature has garnered significant popularity within the FAF community, with over half of the player base actively participating in AI games. By providing players with the opportunity to challenge intelligent computer opponents, AI enhances the richness and diversity of gameplay options, catering to a wide range of preferences and skill levels. Consequently, maps should aim to be AI compatible, and be designed with AI in mind.

For a comprehensive understanding of how AI functions in FAF, you may refer to the main page on AI. Relevant information in the context of mapping is provided by this tutorial on [best practises to create AI friendly maps](/en/Development/Mapping/ai-friendly-maps). It is recommended to follow these guidelines to ensure your maps are compatible with for AI.

## Clouds

## Skyboxes

## Adaptive mapping
Prior to the introduction of adaptive maps, it was a common practice to upload multiple versions of the same map, each modified with slight resource variations (e.g., Canis 4v4, Canis 5v5). However, with the advent of the adaptive map script developed by CookieNoob and KeyBlue (with further modifications by svenni_badbwoi), this is no longer required. Adaptive maps enable the consolidation of several similar map versions into a single map, offering advanced map settings directly accessible from the game lobby. Such settings may allow players to adjust map resources dynamically based on the number of players, as well as add or remove resources, units, and wrecks. Two tutorials, [one legacy tutorial](/en/Development/Mapping/Adaptive-Maps) and [one updated tutorial](/en/Development/Mapping/Adaptive-Mapping-2021) are available.

## Campaigns
Experienced mappers may want to create a campaign. This requires an understanding of [mission scription.](/en/Development/Missions/Mission-Scripting). Some maps are already available for [adaption to campaign-related content](/en/Development/Mapping/campaign-ready-maps).

## Creating maps for the matchmaker pool
The [matchmaker map pool](/en/Play/Client/tmm) consists of a selection of high quality maps selected by the [matchmaking team](/en/Infrastructure/FAF-Teams). To be eligable for inclusion in the map pool, maps have to meet several [technical](/en/Development/Matchmaker/matchmaker-technical-requirements) and [practical](/en/Development/Matchmaker/matchmaker-practical-requirements), as well as quality standards. Maps submitted for review are reviewed according to a [semi-automated reviewing process](/en/Development/Matchmaker/matchmaker-review).

# Mapping Tournaments
Periodically, the FAF community comes together to organize mapping tournaments with the aim of fostering creativity and inspiring mappers to produce exceptional works. These tournaments serve as exciting platforms that challenge map-makers to push the boundaries of their skills and showcase their ingenuity in crafting remarkable and immersive maps. Depending on the tournament, participants may presented with unique challenges and themes, encouraging them to explore innovative concepts and provide an avenue for recognition and celebration of outstanding map-making achievements, as well as encourages collaboration, knowledge sharing, and the evolution of map-making techniques. 

As some map-making competitions place a strong emphasis on thorough documentation of the map creation process and encourage peer review, studying the works of fellow mappers becomes an invaluable means of honing one's own map-making skills. You may find an overview of recent tournaments below.

## 'Princess Burke' mapping tournament

## Legacy forum tournaments

# Other resources
## Discord
## Community-made Assets
### Map-wide decal templates
### Skyboxes, texture layers, lighting, and water presents from official maps
### Additional brushes
## Veteran Mapper Workflows
## Mapping guidelines for creating FAF versions of existing maps

## Troubleshooting
The map editor is a powerful tool for creating custom maps in Supreme Commander: Forged Alliance, but like with any software, you might encounter various technical issues that can prevent you from creating maps that meet your vision. These issues can range from minor annoyances to serious problems that make it impossible to complete your map. [In the troubleshooting section](/en/Development/Mapping/faf-map-editor-troubleshooting), we'll cover some common technical issues you might encounter while working with the map editor and related files.