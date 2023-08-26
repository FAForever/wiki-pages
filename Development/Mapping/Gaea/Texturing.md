---
title: Texturing in Gaea
description: A tutorial on the process of texturing the terrain in Gaea
published: true
date: 2023-08-26T08:53:55.922Z
tags: mapping, gaea, textures, texturing
editor: markdown
dateCreated: 2023-07-30T10:48:41.754Z
---

# Gaea tutorial: Texturing in Gaea
Introduction text similar to previous tutorials.

This tutorial focusses on texturing your maps in Gaea. Using Gaea to texture your map can be used as a way to quickly experiment with different aestethics, to verify your masks are set up correctly, and to generate map-wide albedo decals. This tutorial will explain how to set up Gaea in a way that simulates how the FAF editor applies textures, and how to use this to create a textured map.

## Prerequisites
As with texturing in the FAF editor, applying textures to specific areas of the terrain requires masks. Creating masks in Gaea is relatively simple, but allows for high detail and complexity. As such, a seperate tutorial has been made available here. 

- [Producing terrain masks in Gaea*Producing stratum masks for texturing*](/en/Development/Mapping/Gaea/Terrain-Masks)
{.links-list}

## Terminology
In my conversations with others in the FAF discord's mapping-general channel, I've come to realize that explaining certain concepts can be a bit challenging, primarily due to the lack of clear definitions for some elements. To ensure that we're all on the same page, please refer to the [terminology page](/en/Development/Mapping/Terms) for definitions of mapping-related terms.

>Note that the terminology list does not include the specific names for less common terms, such as the names of elements of Gaea, as those are defined in their respective tutorials.
{.is-info}

# A review of texturing basics
This workflow aims to emulate the way that textures are applied in FAF. We will setup a graph that simulates a maximum of nine stratums, one base stratum and 8 stratums with accompanying stratum masks, stacked on top of eachother. However, the texturing in Gaea will always be an approximation of what the map will look like in the FAF editor, as the approach differs in a few critical areas. Firstly, FAF uses tiled textures: textures are repeated over the map and exposed to certain parts of the terrain using masks. Interestingly, in some way this results in both higher and lower resolution. The resolution of the textures for each pixel of the heightmap will be bigger in game: the tiled textures, especially at a low zoom-level, will result in far higher pixel density per area of the map than compared to a map-wide decal. However, since these textures are tiled, the textures aren't specific to individual pixels of the terrain heightmap, except in the sense that they are exposed to specific parts of the terrain. 

Creating a map-wide albedo decal in Gaea however, will allow you to assign specific colours and texture to specific parts of the map, but due to file size restrictions you will not be able to approach the resolution per heightmap-pixel that tiled textures will provide you. Although 16K textures might suffice for 5km maps, generally the resulting file size makes  using this approach prohibitive. As a result, map-wide albedo decals should not be depended on to texture the full map without support from the tiled textures. 

A better method, to get the best of both approaches, is to create a textured map in Gaea, use the result to render a map-wide albedo decall, and use that decall to support and enhance the textures applied by using the stratum layers and stratum masks. As the approach here detailed requires you to setup stratum masks anyway, using this method should not be much more effort.

# Colour nodes
To texture your heightmap, there are several important nodes that you should familiarize yourself with. These nodes generally are coloured purple, designating that these nodes provide or process colour-data. 

A basic node that creates colour is the `QuickColor` node, which generates a gradient using two selected colours. This gradient is applied to the heightmap using the height values: the first colour is assigned to the highest part of the heightmap, and the second colour is applied to the lowest part, with all other colours of that gradient applied to the values in between these two extremes.



# Simulating the FAF editor
# Common approaches
# Rendering a map-wide albedo decal
Many aspects similar to creating map-wide normal maps, so all information combined in one tutorial.
# Creating custom textures in Gaea
# Common errors and checklist
## Remaining questions

If you are left with questions or need help, your best bet is to check with people in the FAF discord Mapping-General channel. Alternatively, you may send me (IndexLibrorum, or Prohibitorum) a PM on discord, or leave a message on the forum.