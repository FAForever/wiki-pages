---
title: Creating AI friendly maps
description: Tips for ways to make maps more AI friendly
published: true
date: 2023-03-23T22:29:11.908Z
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
![eye_of_the_storm.png](/eye_of_the_storm.png)

It’s possible that a unit travelling from the top-left start position to the bottom-right (e.g. a monkeylord) is trying to move from point 1 to point 4.  As it gets near to point 2, it sees nearby enemies on the cliff that it can path to, so thinks it will try and attack them.  This causes it to go towards 3, at which point the unit on the cliff is too far away so it decides to ignore it and go back to the enemy base (e.g. towards point 4).  This takes it back underwater, going towards point 2, (with this then repeating).
This example also features several other issues – a narrow path between the mexes (with cliffs on either side), a cliff that juts out of the water in an awkward shape making it more likely for ships around points 1 and 2 to try and attack ships in the point 4 naval area and getting blocked by the cliff, and a small patch of ground around 3 that might confuse the AI if amphibious tanks were to travel on it.

# Civilians
- Don’t place too close to the AI, as it could cause the AI to activate emergency defence type logic in response to the threat.
- Don’t use mobile hostile civilian units where possible, as humans are likely to learn where such units are located, whereas the AI won’t (and typically AIs that provide ‘memory’ of civilian units only do this for civilian structures)
- Wrecks are generally a better choice for providing reclaim than destructible buildings that have a reclaim value, since the AI is more likely to reclaim wrecks than civilian buildings.
- If a hostile civilian is having a firebase, it should have radar (and power for it) with enough range to cover the range of the PD to avoid an unfair advantage for human players (who may know the distance from the firebase that is safe to move to, vs an AI which may assume that the PD can attack at its full range).
- Don’t use indestructible hostile civilian buildings, as this can lead to the AI units all stuck attacking the hostile unit (whereas a human knows to ignore it

# Reclaim
- Avoid placing reclaim by or on unpathable areas such as cliffs – AI may ignore it completely if it thinks it can’t path there.
- If there is a large amount of reclaim to be placed on a particular part of the map, try and have mexes there as well – AI are more likely to prioritise mexes than reclaim areas, and so may not even try to contest a large reclaim field.
- Similarly, try to place such high value reclaim locations (where it’s intended for the meta to be for players to move their ACUs to fight for it) in locations that units taking a straight line to the nearest enemy base are likely to move through/near.

# 3+4 way games and start positions
- Provide lots of flat area around a start position to be built on – AI struggle with space particularly late game and if they run out of space it can lead to them breaking down/doing little and overflowing mass.  It is also likely to find it much harder than a human to find somewhere to  build large footprint units such as a Czar.  For example, Regor Highlands features an ‘air slot’ that gives a small narrow area to be built in, which will be very hard for the AI to make effective use of:
![regor_highlands.png](/regor_highlands.png)

- Far fewer AI are able to make use of an ‘air slot’ position where it is impossible for land units to reach the enemy.
- Naval start points are unlikely to be used properly by AI – some AI may fail completely, others may search for the nearest land mass to the start position and try and setup their base there.
- Avoid start positions where it’s intended for the player to move their ACU a significant distance before they actually start the game. 
- Try to allow for multiple configurations/team settings – e.g. 3 way and 4-way games (most maps are intended for 2 teams only, making finding maps for AI based tournaments such as the rainbow cup very difficult).

# Water, cliff-building, etc.
- Try to avoid concave type shorelines near start positions where a naval factory is likely to be located, and use very shallow water (that cant be used by ships) as little as possible.
-- For example, there is an issue where an AI can validly build a naval factory, yet units that get built from that factory (particularly T3 units) can end up moving onto land and dying.
-- The below is an example of a map with a concave shape near the start point which can cause this issue:

![concave_naval_spawn.png](/concave_naval_spawn.png)

- Try to have beaches for bodies of water near the start position instead of cliffs – i.e. AIs struggle with cliff building (most won’t even attempt it), which can put them at a significant disadvantage to humans, and also lead engineers taking a very long path to try and build somewhere that could be cliff built.  Setons is an example that can cause this problem with the ‘rock’ start position:

![setons_naval_location.png](/setons_naval_location.png)

-- e.g. an AI might decide to try and build on the location just to the right of the ACU start position, and then send its engineers all the around the beach location to the top-left to get there.

- Another example of a map/water setup that is more likely to lead to the AI building a naval factory in a poor location:
