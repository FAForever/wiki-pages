---
title: Game shaders
description: 
published: true
date: 2025-04-08T21:40:35.717Z
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
Refer to the [terrain shader page](/Development/Shaders/terrain-shaders)

    
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
