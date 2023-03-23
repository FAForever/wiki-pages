---
title: Creating AI friendly maps
description: Tips for ways to make maps more AI friendly
published: true
date: 2023-03-23T22:18:03.700Z
tags: mapping
editor: markdown
dateCreated: 2023-03-23T22:14:43.991Z
---

# Introduction
The below points are intended to highlight examples of map design that are more likely to cause issues with AI.  It is not an exhaustive list, and whether the point is relevant will depend largely on the AI in question.
Just because a point is noted below as causing problems for AI, it doesn’t mean the issue should always be avoided.  In many of the points noted the issue is also due to a flaw/limitation in the approach commonly used by AI that could in theory be resolved by the AI.
Common AI approaches to games
While the approach an AI takes to the game is very heavily dependent on the AI being considered, the following is a relatively common approach:
- At the start of the game, identify the hostile player (i.e. human or AI) that is closest to the AI on a straight line distance, and prioritise attacks on this enemy.
- Various decisions will be made based on the distance of units to a particular point.  For example, deciding to attack when a unit is within a certain distance, or considering enemy threats within a certain distance of a start position.  Most of the time, such distance checks are based on a straight line distance, as opposed to considering how long it would take for a unit to travel there.  Depending on the map design this can often lead to unintended consequences for the AI (with its choice of how to respond to threats and where to send units) if a straight line distance check would result in a significantly different result to a land pathing result.

# Cliffs
The bane of AI, cliffs cause all manner of havoc on logic.  For example, units on attack-move getting stuck firing at an enemy unit (with their shots hitting the cliff), taking ages to setup pathfinding, messing up whether the AI thinks a unit is close or not, and in some cases causing the AI to get units stuck in a pattern of moving towards a location that due to cliffs is so much further away that the unit moves too far away, has its order cancelled and replaced with a new one, and repeats the cycle.
Suggestions for making maps that use cliffs more AI friendly include:
- Use cliffs sparingly
- Plateaus are generally preferable to ‘near-plateaus’ where units can still access the location through a small channel.
- Avoid narrow paths – especially on large maps, it takes too much of a CPU load to get down to 1x1 square accuracy on whether somewhere is pathable.  Try to use wide paths for somewhere that is pathable.
--If somewhere is narrow it can also result in it being pathable by small units like land scouts, but not larger units, which can lead to further problems.
- Avoid ‘bendy’ paths that loop around on themselves meaning units can end up close to each other, are able to path to each other, but have a cliff between them.
- If using ramps to allow access to a cliff/’semi-plateau’, make the ramp gradual – AI decisions on whether a location is pathable are typically based on how much the height changes between two points.  Slopes can therefore risk being mistaken as unpathable when pathable, and similarly unpathable areas mistaken as pathable.
- Similarly, if making somewhere unpathable, try to ensure at least 1 unit height change for the cliff, and in the case of cliffs adjacent to water, base this on the height of the water (e.g. astro crater uses a much smaller gap between the side of its cliffs and the water, which can lead to pathfinding issues).
- Very tall cliffs can result in certain attacks used by the AI (e.g. TMLs and cruiser missiles) failing to hit the target due to the terrain.
- Avoid cliffs or significant elevation changes near the start position as far as possible
-- AI are most likely to build point defence near their base to protect it from an attack.  Cliffs near the base greatly hinder this, since they can result in PD being built right by a cliff where most of its shots are blocked.  Similarly, elevation changes can lead to PD shots being blocked when firing at approaching units.
- Particularly for areas outside the main part of the map (e.g. around the border), try to use cliffs as small ‘breakers’ between normal pathable ground rather than lots of cliffs which feature small parts that are pathable.  As an example, despite being a very small map size (2.5kmx5km I think), winter dual can cause some AI to require a significant amount of time to calculate the pathing due to the various cliffs outside the part of the map that is played on.
- Allow space adjacent to mexes for mass storage to be built – if there is a cliff, it’s possible the AI could keep trying to build mass storage somewhere where it cant.
As an example, the following is part of Eye of the Storm:
