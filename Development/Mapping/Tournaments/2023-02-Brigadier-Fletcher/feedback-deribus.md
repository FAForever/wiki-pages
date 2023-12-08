---
title: Feedback by Deribus
description:
published: true
date: 2023-12-08T09:45:10.655Z
tags: 
editor: markdown
dateCreated: 2023-11-16T07:46:09.671Z
---

# 'Brigadier Fletcher' Mapping tournament - Feedback by Deribus

## Review Process

### Step 1: First Impressions and Visuals

I load the map in sandbox with no fog of war and cheats enabled. I look around the map to get an impression of the visuals and any issues I may feel like need to be tested in the next step.

### Step 2: Sandbox Testing

I test the issues that I foresee might be relevant in Step 1. Unfortunately I can't test every map for every potential issue as that'd take way too much time.

### Step 3: Game vs AI

I played a 4v4 with all slots filled with AI: Adaptive. I know little about how AI work but I thought it'd show map AI issues more prominently than something like M27 which is too smart for its own good. Setting were all default except Odd vs Even auto teams and Full Share.

### Step 4: Scoring

Basically just taking all of the above and providing a final score. This will all be done together at the end.

## Overview of points

| Author           | Map                        | AI (up to 6) | Theme (up to 8) | Aesthetics (up to 10) | Strategy (up to 16) | Total   |
| ---------------- | -------------------------- | ------------ | --------------- | --------------------- | ------------------- | ------- |
| CaptainKlutz     | Adaptive Fangtooth Islands | 6.0          | 3.0             | 5.0                   | 13.0                | 27      |
| Sting            | King of Beta Ceti          | 3.0          | 6.0             | 5.0                   | 6.0                 | 20      |
| Prohibitorum     | Project Vortex             | 2.0          | 7.0             | 10.0                  | 4.0                 | 22.9999 |
| TheCrimsonKnight | Stulta Aqau Pugna          | 5.0          | 7.0             | 8.0                   | 15.0                | 35      |

# Adaptive Fangtooth Islands

Props for making it adaptive, but I only have so much time and tested this with all default settings.

## First Impressions and Visuals

- Could use a bit more of a beach/shoreline texture. Water-land interface is quite sudden.
- For a planet that belongs to the UEF there sure are a lot of destroyed buildings and no surviving buildings. Looks a lot more like a planet that _used to_ belong to the UEF.
- Zero underwater decals. Doesn't have to be a lot but a few here and there would be nice, especially where the mexes are
- The medium-dark gray stratum layer is incredibly pixelated, and some cliffs are jagged
- Really pretty work on the asphalt decals though

## Sandbox Testing

#### Dock

Ok you see this dock? It's a lie.
![fangtooth-dock.jpg](/mapping_tournaments/deribus-brigadier-fletcher/fangtooth-dock.jpg)
This is what it looks like in cartographic view.
![fangtooth-dock-carto.jpg](/mapping_tournaments/deribus-brigadier-fletcher/fangtooth-dock-carto.jpg)
And indeed if you try to path a land non-hover unit to the edge of the dock it can't reach it. Here's a side view with the reclaim gone.
![fangtooth-dock-side.jpg](/mapping_tournaments/deribus-brigadier-fletcher/fangtooth-dock-side.jpg)
Minor issue but I noticed it so I pointed it out.

Aaaand that's it. For better or worse the layout of this map is quite standard so there weren't any testing issues. All the waterways are pathable and there are massive flat areas on all islands every attempted drop landed perfectly.

## Game vs AI

This map was a lot of fun! It feels like a less volatile Point of Reach. The islands are easier to reach if your transport goes wrong and they're closer so your transport is less likely to be intercepted. Plus the island in the middle gives a lot of options.

Similar to Vortex, the large amount of distributed underwater mexes allows T1 subs to shine which is a rare occurrence on most maps. I know this review was short but that's because I have few criticisms on the gameplay; was great!

# Kings of Beta Ceti

## First Impressions and Visuals

So my VERY first impression before even opening the map was this.
![ceti_size.jpg](/mapping_tournaments/deribus-brigadier-fletcher/ceti_size.jpg)
That's not a good or bad thing so it won't affect my grading, but it did make me go
![what.gif](/mapping_tournaments/deribus-brigadier-fletcher/what.gif)
For reference that is 5x the other 3 maps _combined_.

- I HATE the flooded squares look. This is personal preference but honestly it just makes the spawn look broken and confuses players whether they're even allowed to build there until they check. Yes I'm biased but this is my review and you can't stop me
- Cruisers in the naval factory is cool as fuck tho
- Clouds look nice too, good work on that
- Cartographic map preview with labels? That's actually pretty clever and I've never seen it before
  ![beta_ceti_preview.jpg](/mapping_tournaments/deribus-brigadier-fletcher/beta_ceti_preview.jpg)

