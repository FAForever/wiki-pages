---
title: Game shaders
description: 
published: true
date: 2024-12-30T21:51:39.297Z
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

### Naming scheme
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

### Available shaders

#### TTerrain
Used by original GPG maps. It only provides half of the texture slots.

#### TTerrainXP
Used by most community-made maps. It provides the full range of texture slots.

#### Terrain001
Terrain001 is designed as a drop-in replacement for TTerrainXP that solely introduces map-wide normals and shadows. That's why it also keeps the half mask range for albedo layers and full mask range for normal layers.

#### Terrain002 and Terrain052
These are very similar to Terrain001. The only difference is that they change how the texture masks get read for the stratum normals.

#### Terrain003 and Terrain053
These additionally use the mapwide albedo texture and the red channel of the normal slot of layer 8 controls the amount of specular reflection. The other channels of the normal slot are unused.

#### Terrain101 and Terrain151
The normal map scales are controlled by the albedo scales to ensure that they use the same values.
The layer mask of layer 8 acts as a roughness multiplier with 0.5 as the neutral value.
They also use the mapwide albedo texture.

#### Terrain301 and Terrain351
The normal map scales are controlled by the albedo scales to ensure that they use the same values.
The layer mask of layer 8 acts as a roughness multiplier with 0.5 as the neutral value.
Height processing happens at two scales, the albedo scales control the near scale and the normal scales control the far scale.
They also use the mapwide albedo texture.


    
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
