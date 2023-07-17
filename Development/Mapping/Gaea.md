---
title: Using Gaea for FAF Mapping
description: 
published: true
date: 2023-07-17T22:31:52.551Z
tags: mapping, gaea
editor: markdown
dateCreated: 2023-05-09T10:38:02.040Z
---

# Making high quality maps with Gaea - A tutorial series

Welcome to the Gaea Map-Making Tutorials for Forged Alliance Forever (FAF).

I am IndexLibrorum (AKA Prohibitorum) and I've been trialblazing the use of Gaea in FAF mapping. An overview of my work can be found [here](https://forum.faforever.com/topic/6066/index-librorum-s-maps-assorted-projects-and-gaea-tutorials). Being the inexhaustible fount of charity and enlightenment that I am, I have decided to write out this series of tutorials, in which I will explain to you how to make maps in FAF without having to do such tedious things as handpaint terrain and masks. With this series, I aim to save you from the pain that is trying to figure out why your masks somehow have stopped behaving as they should for the 11th time in an hour, and catapult you straight to map-making mastery.

Gaea is a powerful industry-standard terrain generation software that allows you to build hyper-realistic looking terrain for such projects as block buster movies, games by Ubisoft and Blizzard, and whatever NASA has used it for that got their logo to show up on Quadspinner's website. You can also use it to build maps for a—somehow still active—15 year old RTS. Whether you're a seasoned map maker or relatively new to the world of terrain generation, these tutorials should provide you with the basic knowledge and techniques to bring your map-making skills to the next level.

Because the length out these tutorials fairly quickly got out of hand, I've split this series in four chapters. Please note that these tutorials assume you have some basic understanding of map making. While I will discuss some of the basics whenever I feel they are relevant, I'd like to recommend you refer to the various tutorials available on the wiki if you get stuck with anything that is not directly related to Gaea.

> This section uses [*Gaea*, a third-party software developed by Quadspinner](/en/https://quadspinner.com/). As of June 2023, they offer the indie version of their software for free on their website. The indie version is limited to a maximum render resolution of 1k. As a consequence, you will require an upgraded license if you are planning to make maps that are bigger than 20x20km.
{.is-info}

### Terminology
In my conversations with others in the FAF discord's mapping-general channel, I've come to realize that explaining certain concepts can be a bit challenging, primarily due to the lack of clear definitions for some elements. So, to ensure that we're all on the same page, I've compiled a list of common terms.

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

>The table below does not include general mapping terms that are not relevant to these specific tutorials. For an exhaustive overview of general mapping terms, see the general [Mapping](/en/Development/Mapping) page.
{.is-info}

>The above table does not include the specific names for less common terms, such as the names of elements of Gaea, as those are defined in their respective tutorials.
{.is-info}

## 1) Basic Introduction to Mapping with Gaea:
In this tutorial, we'll discuss the fundamentals and guide you through the basics of using Gaea for map creation. We'll explore the user interface, essential tools and techniques for generating terrain, setting up the scale and dimensions, and discuss how to render your heightmap for use in the FAF map editor. Additionally, we'll discuss how you may generate realistic terrain features, including mountains, crater fields, canyons, and more, using the power of procedural generation.

[Link to tutorial 1](/en/Development/Mapping/Gaea/Basic-Introduction)

## 2) Producing Terrain Masks in Gaea:
Terrain masks are crucial for defining texture distribution on your map. In this tutorial, we'll dive into the process of creating terrain masks using Gaea's powerful procedural algorithms and functions.

[Link to tutorial 2](/en/Development/Mapping/Gaea/Terrain-Masks)

## 3) Texturing in Gaea:
This tutorial on texturing in Gaea will teach you how to set up a texturing prototype using the masks you learnt to generate in tutorial two. Using this prototype, you can quickly evaluate your masks and make changes where needed. Additionally we will discuss the use of Satmaps in preparation for creating the map-wide albedo generation we will discussin tutorial four. Lastly, we will discuss how to create custom textures to further improve the aestethics of your map.

[Link to tutorial 3]

## 4) Creating Map-Wide Assets:
With the terrain created and textured, we will take a look at the map-wide assets we can create to bring our maps to the next level. We will discuss how to create a map-wide albedo decal, map-wide normal-map decal, and map-wide shadow decal. Together, these decals will add the final touches to bring your map to life.

[Link to tutorial 4]

## Help and frequently asked questions
To help you on your way, all tutorials include a section on common mistakes and their fixes. If these sections do not help you when you are stuck, please feel free to ask for help in the [FAF discord's](https://discord.gg/SsxPZRbM) mapping-section. The mapping-channels in the FAF discord include two threads containing my research notes and comments on Gaea, which you might find useful. Alternatively, [contact Prohibitorum](https://discord.com/channels/@me/prohibitorum/) on discord directly.
