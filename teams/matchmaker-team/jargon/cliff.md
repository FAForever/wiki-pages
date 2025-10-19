---
title: Cliff
description: 
published: true
date: 2025-10-19T19:53:35.835Z
tags: 
editor: markdown
dateCreated: 2025-10-19T19:53:35.835Z
---

# Cliff

A cliff is the most basic feature to influence how land units navigate. Units have a limit set to the maximum slope that they can traverse. This limit is defined by the value `MaxSlope` in the source file 

## Guidelines

## Interesting facts

The formula to compute the slope was found by Balthazar and is the following:

```lua
---@param x number   # in world coordinates
---@param z number   # in world coordinates
---@param maxSlope number
---@return boolean
local function canPathSlope(x, z, maxSlope) 
       local a, b, c, d = GetTerrainHeight(x - 1, z - 1), GetTerrainHeight(x - 1, z), GetTerrainHeight(x, z), GetTerrainHeight(x, z - 1) 
       return max(abs(a - b), abs(b - c), abs(c - d), abs(d - a)) <= maxSlope 
end
```

The slope is defined by a [Lua source file](https://github.com/FAForever/fa/blob/develop/lua/footprints.lua). The maximum slope can be different for units of different sizes. In practice however, the maximum slope is always set to 0.75 for a 1x1 block of terrain.

Terrain types also influence the navigation of units when the field `Blocking` is set to `true`. Terrain types are also defined by a [Lua source file](https://github.com/FAForever/fa/blob/develop/lua/TerrainTypes.lua). 

## Misconceptions

The official FAF editor used to give an incorrect estimation as to what parts of the terrain would be inaccessible due to steep terrain.  This was fixed however since 2023 with []().

