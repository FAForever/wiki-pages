---
title: Terrain Topology: Cliffs
description: Describes the general guidelines on the use of cliffs.
published: true
date: 2025-10-20T15:27:31.470Z
tags: 
editor: markdown
dateCreated: 2025-10-19T19:53:35.835Z
---

# Cliff

A cliff is the most basic feature to influence how land units navigate. When terrain that is above water is too steep it blocks the pathing of land, amphibious and hover units. The same applies for amphibious units for terrain that is below water. 

## Tabs {.tabset}
### Williamson's Bridge :green_circle:

![Image of a Megalith next to a cliff on the map Williamson's Bridge](/teams/matchmaker-team/cliff-williamson-bridge.png =700x)

Example of a cliff with reasonable slope on the map Williamson's Bridge.

### Project Tabula :red_circle:

<br>

<video style="border-radius: 10px" width="700" height="450" controls>
  <source src="/teams/matchmaker-team/bomber-behavior-01.mp4" type="video/mp4">
</video>

Example of poor behavior of air units when the height difference is too excessive on the map Project Tabula.


## Guidelines

Air units are sensitive to excessive height changes above land. If the rate of height change is significant enough it will change the behavior of air units. This is very difficult for the player to take into account, especially for the long attack runs of bombers. Therefore excessive height changes above land are a frustrating experience. 

A few simple guidelines:

- Small cliffs of the size of a tech 1 power generator (2x2) should not have more height difference than a Brick.
- Medium cliffs of the size of a tech 2 power generator (6x6) should not have more height difference than a Monkey Lord.
- Large cliffs of the size of a tech 3 power generator (8x8) should not have more height difference than a Megalith. 

In general any elevation difference between a lower ground and an upper ground should not be higher than a Megalith. All projectiles in this game are simulated. They rely on computing a firing trajectory. Especially for tech 1 artillery, when the difference in height is larger than a Megalith chances are that they're unable to find a firing trajectory and therefore refuse to fire even though the target is in range. The player usually does not anticipate this and therefore it is a frustrating experience.

## Misconceptions

The official FAF editor used to give an incorrect estimation as to what parts of the terrain would be inaccessible due to steep terrain.  This was fixed however since 2023 with []().

Bombers used to miss occasionally, but this is fixed in [] and []. 

## Trivia

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
