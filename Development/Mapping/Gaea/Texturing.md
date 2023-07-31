---
title: Texturing in Gaea
description: A tutorial on the process of texturing the terrain in Gaea
published: true
date: 2023-07-31T17:33:01.033Z
tags: mapping, gaea, textures, texturing
editor: markdown
dateCreated: 2023-07-30T10:48:41.754Z
---

# Gaea tutorial: Texturing in Gaea
Introduction text similar to previous tutorials.

This tutorial focusses on texturing your maps in Gaea. Using Gaea to texture your map can be used as a way to quickly experiment with different aestethics, to verify your masks are set up correctly, and to generate map-wide albedo decals. This tutorial will explain how to set up a a graph in Gaea to simulate how the FAF editor applies textures. That is—a way that simulates nine layers that stack on top of eachother, with layer masks determining where textures are applied.

## A review of texturing basics
This workflow aims to emulate the way that textures are applied in FAF. We will setup a framework that simulates a maximum of eight stratums, stacked on top of eachother. However, the texturing in Gaea will always be an approximation, as the approach differs in a few critical areas. Firstly, FAF uses tiled textures: textures are repeated over the map and exposed to certain parts of the terrain using masks. Interestingly, this results in both higher and lower resolution textures. The resolution of the textures for each pixel of the heightmap will be bigger in game: the tiling of the textures, especially at a low zoom-level, will result in far higher pixel density per area of the map than compared to a map-wide decal. However, since these textures are tiled, the textures aren't specific for the terrain except in the sense that they are exposed to specific parts of the terrain. Creating a map-wide albedo decal in gaea however will allow you to assign specific colours and texture to specific parts of the map, but due to file size restrictions you will not be able to approach the resolution per heightmap-pixel that tiled textures will provide you.

As a result, map-wide albedo decals should not be used to texture the full map at once. Although 16K textures might suffice for 5km maps, generally the resulting file size makes actually using this approach prohibitive. A better method is to create a textured map in Gaea,

Due to this, the resolution of the textures in the game can be of higher quality than the map-wide textures produced in Gaea, although they are less specific to the terrain.



## Prerequisites

This process is dependent on masks, a tutorial for which is available here. 