## Sandbox Testing

### Naval Pathing

For naval pathing I spawned a Cybran frigate and saw where it could and couldn't path through. The red Xs are waterways it couldn't get through.

On the entire map I only found these two, which is pretty good.
![beta_ceti_naval_pathing.jpg](/mapping_tournaments/deribus-brigadier-fletcher/beta_ceti_naval_pathing.jpg)

### Drops

To check which plateaus were too small to drop, I filled a bunch of UEF T3 transports with T1 engineers and made 3 attempts to drop each one where there was either a mex or decent mass to reclaim. A green check mark means all three attempts succeeded, a yellow circle means at least one succeeded, and a red x means none of them succeeded.

There were no complete fails and most squares were droppable without issue, so pretty good overall.
![beta_ceti_drops.jpg](/mapping_tournaments/deribus-brigadier-fletcher/beta_ceti_drops.jpg)

### Invincible ACU

Ok so unfortunately this one is a doozy. If you attempt to walk off a square your ACU will usually be unable to, but if you attempt to do it near a corner your ACU will phase into the terrain and be very very difficult to kill.
[invulnerableacu.mp4](/mapping_tournaments/deribus-brigadier-fletcher/invulnerableacu.mp4)

It's not _completely_ invulnerable, as anything with enough AoE like strats or zthuees can still kill it, but it's immune to most direct fire weapons and cannot be targeted with torpedoes. Still problematic

## Game vs AI

The basic layout of this map was actually quite a bit of fun, but unfortunately the "flooded" aspect of the squares did lead to issues, as I feared.

The most obvious are the targeting issues. Direct fire units will sometimes refuse to attack something on a flooded square, and then if you move the mouse away and mouse over again they'll change their mind. Sometimes it's scouting that makes them realize these units are indeed not underwater. Another issue was my ACU continually missing a stationary tank that dropped next to, only for the whole drop to explode as if it landed on invalid terrain a few seconds later. The game really doesn't know what's going on.

You also seem to be forced to rush T2 air for the transports. An ACU dropped on basically any island secures it, as there won't be any land to contest and early navy isn't numerous enough to punish an ACU.

_However_ if all that were fixed I do see the beginnings of a fun map. There are clumps of mexes to draw fighting, a few different ways for navy to attack, and very difficult to defend bases which should lead to aggressive gameplay.

# Project Vortex

I reviewed v9 which is the version submitted by the deadline, some of these issues might be fixed in later versions

-0.0001 points for making me test offline because launching through the client would auto-update the map to v12

## First Impressions and Visuals

- Pretty as fuck map damn sonny
- Reclaim in the middle of the map is completely invisible without ctrl-shift. I think the depth in the middle can be turned down a bit
- Turned naval fac wrecks look... weird
  ![project_vortex_factory.jpg](/mapping_tournaments/deribus-brigadier-fletcher/project_vortex_factory.jpg)
- Spawns 5 through 8 are can't build a land/air factory without walking? Who hurt you?
- I do hate the slightly flooded land that water can't actually path through. It's confusing and looks broken

## Sandbox Testing

#### Naval Pathing

For naval pathing I spawned a Cybran frigate and saw where it could and couldn't path through. The red Xs are waterways it couldn't get through. Especially concerning were the yellow shaded areas though, which were bodies of water where you could build a naval factory but out of which it was impossible to navigate.

![project_vortex_naval_pathing.jpg](/mapping_tournaments/deribus-brigadier-fletcher/project_vortex_naval_pathing.jpg)

#### Drops

To check which plateaus were too small to drop, I filled a bunch of UEF T3 transports with T1 engineers and made 3 attempts to drop each one where there was either a mex or decent mass to reclaim. A green check mark means all three attempts succeeded, a yellow circle means at least one succeeded, and a red x means none of them succeeded.
![project_vortex_drops.jpg](/mapping_tournaments/deribus-brigadier-fletcher/project_vortex_drops.jpg)

Picture speaks for itself I think, most of the islands were functionally un-droppable.

#### Invulnerable ACU

See the same section under Beta Ceti for a description of what I was checking for, but there were no issues found so it doesn't really matter in this case.

## Game vs AI

This map is incredibly difficult to play on, especially for hypothetical lower skilled players (not me obviously). There no mex clumps outside of spawn, so you can't focus your attention and resources anywhere specific, the entire map is equally important. Expanding is also hard because you have to drop mexes almost individually, which can be a problem because of the aforementioned drop problems. In a PvP game instead of vs AI this might not be not as taxing to play on because the other player will have similar focusing issues, but I don't expect it to make too much a difference. You end up throwing all your units face first into the enemy spawn because there aren't any clumps of resources to warrant raiding.

Hover is also a massive advantage because you can send cheap hover units to mess with islands one after the other without worrying about potential pathfinding issues from navy. Although it was nice to see an actual purpose to T1 subs, because of all the spread out underwater mexes they can raid and be difficult to find.

