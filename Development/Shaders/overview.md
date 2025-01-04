---
title: Game shaders
description: 
published: true
date: 2025-01-04T10:12:58.710Z
tags: modding, textures, shaders, units
editor: markdown
dateCreated: 2023-10-03T09:05:20.882Z
---

# Game shaders

This article represents an overview of how the game shaders interpret the assets of, in particular, units. You can always find the latest shaders on [Github](https://github.com/FAForever/fa/tree/deploy/fafdevelop/effects). Specifically, the following shaders are discussed in this article:

- [terrain.fx](https://github.com/FAForever/fa/blob/deploy/fafdevelop/effects/terrain.fx) : contains all terrain and decal related shader techniques
- [mesh.fx](https://github.com/FAForever/fa/blob/deploy/fafdevelop/effects/mesh.fx) : contains all entity, unit, prop, projectile and shield related shader techniques

## Mesh.fx shader techniques

<todo></todo>

## Terrain.fx shader techniques

<todo></todo>
  
### Terrain shader techniques

#### Naming scheme
FAF provides additional terrain shaders. These alter how the game renders the map and provide opportunity to improve the visual fidelity of the map. 
The new shaders are organized by a naming scheme to make it easier to select the one you want and to add even more shaders in the future. All shaders are named 'Terrain' followed by a three-digit number. The numbers are used as follows

The first digit shows the main category
- Terrain0XX for shaders that don't use roughness maps or advanced splatting
- Terrain1XX for shaders using roughness maps
- Terrain2XX for shaders using advanced splatting
- Terrain3XX for shaders using roughness maps and advanced splatting

The second digit gives info about some technical properties of the shader with the range being divided into two halfes:
- TerrainX0X to TerrainX4X for shaders with half mask range
- TerrainX5X to TerrainX9X for shaders using the full mask range

Due to an oversight by the original developers, the stratum masks in the standard shaders only work in the 128 to 255 value range and have no effect in the lower half. Annoyingly this only affects the albedo textures, the according normal textures interpret the masks in the full 0 to 255 range.
This shader fixes this inconsistency by making both interpret the 128 to 255 value range (half range) or the 0 to 255 value range (full range) as 0 to 100%.
We provide both options because this bug has been around for so long that many tools and mapmakers assume half range to be used, so this makes upgrading to a different shader easier.

We can then use individual digits for different properties:
- TerrainX0X and TerrainX5X for shaders without any additional properties
- TerrainX1X and TerrainX6X for shaders using biplanar mapping
- TerrainX2X and TerrainX7X for shaders using additional rotated sampling
- TerrainX3X and TerrainX8X for shaders using biplanar mapping and additional rotated sampling

This leaves us with the third digit to have enough room to create multiple shader variations of the same category.

#### Available shaders

`TTerrain`
Used by original GPG maps. It only provides half of the texture slots.
It features a specular color that is always white. The inverted alpha value of the albedo textures acts as a multiplier on the amount of specular, so typically (full opacity textures) the specularity is 0.

Probably due to an oversight the masks for the stratums behave oddly. The normal texture behaves as expected and its opacity is direcly controlled by the mask opacity. But the albedo texture only uses half the mask range. It interprets values up to 128 as 0 and only then starts showing up. This can lead to annoying behaviour when trying to paint a layer.

`TTerrainXP`
Used by most community-made maps. It provides the full range of texture slots.
It features an RGB specular color. This time the regular alpha value of the albedo textures acts as a multiplier on the amount of specular. (Yes, this difference between TTerrain and TTerrainXP sounds nonsensical, but this is how the original devs made it and we can't change it now because it would alter the look of many maps.)

TTerrainXP suffers from the same mask issue as TTerrain.

The upper layer can be used for macrotextures to try to break up texture repetition. This layer interprets the alpha value of the texture as opacity. Textures that are intended for this usage typically have `macrotexture` in their name.

`Terrain001`
Terrain001 is designed as a drop-in replacement for TTerrainXP that solely introduces the terrain info texture for map-wide normals and shadows. That's why it also keeps the half mask range for albedo layers and full mask range for normal layers.
As the terrain info texture goes into the upper slot you lose the ability to have a macrotexture.

`Terrain002 and Terrain052`
These are very similar to Terrain001. The only difference is that they make the used value ranges in the layer masks consistent between normal and albedo. Terrain002 uses only the upper half of the mask values and Terrain052 uses the full range.

`Terrain003 and Terrain053`
These use [UDN blending](https://blog.selfshadow.com/publications/blending-in-detail/) to blend the normals of the different layers.
The macrotexture is now in layer 8 albedo. It doesn't react to scaling and will always perfectly fit the dimensions of the map.
The terrain info texture goes into the upper slot again.
The red channel of the normal slot of layer 8 controls the amount of specular reflection. The other channels of the normal slot are unused.
Terrain003 uses only the upper half of the mask values and Terrain053 uses the full range.

`Terrain101 and Terrain151`
These shaders use roughness textures.

The terrain info texture is in the upper slot.
The macrotexture is in layer 8 albedo. It doesn't react to scaling and will always perfectly fit the dimensions of the map.
The texture atlas for the roughness textures goes into the layer 8 normal slot.
The layer mask of layer 8 acts as a roughness multiplier with 0.5 as the neutral value. This way you can vary the roughness over your map, for example to give the impression of wetter and drier areas.
The normal map scales of all layers are controlled by the albedo scales to ensure that they use the same values.
Terrain101 uses only the upper half of the mask values and Terrain151 uses the full range.

`Terrain301 and Terrain351`
These shaders use roughness textures and height-based texture blending.

Every second texture layer is rotated by 30 degrees to help breaking up visible texture repetition.
The terrain info texture is in the upper slot.
The macrotexture is in layer 8 albedo. It doesn't react to scaling and will always perfectly fit the dimensions of the map.
The texture atlas for the roughness and height textures goes into the layer 8 normal slot.
The layer mask of layer 8 acts as a roughness multiplier with 0.5 as the neutral value.
Height processing happens at two scales, the albedo scales control the near scale and the normal scales control the far scale.
The normal map scales are controlled by the albedo scales to ensure that they use the same values.
The red channel of the specular color controls the blurriness of the texture blending.
Terrain301 uses only the upper half of the mask values and Terrain351 uses the full range.


    
### Decal shader techniques

The use of decal shader technique is less flexible. At the moment it is not possible to create new shader techniques for decals without changing the look and feel of existing maps. Commonly used shader techniques are:

- `TDecals` : albedo decal; it represents colors and uses the alpha channel for opacity
- `TDecalsXP` : albedo decal; it represents colors and uses the alpha channel for opacity
- `TDecalsNormals` : normals decal; it represents directions and uses the red channel for opacity

Various more uncommon shader techniques are:

- `TDecalGlowMask`: behavior is unknown
- `TDecalsGlow`: glow decal; it only uses the alpha channel to influence bloom
- `TDecalsWaterAlbedo`: albedo decal; identical to `TDecalsXP` except that it clamps to the water surface
- `TDecalsWaterMask`: behavior us unknown
- `TDecalsNormalsAlpha`: normals decal; appears to be identical to `TDecalsNormals`
- `TDecalOverDraw`: used for debugging to show decal overdraw 
