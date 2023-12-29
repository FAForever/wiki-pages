---
title: Creating Map-Wide Assets
description: A tutorial on the process of creating map-wide assets 
published: true
date: 2023-12-29T15:00:42.051Z
tags: gaea, decal, shadow, normal, albedo
editor: markdown
dateCreated: 2023-12-22T12:44:57.314Z
---

# Gaea tutorial: Creating map-wide assets in Gaea
This tutorial focuses on creating map-wide assets in Gaea. Here, I will discuss the creation of custom shadows, map-wide normals, and map-wide albedo decals. Additionally, this tutorial will explain the two main ways these assets can be applied to your map, and will include a discussion on the newly developed shaders.

>When specific nodes are referenced, they are highlighted like this: `Node`. Specific parameters for these nodes are written like this: `Slope, 30, 90, 0`, to specify a `Slope` node with Parameters 30 (min), 90 (Max), and 0 (Falloff).
{.is-info}

## Prerequisites
This tutorial assumes you've got a basic understanding of image editing and FAF mapping. An understanding of Gaea is also required: while I will discuss the relevant nodes and how they work, I will leave familiarizing yourself with the software for self study. Watch a few youtube tutorials on the basics, or read the general introduction to Gaea [here](https://docs.quadspinner.com/Guide/index.html). As the techniques described in this tutorial use elements discussed in the previous tutorials on masks and texturing, it is highly recommended to go through these tutorials first.

