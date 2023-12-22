---
title: Creating Map-Wide Assets
description: A tutorial on the process of creating map-wide assets 
published: true
date: 2023-12-22T13:44:34.907Z
tags: gaea, decal, shadow, normal, albedo
editor: markdown
dateCreated: 2023-12-22T12:44:57.314Z
---

# Gaea tutorial: Creating map-wide assets in Gaea
This tutorial focuses on creating map-wide assets in Gaea. These tutorial will discuss the creation of custom shadows, map-wide normals, and map-wide albedo decals. Additionally, this tutorial will explain the two main ways these assets can be applied to your map, and will include a discussion on the newly developed shaders.

>When specific nodes are referenced, they are highlighted like this: `Node`. Specific parameters for these nodes are written like this: `Slope, 30, 90, 0`, to specify a `Slope` node with Parameters 30 (min), 90 (Max), and 0 (Falloff).
{.is-info}

## Prerequisites
This tutorial assumes you've got a basic understanding of image editing and FAF mapping. An understanding of Gaea is also required: while I will discuss the relevant nodes and how they work, I will leave familiarizing yourself with the software for self study. Watch a few youtube tutorials on the basics, or read the general introduction to Gaea [here](https://docs.quadspinner.com/Guide/index.html). As the techniques described in this tutorial use elements discussed in the previous tutorials on masks and texturing, it is highly recommended to go through these tutorials first.

Required for this tutorial is a copy of Gaea (the indie version is free to use and more than sufficient for maps up to 20km), which can be downloaded [here](https://quadspinner.com/download). Additionally, an image editor such as Photoshop or Gimp is required, though the free to use online photoshop-clone [Photopea](https://www.photopea.com/) works fine too. Lastly, you will need the the FAF map editor.

As with texturing in the FAF editor, applying textures to specific areas of the terrain requires masks. Creating masks in Gaea is relatively simple, but allows for high detail and complexity. As such, a seperate tutorial has been made available here. 

- [General introduction to Gaea*Official documentation*](https://docs.quadspinner.com/Guide/index.html)
- [Producing terrain masks in Gaea*Producing stratum masks for texturing*](/en/Development/Mapping/Gaea/Terrain-Masks)
{.links-list}

## Terminology
In my conversations with others in the FAF discord's mapping-general channel, I've come to realize that explaining certain concepts can be a bit challenging, primarily due to the lack of clear definitions and names for some elements. To ensure that we're all on the same page, please refer to the [terminology page](/en/Development/Mapping/Terms) for definitions of mapping-related terms.

In this tutorial specifically, I will be using the noun *texture* to mean those little tile-able images you may use in the FAF editor to cover a stratum. The verb *to texture* will be used to refer to everything that has to do with applying colour and textures to the terrain. When using colour-nodes in Gaea to add colour to the terrain, I will be refering to the product of those nodes as a *texture design*  or *map design*. Such a *map design* can be used to create what other tutorials refer to as *map wide albedo-decals* or *texture decals*, the use of which is explained in a seperate tutorial.

>Note that the terminology list does not include the specific names for less common terms, such as the names of elements of Gaea, as those are defined in their respective tutorials.

# The use and creation of map-wide assets
## General introduction to map-wide assets
## Map-wide shadows
## Map-wide normals
## Map-wide albedo

# Applying map-wide assets to maps
## As decals
### Decal presets
## Using the new shaders
### General introduction new shaders
### Creating combined shader-accepted files in Gaea
#### Shadows and albedo
#### Normals



