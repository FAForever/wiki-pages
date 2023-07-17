---
title: Mapping
description: Map creation for Forged Alliance (Forever)
published: true
date: 2023-07-17T23:36:41.545Z
tags: mapping, map, maps
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
{.align-right}

## Terminology
Some terms in the map-making context may lack precise or consistent definitions, leading to potential misunderstandings and ambiguity. In order to provide a clear and concise reference for essential concepts in FAF mapping, this section present a list of key terms and their definitions. 

| Term | Definition | Term | Definition |
|-|-|-|-|
|Editor *or* Ozonex editor *or* FAF editor|This is the program that you use to assemble all elements of a map and export it in such a way that you may use it in FAF. This editor is the most recent of the two and significantly more modern. You may download the editor [here.](/en/Development/Mapping/FA-Forever-Map-Editor)|Old editor *or* GPG editor |The older editor, released in 2007, which you may download [here.](/en/Development/Mapping/GPG-Map-Editor). *Note:* Unless otherwise specified, 'editor' refers to the *Ozonex Editor*. 
|Map|The completed assembly of terrain, textures, stratum masks, decals, and other elements that together form the world that you may play games in.|Terrain|The bare geometry of the map that forms the moutains, cliffs, ground, bumps, and crevaces. The shape of the terrain is defined by the heightmap.|
|Heightmap|A greyscale image of a certain size, for which the brightness of each pixel corresponds to the height of a specific point of the terrain.|Assets|A general term for textures, normal maps, or masks, or other files and materials used to create a map.|
|Stratum layer *or* Stratum|The layer that contains a texture and its settings, its corresponding normal map, and a stratum mask. Each map may at most use 9 stratums, the lower of which does not accept a stratum mask.|Texture layer *or* Texture|The tiled images that you apply to the terrain using masks, which bring colour and patterns to the terrain. You may apply one texture per stratum, giving you at most 9 textures per map.|
|Stratum mask *or* Texture mask *or* Mask|A greyscale image, for which the brightness of each pixel corresponds with the opacity of the corresponding texture. *Note*: 'mask' is a general term that is also used as an element in Gaea.|Normal map|Normal maps, also known as bump maps, are used for faking the lighting of bumps and dents, and are used to fake complex geometry where there is none. These images use the red/alpha channels to encode their information and are recognizably different from other assets.|
Decals|Decals are image files that are often either an albedo or a normal map. These images may be freely positioned, scaled, and rotated on the map, and are an essential part to add additional detail to the map.|Map-wide decals *or* Map-wide assets|A specific subcategory of decals that are precisely placed to align with the terrain and cover the whole map. Common map-wide assets include a map-wide shadow decal, a map-wide normal map, or a map-wide albedo decal.|
|Map-wide normal map|A normal map that covers the whole map and is precisely aligned with the terrain. Using this asset, you can fake small details which the resolution of your heightmap normally would not allow, such as weathering patterns.|Map-wide shadow decal|A transparent decal that covers the whole map and precisely aligns with the terrain to add shadows to the map.|
|Map-wide albedo decal|A map-wide decal precisely aligned to the terrain to add extra colour to the map, supporting the texture layers and adding extra detail.|Rendering *or* Exporting|Saving an image, such as assets created in Gaea, at a certain resolution and in a specific file format.|

>The above table does not include the specific names for less common terms, such as the names of elements of Gaea or WorldMachine, as those are defined in their respective tutorials.
{.is-info}

# Tools and software
## Editors
### Ozonex Editor


### GPG editor

## Terrain generation tools
### WorldMachine
### Gaea

## Other tools
### Image-editing tools
Photoshop, gimp, photopea

### Encoding tools
Magick

# Tutorials

## Video tutorials

# Adaptive mapping
### Updated
### Obsolete version

# AI

# Mapping Tournaments
## Princess Burke

# Other resources
## Discord
## Troubleshooting