# Stulta Aqua Pugna

## First Impressions and Visuals

- Whoaaaa, you spawn WITH power and a T2 radar?
  ![aqua_pugna_radar.jpg](/mapping_tournaments/deribus-brigadier-fletcher/aqua_pugna_radar.jpg)
- There are elements to that I like and that I don't like. I love the idea of players spawning immediately with power generation, as it requires developing some new and creative build orders. _Buuuuut_ in order to get any benefit you have to turn off the radar because it is useless in the very beginning of the game. Since that radar is on the opposite side of the map from your spawn, you have to zooom all the way out, select the radar, pause it, zoom back in, and then do your build order, This would be 10x better if it just spawned pre-disabled.
- Loooove the UEF bases. The smoke from the manufacturing buildings and the little bit of motion from the pgens really makes it feel alive. Plus the placing of air on the airstrip decals? \*\*Chef's kiss\*\*
- Great work on the textures and decals too. If I had to find one fault it's the overreliance on the same decal at every mex spawn but that's a fairly minor nitpick.

## Sandbox Testing

### Factory Placement

Ya see dis?
![aqua_pugna_factory.jpg](/mapping_tournaments/deribus-brigadier-fletcher/aqua_pugna_factory.jpg)
This fac placement both doesn't get adjacency from second mex and blocks storage later on.
![unacceptable.gif](/mapping_tournaments/deribus-brigadier-fletcher/unacceptable.gif)
Cardinal sin of mapmaking

### Naval Pathing

For naval pathing I spawned a Cybran frigate and saw where it could and couldn't path through. The red Xs are waterways it couldn't get through.

![aqua_pugna_naval_pathing.jpg](/mapping_tournaments/deribus-brigadier-fletcher/aqua_pugna_naval_pathing.jpg)

There were only 3 places that looked pathable by navy but weren't, and none of them were really an issue. You did have one yellow shaded area though, which is a place where a naval factory can be built but navy can't get out of. Easily fixable by completing that land bridge to form a lake though. I also circled two lakes, in which _technically_ you can also build a locked naval fac but it's quite obvious there's no path out so I'm completely fine with that, just mentioning it to not make it seem like there's a double standard.

### Drops

To check which plateaus were too small to drop, I filled a bunch of UEF T3 transports with T1 engineers and made 3 attempts to drop each one where there was either a mex or decent mass to reclaim. A green check mark means all three attempts succeeded, a yellow circle means at least one succeeded, and a red x means none of them succeeded.

![aqua_pugna_drops.jpg](/mapping_tournaments/deribus-brigadier-fletcher/aqua_pugna_drops.jpg)

This testing went exactly as expected, with only these two islands being un-droppable.

## Game vs AI

I... struggle to put into words just how much I enjoyed playing this map. The spawns mean there is a 3v1 on each side, but that one player gets a massive starting bonus via the aforementioned pgens. Their teammates are also not too far away to help out, and indeed their best naval factory positions encourage helping their last player. Plus there's tons of opportunities for drops, proxy bases, naval raiding... ugh it's so good. Could use a few underwater mexes though for the early T1 sub gameplay I praised other other maps for. And maybe one or two big masses on the islands next to the solo player, get some early fightin' over there.

# Scoring (or Grading as Jeep calls it)

## AI

I know nothing about AI and have enough useless FAF knowledge already. My AI games revealed no problems on any of the maps. However I did do a bunch of drop and naval pathfinding testing so I'll use that for my grading.

### Adaptive Fangtooth Islands: 6/6

Only map that passed the drop and navigational testing with 0 issue. There is the one weird dock on each side but I don't see that affecting gameplay.

### Kings of Beta Ceti: 3/6

It did reasonably well on the testing, but the targeting issues were quite apparent and unit AI suffered.

### Project Vortex: 2/6

Did by far the worst in my pathfinding and drop tests. I haven't counted but I think there are probably 2 undroppable islands for every one that drops without issue.

### Stulta Aqua Pugna: 5/6

_Almost_ passed drop and pathfinding tests but there were a few minor hiccups.

## Theme

### Adaptive Fangtooth Islands: 3/8

It's UEF all right, but all the UEF stuff is broken. This feels like a _used to be UEF_ planet rather than a _currently_ UEF planet. Note what Jip said about Earth in the Theme section of the grading outline.

### Kings of Beta Ceti: 6/8

For sure feels like an active UEF base, but is short on UEF-specific decals. I like the additional theming in the preview though!

### Project Vortex: 7/8

Has a lot of wrecks, but the UEF presence still exists in a lot of intact buildings, units, and even full bases. Bonus point for coming up with a story for what happened on this planet, featuring the UEF's favorite toy Black Sun.

### Stulta Aqua Pugna: 7/8