Required for this tutorial is a copy of Gaea (the indie version is free to use and more than sufficient for maps up to 20km), which can be downloaded [here](https://quadspinner.com/download). Additionally, an image editor such as Photoshop or Gimp is required, though the free to use online photoshop-clone [Photopea](https://www.photopea.com/) works fine too. Lastly, you will need the the FAF map editor.

Creating map-wide assets requires you to have prepared the basics of a map in advance. For the creation of a shadow and a normal-map decal, your heightmap should be finished. It is not necessary for your map to have been created within Gaea: you are able to export the heightmap from the FAF editor and import it into Gaea for further processing. For the creation of a map-wide albedo decal, you should already have most of your map texture design completed within the FAF editor. It is not required to have textured your map in Gaea, although to create a map-wide albedo decal you will need to do some texturing in Gaea. If you are unfamiliar with how to do this, you should refer to the previous parts of this tutorial series.

- [General introduction to Gaea*Official documentation*](https://docs.quadspinner.com/Guide/index.html)
- [Producing terrain masks in Gaea*Producing stratum masks for texturing*](/en/Development/Mapping/Gaea/Terrain-Masks)
- [Texturing in Gaea*Creating a texture design for your map within Gaea*](/en/Development/Mapping/Gaea/Texturing)
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

Similarly, while map-wide normals are used to fake details in the geometry of the heightmap where there aren't any, care should be taken to ensure this does not confuse the player. Making mountains look rougher than they actually are is typically fine, but doing the same to flat terrain might give players the impression that units cannot cross and buildings not be build. As with all elements of map design, the effect of the design on the readability of the map needs to be kept in mind.

Used properly however, these three types of decalls will add a lot visually to the map, and let you take your map from *good* to *great*.

## Map-wide shadows
While the game engine inherently renders shadows for structures, units, and props, visible shadows for the terrain are often lacking. The integration of map-wide shadow decals addresses this gap, enhancing both the visual aesthetics and realism of the terrain, while providing clearer visual cues about the map's topography.

Creating a shadow decal in Gaea is a straightforward process utilizing the `Light` node. This node acts as a sunlight simulator, allowing modification of the sun's position in the virtual sky and rendering shadows, ambient occlusion, and diffuse light. A basic shadow decal can be crafted using only the shadow output. For a more nuanced composition, including ambient occlusion and diffuse light outputs adds subtle ambient-occlusion-related shadows and highlights to the terrain.

***->image map without/with shadows/with complex shadows***

### Creating a basic shadow decal in Gaea
To create a shadow decal in Gaea, the first step is to prepare the heightmap we will be using as a source. 
- If you have created the terrain for your map entirely within Gaea, we're all set: all that is needed is to add a `Light` node to the end of your graph.
- If you have created most of the terrain within Gaea, but have since made modifications in the FAF editor or with other software, or have made the heightmap in another software entirely, we will have to import the heightmap into Gaea. This can be done with a `File` node, and using it to load the heightmap image. It may be that the vertical scale of the imported terrain is different from what you see in the FAF editor. In this case, you may need to rescale the height, which can be done using the 'Multiply' [modifier parameter](https://wiki.faforever.com/en/Development/Mapping/Gaea/Basic-Introduction#modifier-parameters). Once imported and properly scaled, a `Light` node needs to be added.

After preparing the heightmap and connecting the `Light` node, we must change the settings of the `Light` node. Important settings to adjust are the two sliders that control the position of the sun in the sky, as that determines the direction and length of your shadows. To ensure that the shadows that we will be adding align with the shadows that are already in the game, we have to match the `Light` node settings with the Light settings in the FAF editor. For the elevation slider, which controls the height of the sun in the sky, we may copy the value straight from the FAF editor. The values for the azimuth slider, however, cannot be copied straight from FAF editor, because the FAF editor puts the sun at a different position for the '0' value. Consequently, alligning the shadows can best done by eye. 

Once set-up correctly, connect an `Invert` node to the *Shadows* output of the light node. This creates an image that consists of a black background, with the shadows showing in white. This image, when added to the map in the editor as a decall, is what will create the shadows. It is important to `Invert` the *Shadows* output of the lightnode, rather than use it straight from the node where shadows are black on a white background, because the FAF editor interprets black as a transparant background, and non-black as something that should be visible.

***-> Image of nodes setup correctly***

Marking the `Invert` node for exporting—by selecting it and pressing <kbd>F3</kbd>, or by right-clicking on the node and selecting *'Mark for export'*—will put this node in the list of the *Build* tab. For map-wide shadow decals, exporting the file as *.png* at a resolution of 512px or 1024px works for most uses. All other export options may be left on their default settings. 

Once rendered, the image should be encoded to .DDS by any of the methods previously discussed, after which it is ready to be added to the map.

***-> Check if the above works as explained. Different from normal workflow, this follows EsAihSix's workflow. Verify, and credit.***

Alternative method involves rendering straight from node, making transparant, keeping shadows not white but black, and adjusting opacity. 

### Creating an advanced shadow decal in Gaea
Node use, light settings. Using all exports. Splitting ambient occlusion into white and dark in photoshop. Creating composite, finetuning opacity values. 

## Map-wide normals
A map-wide normal decal is very similar to the small normals that are by default included with the editor, and behaves similarly. Normal decals are added to a map to fake complex and detailed  looking terrain, without having to adjust the underlying heightmap. In this way, details like cracks, bumps, and erosion patterns can be added to mountains and flat terrain alike, without messing with unit pathing. 

Creating map-wide normal decals in Gaea involves the utilization of the `Normal` node, as well as a specific cluster of nodes to make the necessary adjustments to the output of the `Normal` node. 

### Creating a map-wide normal decal in Gaea
Node use, strength, Y-flip. Adding new details using erosion nodes etc as a source rather than the 'plain' heightmap. Node-cluster to create the FAF supported format (green/orange instead of blue/purple). Splat, RGBA-A output, how different channels combine into one layer and how to adjust individual channels. Adjusting transparancy (red channel). Difference between RGB/RGBA. Rendering, resolution, filetype. Encoding using imagemagick. 

***->image without/with normals***


Ensuring coherence with the in-game environment, it's essential to align the direction of the normals with existing in-game lighting sources. This alignment guarantees that the added surface details seamlessly integrate with the natural lighting conditions. While introducing normal decals, attention should be paid to potential discrepancies that might arise, such as normal conflicts with unit or building elements. 



## Map-wide albedo
Map-wide albedo's are based on the map texture created within gaea. For a detailed explanation on how to produce a textured map, see the tutorial.

### Creating a map-wide albedo decal in Gaea

# Applying map-wide assets to maps
## As decals
Encoding, placing, positioning, issues.

While incorporating the shadow decal, consideration should be given to potential double shadows, where the game renders unit and building shadows atop the terrain shadow. While the issue of double shadows is relatively minor, a new method has been introduced to address and mitigate this occurrence."

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

