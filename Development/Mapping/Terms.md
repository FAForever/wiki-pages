---
title: Terminology
description: An exhaustive list of terms and definitions
published: true
date: 2023-07-19T16:54:14.951Z
tags: terms, terminology, definitions, the words mason, what do they mean
editor: markdown
dateCreated: 2023-07-18T06:35:43.693Z
---

In tutorials and converstations with other mappers we use specific words to refer to specific elements of map making. However, some terms in these contexts may lack precise or consistent definitions, leading to potential misunderstandings and ambiguity. For others, the meaning may be unclear at first glance, making it difficult for beginning mappers to understand what is meant. In order to provide a clear and concise reference for essential concepts in FAF mapping, this section present a list of key terms and their definitions. Definitions for terms that are not specific to FAF mapping may be found in the [Glossary](/en/FAQ/Glossary).

>The lists below may not include some very specific definitions for less common terms, such as the names of elements of Gaea or WorldMachine, as those are defined in their respective tutorials.
{.is-info}

# General terms
| Term | Definition | Term | Definition |
|-|-|-|-|
|Editor *or* Ozonex editor *or* FAF editor|This is the program that you use to assemble all elements of a map and export it in such a way that you may use it in FAF. This editor is the most recent of the two and significantly more modern.|Old editor *or* GPG editor |The legacy editor, released in 2007. *Note:* Unless otherwise specified, 'editor' refers to the *Ozonex Editor*. 
|Map|The completed assembly of terrain, textures, stratum masks, decals, and other elements that together form the world that you may play games in.|Rendering *or* Exporting|Saving an image, such as assets created in Gaea, at a certain resolution and in a specific file format.|
|FAF client|The software you use to browse FAF lobbies, find new maps, watch replays, and install mods| Map vault *or* vault| The database of FAF maps that you may access through the FAF client, and to which you may upload your own maps|

# Map elements
## Heightmaps and terrain
|-|-|-|-|
|Terrain|The bare geometry of the map that forms the moutains, cliffs, ground, bumps, and crevaces. The shape of the terrain is defined by the heightmap.|Heightmap|A greyscale image of a certain size, for which the brightness of each pixel corresponds to the height of a specific point of the terrain.|
|Assets|A general term for textures, normal maps, or masks, or other files and materials used to create a map.|Stratum layer *or* Stratum|The layer that contains a texture and its settings, its corresponding normal map, and a stratum mask. Each map may at most use 9 stratums, the lower of which does not accept a stratum mask.|
|Texture layer *or* Texture|The tiled images that you apply to the terrain using masks, which bring colour and patterns to the terrain. You may apply one texture per stratum, giving you at most 9 textures per map.|Stratum mask *or* Texture mask *or* Mask|A greyscale image, for which the brightness of each pixel corresponds with the opacity of the corresponding texture. *Note*: 'mask' is a general term that is also used as an element in Gaea.|
|Grid overlay *or* grid|A grid overlay that you can toggle in the editor by pressing <kbd>G</kbd>. Usefull for aligning map markers.|Slope overlay *or* Slope debug|A colour overlay that can be used to check the flatness or lack thereof of the terrain. Can be toggled by pressing <kbd>Ctrl+G</kbd>|
## Water

## Decals
|-|-|-|
|Decals|Decals are image files that are often either an albedo or a normal map. These images may be freely positioned, scaled, and rotated on the map, and are an essential part to add additional detail to the map.|Normal map|Normal maps, also known as bump maps, are used for faking the lighting of bumps and dents, and are used to fake complex geometry where there is none. These images use the red/alpha channels to encode their information and are recognizably different from other assets.|
|Map-wide decals *or* Map-wide assets|A specific subcategory of decals that are precisely placed to align with the terrain and cover the whole map. Common map-wide assets include a map-wide shadow decal, a map-wide normal map, or a map-wide albedo decal.|Map-wide normal map|A normal map that covers the whole map and is precisely aligned with the terrain. Using this asset, you can fake small details which the resolution of your heightmap normally would not allow, such as weathering patterns.|
|Map-wide shadow decal|A transparent decal that covers the whole map and precisely aligns with the terrain to add shadows to the map.|Map-wide albedo decal|A map-wide decal precisely aligned to the terrain to add extra colour to the map, supporting the texture layers and adding extra detail.|
## Lighting

## Markers and AI

## Props

## Units




# Terrain features and map design

# Gaea specific terms