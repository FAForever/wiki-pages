---
title: Feedback by Jip
description:
published: true
date: 2023-11-16T08:15:29.887Z
tags:
editor: markdown
dateCreated: 2023-11-16T07:46:10.819Z
---

# 'Brigadier Fletcher' Mapping tournament - Feedback by Jip

## Review process

Reviewing is subjective by nature. I tried to make it more objective by using a grading matrix. The full matrix and some of the reasoning of it can be found in the next sub sections.

### AI

What matters to me in this section is whether your map represents patterns that are almost unsolveable for an AI. A simple example is the inability for a transport to drop units on a plateau. The game does not provide the AI with the events and/or data to help the AI understand that it is unable to drop at that location. As a result it is almost unsolveable for an AI to determine accurately whether a drop will succeed. Maudlin, the author of M27 and M28, wrote an extensive article on other difficult map patterns in [this separate wiki topic](https://wiki.faforever.com/en/Development/Mapping/ai-friendly-maps).

| Description                                      | Point reduction | Reasoning                                                                                                                                                                                              |
| ------------------------------------------------ | --------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Navigational mesh**                            |                 |                                                                                                                                                                                                        |
| Unable to generate expansion markers             |                 | Without the expansion markers the AI does not understand where it can expand to. Usually this occurs because there are no clustered mass extractors or they are too far apart.                         |
| Unable to generate large expansion markers       |                 | Without the expansion markers the AI does not understand where it can expand to. Usually this occurs because there are no clustered mass extractors or they are too far apart                          |
| **Legacy support**                               |                 |                                                                                                                                                                                                        |
| No legacy pathing markers                        |                 | Legacy markers are still used by various AIs and usually take little time and/or effort to place.                                                                                                      |
| No legacy AI utility markers                     |                 | Legacy markers are still used by various AIs and usually take little time and/or effort to place.                                                                                                      |
| **Heightmap**                                    |                 |                                                                                                                                                                                                        |
| Map has narrow paths                             |                 | A path is considered narrow when a Fatboy is unable to fit through. The AI may not be able to understand that regular units can fit through somewhere but a large, usually experimental, unit can not. |
| Map has tall cliffs                              |                 | A cliff is considered tall when bombers miss as they drop a bomb while flying over it. It is almost impossible for the AI to understand this.                                                          |
| Map has extractors with no room for all storages |                 | An AI may have trouble distinguishing the build site being blocked by units, or because it is simply unbuildable.                                                                                      |
| Map has reclaim on unpathable terrain            |                 | An area is considered unpathable if it is blocked, usually either by terrain elevation or terrain type.                                                                                                |
| Map has extractors too close to the map border   |                 | The editor gives you a warning when this applies. Scripted build orders can not always apply to build locations at the very edge of a map.                                                             |
| Map has small plateau's                          |                 | A small plateau may easily become undroppable which is difficult for the AI to understand.                                                                                                             |
| **Spawn locations**                              |                 |                                                                                                                                                                                                        |
| Spawn locations have civilians nearby            |                 | In particular hostile civilians may trigger all sorts of conditions of an AI spawns too nearby.                                                                                                        |
| Spawn locations are too small for a large base   |                 | An AI may have trouble understanding that there's not enough space in a base location.                                                                                                                 |
| Spawn locations rely on cliff building           |                 | An AI usually is unable to decipher whether it can cliff build in a reliable manner.                                                                                                                   |

### Aesthetics

What matters in this section to me is not so much about what color palette you used but whether you used the tools available to you to create a coherent experience for the player. And specifically: do you help the player to understand the map?

| Description                                                 | Point reduction                                                                                                              |
| ----------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------- |
| **Decals**                                                  |                                                                                                                              |
| Decals do not accentuate terrain                            | Decals are a good tool to bring the attention of players to bumps of the heightmap that would otherwise be difficult to see. |
| Decals do not accentuate ramps                              | Decals are a good tool to bring the attention of players to ramps to make it easier to understand the map.                   |
| Decals do not accentuate props                              | Decals can be a good tool to accentuate prop placement, to make them feel more coherent.                                     |
| Fewer than 10 decals                                        | Lack of decals usually indicates a lack of detail.                                                                           |
| More than 2000 decals                                       | Excessive use of decals can cause performance issues on computers with weaker hardware.                                      |
| Decals do not have proper LODCutoffs                        | Excessive number of visible decals can cause performance issues on computers with weaker hardware.                           |
| **Props**                                                   |                                                                                                                              |
| Props appear to be random                                   | Coherent prop placement can help with the immersion of the player.                                                           |
| Less than 10 props                                          | Lack of props usually indicates a lack of effort.                                                                            |
| More than 10000 props                                       | Excessive number of props can cause performance issues.                                                                      |
| Excessive floating props                                    |                                                                                                                              |
| **Heightmap**                                               |                                                                                                                              |
| Terrain appears to be artificial                            |                                                                                                                              |
| Terrain that is unpathable is not recognizable              |                                                                                                                              |
| Terrain is excessively noisy                                | In particular spikey mountains are                                                                                           |
| **Stratum textures or masks**                               |                                                                                                                              |
| Used five or fewer stratum layers                           |                                                                                                                              |
| Two or more duplicated stratum textures                     |                                                                                                                              |
| Stratum texture repetition                                  |                                                                                                                              |
| Stratum texture stretching                                  |                                                                                                                              |
| Stratum mask visually look like noise                       |                                                                                                                              |
| Stratum masks do not blend properly                         |                                                                                                                              |
| Stratum texture too blurry                                  |                                                                                                                              |
| **Water**                                                   |                                                                                                                              |
| Water ramp bleeding                                         |                                                                                                                              |
| Lack of waves                                               |                                                                                                                              |
| **Lighting**                                                |                                                                                                                              |
| Incorrect use of map-wide shadow                            |                                                                                                                              |
| Incorrect use of map-wide normals                           |                                                                                                                              |
| Over-saturated colors                                       |                                                                                                                              |
| Excessive normals                                           |                                                                                                                              |
| Map is too bright                                           |                                                                                                                              |
| Map is too dark                                             |                                                                                                                              |
| **Terrain types**                                           |                                                                                                                              |
| No terrain types applied                                    |                                                                                                                              |
| Incorrect use of terrain types                              |                                                                                                                              |
| **Disksize**                                                |                                                                                                                              |
| Map is more than 200 megabytes in disk size when compressed |                                                                                                                              |
| **General impression**                                      |                                                                                                                              |
| Map feels incoherent                                        |                                                                                                                              |
| Map feels unfinished                                        |                                                                                                                              |

### Strategy

| Description                                                                  | Point reduction | Reasoning                                                                                                                                                                                                                                                                 |
| ---------------------------------------------------------------------------- | --------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Resources**                                                                |                 |                                                                                                                                                                                                                                                                           |
| No safe resources for each player (< 3)                                      |                 | The resources near your spawn location are considered safe. There is usually an ACU or several factories that makes the resources impossible to raid.                                                                                                                     |
| No raidable resources for each player (< 2)                                  |                 | The resources that are on the edge of your sphere of influence are usually considered raidable. These resources reward attacking players for creating raiding parties. And it rewards defending players for having intel and being able to intercept the raiding parties. |
| No contestable resources for each player (< 2)                               |                 | The resources that are as far away to you as to your opponent (usually in between of you) are considered contested. They usually only belong to one team and may often switch owners as the game progresses. These resources reward having army presence.                 |
| Too many contestable resources for each player ( > 4)                        |                 | Too many contestable resources can create a snowball effect.                                                                                                                                                                                                              |
| No clear expansions for each player                                          |                 | A clump of extractors can be immediately recognized as an expansion. It is a tool for the map author to guide the player and it helps the player to make quick decisions.                                                                                                 |
| No hydrocarbon plants for each player                                        |                 | A hydrocarbon plant adds diversity to the available build orders for a player.                                                                                                                                                                                            |
| **Reclaim**                                                                  |                 |                                                                                                                                                                                                                                                                           |
| Very little or no reclaim (< 500 mass per player)                            |                 | Reclaim rewards the players that have a better understanding of managing their economy.                                                                                                                                                                                   |
| Excessive reclaim (> 5000 per player)                                        |                 | Excessive reclaim can be interesting but usually it skews the game. Effectively it allows plaeyrs to skip the tech 1 and sometimes even the tech 2 phase.                                                                                                                 |
| **Gameplay**                                                                 |                 |                                                                                                                                                                                                                                                                           |
| Map has volatile plateau's                                                   |                 | A plateau is a bit of buildable land that you can't get to without a transportand/or cliffbuilding. It is considered volatile when the plateau has significant resources while being at the same distance to each team.                                                   |
| Map has volatile islands                                                     |                 | An island is a bit of buildable land that you can't get to without using amphibious units, transports and/or cliffbuilding. It is considered volatile when the island has significant resources while being at the same distance to each team.                            |
| Map has volatile reclaim                                                     |                 |                                                                                                                                                                                                                                                                           |
| Map has volatile resources                                                   |                 |                                                                                                                                                                                                                                                                           |
| **Water**                                                                    |                 |                                                                                                                                                                                                                                                                           |
| Map doesn't utilize water                                                    |                 |                                                                                                                                                                                                                                                                           |
| Map favors faction with early hover                                          |                 |                                                                                                                                                                                                                                                                           |
| **Heightmap**                                                                |                 |                                                                                                                                                                                                                                                                           |
| Map has spotty pathing                                                       |                 |                                                                                                                                                                                                                                                                           |
| Map has narrow land pathing (doesn't fit a Fatboy side to side)              |                 |                                                                                                                                                                                                                                                                           |
| Map has narrow naval pathing (doesn't fit a CZAR side to side)               |                 |                                                                                                                                                                                                                                                                           |
| Map has clear choke points                                                   |                 |                                                                                                                                                                                                                                                                           |
| Map has spotty build locations (a lot of difficult to see slopes)            |                 |                                                                                                                                                                                                                                                                           |
| Map has spotty build locations at a spawn (a lot of difficult to see slopes) |                 |                                                                                                                                                                                                                                                                           |
| Map has excessive cliffs that cause bombers to miss                          |                 |                                                                                                                                                                                                                                                                           |
| Map has hard to see hills that block projectiles                             |                 |                                                                                                                                                                                                                                                                           |
| Map has a lot of resources near the edge of the map                          |                 |                                                                                                                                                                                                                                                                           |

## Overview of points

| Author           | Map                        | AI (up to 6) | Theme (up to 8) | Aesthetics (up to 10) | Strategy (up to 16) | Total |
| ---------------- | -------------------------- | ------------ | --------------- | --------------------- | ------------------- | ----- |
| CaptainKlutz     | Adaptive Fangtooth Islands | 4.5          | 6.5             | 7.5                   | 13.5                | 32    |
| Sting            | King of Beta Ceti          | 5.5          | 6.5             | 11                    | 6                   | 29    |
| Prohibitorum     | Project Vortex             | 5.5          | 6.5             | 9.25                  | 11.75               | 33    |
| TheCrimsonKnight | Stulta Aqau Pugna          | 5.75         | 7.5             | 8.5                   | 15                  | 37    |

## Submissions

### Adaptive Fangtooth Islands

The submission is created by CaptainKlutz.

My overall opinion is positive. The map has a consistent theme and sufficient gameplay options. The map feels unique but doesn't push it so that it becomes unrecognizeable to the player. With a few touches I think you can create a diamond that hopefully people won't forget about.

#### AI (4.5/6.0 points)

Overall the AI should be able to adapt to the map. There are no glaring issues. There are two (contested) mass extractors that can not be fully ringed with storages. The legacy AI markers are missing but the majority of the existing AIs do not rely on these markers.

| Description                                      | Point reduction |
| ------------------------------------------------ | --------------- |
| **Legacy support**                               |                 |
| No legacy pathing markers                        | 0.5             |
| No legacy AI utility markers                     | 0.5             |
| **Heightmap**                                    |                 |
| Map has extractors with no room for all storages | 0.5             |

#### Theme (6.5/8.0 points)

The map feels like it belonged (past tense) to the UEF faction. The description mentions that many vessels are drawn to these lands and that only a few leave unscathed. The scene represents this through wreckages and decals that represent various lost settlements. There's also no signs of the UEF defending the planet. Interestingly enough - this is exactly what the UEF did. They abandoned entire planets and this map would fit right in. The only thing I'm missing is the occasional UEF and non-UEF wreck that shows some form of battle that occured with the few UEF units that happened to be on the planet trying to fight for their lives.

#### Aesthetics (7.5/10.0 points)

The map feels cohesive. You tried to do something out of the box and in my opinion it worked. The map uses the stratum textures to communicate to the player what it can expect. A great example of this is the dark-grey color that represents ramps and/or bumpy terrain. The use of decals and props is great. I'm especially fond of what you did with the 'cracks' and the rocks on top of it.

There's a few sharp edges around cliffs and/or mountains. I'd definitely look into fixing that.

| Description                      | Point reduction |
| -------------------------------- | --------------- |
| **Heightmap**                    |                 |
| Terrain appears to be artificial | 0.5             |
| Terrain is excessively noisy     | 0.5             |
| **Water**                        |                 |
| Water ramp bleeding              | 0.5             |
| **Terrain types**                |                 |
| No terrain types applied         | 1.0             |

#### Strategy (14/16 points)

It feels to me that this map has all the gameplay options available to you as a player. Each spawn has a specific role but they have multiple options in how to execute that role.

The map has several volatile islands. In my opinion an island is volatile when it requires a decent investment (like a transport with several engineers) to get there while the island is so small that usually only one team can claim the island. The team that happens to be first can take the entire island. I'm specifically referring to the center island. There's six extractors on it and they're relatively safe from frigates. The team that ends up being a few seconds earlier with their drop can create the factory first and quickly secure the entire island including the resources and the reclaim.

The islands in the corners are less volatile because the mountains split the island into two! If you can't drop on one side then you can try the other side.

| Description                | Point reduction |
| -------------------------- | --------------- |
| **Gameplay**               |                 |
| Map has volatile reclaim   | 1.5             |
| Map has volatile resources | 0.5             |

### Kings of Beta Ceti

The submission is created by Stlng.

Unique is just one of the many words one can use to describe this map. It certainly leaves a mark in memory. The map is atmospherically of exceptional quality.

#### AI (5.5 / 6 points)

Overall the AI should be able to adapt to the map.

| Description             | Point reduction |
| ----------------------- | --------------- |
| **Heightmap**           |                 |
| Map has small plateau's | 0.5             |

#### Theme (7.5/8.0 points)

Thematically the map is strong. According to the description the site/map is quickly flooding because of a (significant) tide and as a result of the rush equipment is left behind. Assuming that the valley was not underwater before the tide I'd expect wrecks of civilian structures and/or land units on the ocean floor. But instead the ocean floor is scattered with the one unit type that could easily survive the rapid flooding: it is scattered with air units!

Initially I thought it may have been air units that were caught in a battle between two factions. But it appears all the units are of the UEF faction. Which leaves me wondering - what happened to these air units that they were all lost?

#### Aesthetics (11 / 10 points)

Aesthetically the map is of exceptional quality. I can encourage every map author to look up how this map is made. An additional bonus point for the custom map preview.

#### Strategy (6 / 16 points)

Every extractor can be raided using a frigate or a submarine with a deck gun. Balance-wise frigates are fast and have a lot of health for their damage output. In the early game it allows you to raid several extractors even when your frigate is taking fire from one or more frigates. In my opinion it is a dominant strategy - there's almost no alternative. And if you're unable to raid extractors then you can definitely prevent engineers from scooping up reclaim. An additional reduction of four points.

There's also a subtle 'bug' where submarines think it can hit any structure build on the columns with torpedo's because they are _just slightly_ in the water. This can be confusing during fights as the target priorities of the submarine may prefer a high tech (defense) structure over a low tech naval unit even though the torpedo's will always collide with the columns.

To me these issues are inherent to the unique, atmospherical design of the map.

| Description                                           | Point reduction | Reasoning |
| ----------------------------------------------------- | --------------- | --------- |
| **Resources**                                         |                 |           |
| No safe resources for each player (< 3)               | 1.0             |           |
| Too many contestable resources for each player ( > 4) | 1.0             |           |
| **Gameplay**                                          |                 |           |
| Map has volatile reclaim                              | 2.0             |           |
| **Heightmap**                                         |                 |           |
| Map has excessive cliffs that cause bombers to miss   | 0.5             |           |
| Map has a lot of resources near the edge of the map   | 0.5             |           |

### Project Vortex

The submission is created by Prohibitorum.

Overall a great design and an interesting jump with the spawn that starts in the water. I can highly recommend this map to players that are looking for an all-out naval engagements.

#### AI (5.5 / 6 points)

The AI may have a lot of trouble adapting to the spawn that starts in the water. There are various small plateau's (that look like islands) that I'm guaranteed of that the AI will have trouble with because a transport won't be able to drop units as easily when the plateau has structures on it.

| Description             | Point reduction |
| ----------------------- | --------------- |
| **Heightmap**           |                 |
| Map has small plateau's | 0.5             |

#### Theme (6.5 / 8.0 points)

A great and coherent theme. The map is trying to tell you a story about an accident that has gone tragically wrong. The wrecks and dead trees portray this horrific event. There's also no grass to be seen. A small deduction for what feels like an inconsistency. The civilian bases appear to have survived the blast. Initially I thought this was because of the mountains providing a natural barrier. But looking at it again, not only do the mountains provide no protection neither do the walls because the entrance is in the direction of the blast. It would've been more immersive if the entrance was on the other side and the walls that are pointing towards the explosion were damaged and on fire. Or just flat out destroyed, like the bit of a settlement in the top-right or bottom-left corners.

#### Aesthetics (9.25 / 10.0 points)

Overall the map is coherent. The use of procedural software is clearly visible but it isn't distracting. In fact - it appears to be of very high quality. I'd love to see how you generated the stratum masks. I also noticed the custom water ramp. An additional bonus point for these efforts.

The corner areas that are underwater appear to be intentionally unpathable for naval units. I can highly recommend you to use one of your remaining stratum masks to communicate where naval units can and can not go to.

| Description                                    | Point reduction |
| ---------------------------------------------- | --------------- |
| **Heightmap**                                  |                 |
| Terrain that is unpathable is not recognizable | 0.5             |
| **Lighting**                                   |                 |
| Incorrect use of map-wide shadow               | 1.0             |
| Map is too dark                                | 0.25            |

#### Strategy (11.75 / 16.0 points)

Personally I think the map delivers on its promises. It almost guarantees large naval battles. I'm not a huge fan of the uniform distribution of the extractors, but considering the theme of the map I do understand it. There's a few gotcha's that makes the map difficult to play. One is the long slope near the spawn location of the player closest to the civilian base. The entire slope is essentially unbuildable, but it's not obvious that the slope exists. Another problem is that certain area's are underwater but not pathable to naval units. I've also mentioned this in the aesthetics section. And last but not least, some extractors are so close to the border of the map that bombs are almost guaranteed to go off map when they try to bomb the given extractor.

| Description                                                                  | Point reduction |
| ---------------------------------------------------------------------------- | --------------- |
| **Heightmap**                                                                |                 |
| Map has spotty build locations (a lot of difficult to see slopes)            | 2.0             |
| Map has spotty build locations at a spawn (a lot of difficult to see slopes) | 0.5             |
| Map has a lot of resources near the edge of the map                          | 1.5             |

### Stulta Aqua Pugna

The submission is created by TheCrimsonKnight.

In my opinion this is the best submission of the tournament. Especially when you compare it to your submission to the Princess Burke mapping tournament - you've improved a lot and it shows! The aesthetics of the map clearly communicate to the player what it can expect. Especially flat and non-flat areas are well communicated. The map is relatively easy to understand for the player and it's unique enough to make it feel like a fresh, almost new experience to the average player.

#### AI (5.75 / 6 points)

All is good. Of all the submissions this map is likely the easiest for an AI to understand. The one and only problem is a narrow naval path that does allow for tech 1 and tech 2 naval units to pass, but tech 3 units need to go around. It may be worth the time to fix that.

| Description          | Point reduction |
| -------------------- | --------------- |
| **Heightmap**        |                 |
| Map has narrow paths | 0.25            |

#### Theme (7.5 / 8.0 points)

Simple and rock solid. It is clearly a planet that belongs to the UEF faction. The only thing that is lacking is a description with some lore in it.

#### Aesthetics (8.5 / 10 points)

The map looks great. It is a coherent design. Inititally it appeared that the angle of the sun played a vital role on how the map is perceived. But actually there's two stratum masks that you use to make an area appear darker or brighter and that _happens_ to be aligned with the sun. Without it, the map would almost feel bland. This is quite innovative and you get a bonus point for that.

| Description                          | Point reduction |
| ------------------------------------ | --------------- |
| **Decals**                           |                 |
| Decals do not have proper LODCutoffs | 1.0             |
| **Water**                            |                 |
| Water ramp bleeding                  | 0.25            |

| Lack of waves | 1.0 |

#### Strategy (15.0 / 16.0 points)

The only problem I have strategically is what I already described in the AI section: there's one naval path that allows for tech 1 and tech 2 naval units but tech 3 naval units have to go around. A naval path way should always be roughly the size of a CZAR or the behavior of the player may have their units behave unexpectedly. Beyond that the map clearly communicates to the player what it can expect and where it can expand to.

| Description                                                    | Point reduction |
| -------------------------------------------------------------- | --------------- |
| **Heightmap**                                                  |                 |
| Map has narrow naval pathing (doesn't fit a CZAR side to side) | 1.0             |