This really feels like a living, breathing, UEF planet. Short of a massive city like is on Loki I don't think you could do better, and I'm not sure that would be beneficial for gameplay

## Aesthetics

### Adaptive Fangtooth Islands: 5/10

It feels a little... dead. The islands outside of spawn are pretty barren, and there aren't any decals underwater. The lack of any texture transition between land and water is jarring too. Could use a lil sprucing up.

### Kings of Beta Ceti: 5/10

This is very difficult for me to grade so I'll split it down the middle. I discussed how I hate hate hate the flooded squares look, but with that aside there was clearly a lot of work spent beautifing the map. It's the only one with cloud effects (not saying every map should have them, but the effort is noteworthy), and quite some time was spent unifying everything together. If only the terrain were a lil more... fun.

### Project Vortex: 10/10

This map seems to have put aesthetics first, and it shows. It looks fantastic and ties in beautifully to the story behind it. Decals galore, beautiful bases, and even zoomed out this map looks poster worthy.

### Stulta Aqua Pugna: 8/10

Also an incredibly beautiful map. Unfortunately not quite as drop-dead gorgeous as Project Vortex is, but there are decals and textures and buildings all over the place yet still tied together. The only negative thing I noted was the reuse of the same decal for every mex.

## Strategy

This section is primarily "how much fun did I have playing it" and "how likely do I see this map being hosted post-tournament?". I don't have anything additional to write so I'll just copy the **Game vs AI** writeup I did for each.

### Adaptive Fangtooth Islands: 13/16

This map was a lot of fun! It feels like a less volatile Point of Reach. The islands are easier to reach if your transport goes wrong and they're closer so your transport is less likely to be intercepted. Plus the island in the middle gives a lot of options.

Similar to Vortex, the large amount of distributed underwater mexes allows T1 subs to shine which is a rare occurrence on most maps. I know this review was short but that's because I have few criticisms on the gameplay; was great!

### Kings of Beta Ceti: 6/16

The basic layout of this map was actually quite a bit of fun, but unfortunately the "flooded" aspect of the squares did lead to issues, as I feared.

The most obvious are the targeting issues. Direct fire units will sometimes refuse to attack something on a flooded square, and then if you move the mouse away and mouse over again they'll change their mind. Sometimes it's scouting that makes them realize these units are indeed not underwater. Another issue was my ACU continually missing a stationary tank that dropped next to, only for the whole drop to explode as if it landed on invalid terrain a few seconds later. The game really doesn't know what's going on.

You also seem to be forced to rush T2 air for the transports. An ACU dropped on basically any island secures it, as there won't be any land to contest and early navy isn't numerous enough to punish an ACU.

_However_ if all that were fixed I do see the beginnings of a fun map. There are clumps of mexes to draw fighting, a few different ways for navy to attack, and very difficult to defend bases which should lead to aggressive gameplay. **I score this higher than Project Vortex because its issues are fixable, whereas Project Vortex' seem inherent to the map design.**

### Project Vortex: 4/16

This map is incredibly difficult to play on, especially for hypothetical lower skilled players (not me obviously). There no mex clumps outside of spawn, so you can't focus your attention and resources anywhere specific, the entire map is equally important. Expanding is also hard because you have to drop mexes almost individually, which can be a problem because of the aforementioned drop problems. In a PvP game instead of vs AI this might not be not as taxing to play on because the other player will have similar focusing issues, but I don't expect it to make too much a difference. You end up throwing all your units face first into the enemy spawn because there aren't any clumps of resources to warrant raiding.

Hover is also a massive advantage because you can send cheap hover units to mess with islands one after the other without worrying about potential pathfinding issues from navy. Although it was nice to see an actual purpose to T1 subs, because of all the spread out underwater mexes they can raid and be difficult to find. **I score this lower than Kings of Beta Ceti because its issues seem inherent to the map design, whereas Kings of Beta Ceti's are fixable.**

### Stulta Aqua Pugna: 15/16

I... struggle to put into words just how much I enjoyed playing this map. The spawns mean there is a 3v1 on each side, but that one player gets a massive starting bonus via the aforementioned pgens. Their teammates are also not too far away to help out, and indeed their best naval factory positions encourage helping their last player. Plus there's tons of opportunities for drops, proxy bases, naval raiding... ugh it's so good. Could use a few underwater mexes though for the early T1 sub gameplay I praised other other maps for. And maybe one or two big masses on the islands next to the solo player, get some early fightin' over there.

## Totals:

### Adaptive Fangtooth Islands: 27/40

### Kings of Beta Ceti: 20/40

### Project Vortex: 22.9999/40

See first impressions section for why it got a point reduction. >:(

### Stulta Aqua Pugna: 35/40

# Love you all and I hope I didn't hurt any feelings! Good work everyone, and Jip for hosting!
