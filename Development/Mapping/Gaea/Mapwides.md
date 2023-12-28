---
title: Creating Map-Wide Assets
description: A tutorial on the process of creating map-wide assets 
published: true
date: 2023-12-28T08:39:01.302Z
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

In this tutorial specifically, map-wide assets are often refered to as a specific type of decal. Decals, are you likely know, are the little sticker-like images that you may find in the resource viewer of the FAF editor, and which you can freely position, scale, rotate and then place on your map to add aesthetic detail. Decals do not change the geometry of the heigthmap or interfere with units in any way; their effect is purely visual.

Until recently, the only way to add map-wide assets to your maps was as a decal. With the new shaders having been developed, another way to add these assets to your map has become possible. Nonetheless, in this tutorial I will regularly refer to these assets as 'decals', regardless of the way they are later applied to the map.

>Note that the terminology list does not include the specific names for less common terms, such as the names of elements of Gaea, as those are defined in their respective tutorials.

# The use and creation of map-wide assets
## General introduction to map-wide assets
Map wide assets are an extra method to improve the aestethics of a map. They have a lot in common with the default decals, in that they add extra details, colour, and fake terrain complexity. As the name implies, they differ from normal decals in that they affect the whole map with one file. Most commonly, three types of map-wide assets are used: those that add shadows, those that add colour (albedo), and those that add normals.

By and large, there are two main ways to apply these decals to your map. The first way is by applying them as you would any other decal. This involves rendering the asset as an image, encoding them as a .dds file, and loading them through the resource viewer onto your map. The second method involves loading the assets into one of the stratum layers, essentially using them as a texture. Both techniques, as well as their individual benefits and disadvantages, will be discussed in detail later in this tutorial.

Map-wide assets further differ from the default decals in that they are typically rather large. It is not recommended to render map-wide assets in less than 4k or 8k resolution, depending on your mapsize. This large resolution is necessary to achieve a high enough level of detail to ensure the decals are not pixelated when seen up close, such as when a player zooms all the way in. Naturally, as the decal has to be stretched further to cover larger maps, larger maps require higher resolutions. Consequently, for a 5km map a 4k map-wide decal might suffice, but a 8k resolution might barely be sufficient for a 20km map. 

***-> Image of low/high res zoomed in/zoomed out. Comparison side by side. Difference for 5k/20k map. Same map, rescaled.***

This advice is less relevant for map-wide shadow decals. As these decals are generally significantly less complex and do not need crisp edges as much as map-wide normals do, they may be rendered at resolutions as low as 0.5k. Lower resolutions benefit the eventual size of the map folder, which will quickly increase as larger resolution assets are added: it is not uncommon to see a mapfolder grow from 1-10MB to as much as 250MB after adding two high-resolution assets. It is important to keep this in mind, as this results in slow download speeds for players with slower internet connections.

Similar to the default decals, map-wide assets should be carefully used so as not to overwhelm the other elements of your map. The idea of texturing a whole map in one go using a map-wide albedo might sound seductive, but as previously explained in the [texturing tutorial](https://wiki.faforever.com/en/Development/Mapping/Gaea/Texturing#a-review-of-texturing-basics), this approach will not be able to approach the same level of resolution that can be achieved with the tiled textures. Furthermore, bold colours and overly busy patterns only add to visual noise, which makes maps unpleasant to play. As such, it is better to use map-wide albedo decals to accentuate existing textures, add colour variation and adjustments, and to break up the repeating pattern tiled-textures might make. 

***-> add images of several maps that use it properly. Some of sting's work, some Jip stuff***

Similarly, while map-wide normals are used to fake details in the geometry of the heightmap where there aren't any, care should be taken to ensure this does not confuse the player. Making mountain look rougher than they actually are is typically fine, but doing the same to flat terrain might give players the impression that units cannot cross and buildings cannot be build. As with all elements of map design, the effect of the design on the readability of the map needs to be kept in mind.

Used properly, these three types of decalls will add a lot visually to the map, and let you take your map from *good* to *great*.

## Map-wide shadows
The game engine renders shadows for structures, units, and props. Clearly visible shadows for the terrain are largely absent, however. Using map-wide shadow decals, 

Shadows are added to add to the already existing shadows that the game renders. However, the shadows rendered by the game are not very visible, and adding custom shadows adds a lot visually. The main node that is used to create the shadows is the light node. The light node simulates sunlight, lets you modify the sun's position in the sky, and renders shadows, ambient occlusion, and diffuse light. These layers can be used either together, or just the shadows layer on its own, to add higher quality light effects to your map.

## Map-wide normals
Map-wide normals are very similar to the small normals that you find shipped with the editor, and behaves similarly. They are added to fake terrain details were there are none, adding things like cracks, bumps, and erosion patterns to mountains and flat terrain alike.

## Map-wide albedo
Map-wide albedo's are based on the map texture created within gaea. For a detailed explanation on how to produce a textured map, see the tutorial.

# Applying map-wide assets to maps
## As decals
Encoding, placing, positioning, issues.

### Templates
As map-wide assets are directly derived from your (height)map, it is critical that they are precisely aligned with the terrain. As getting the scale and position of the decal exactly right is a bit of a hassle, templates with placeholders have been produced and published under a CC license by Jip. More
### Decal presets
Explanation of need, where to get them, how to use them.
## Using the new shaders
### General introduction new shaders
### Creating combined shader-accepted files in Gaea
#### Shadows and albedo
#### Normals

## Examples on existing maps

# Remaining questions

