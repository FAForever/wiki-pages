---
title: Game & Balance Patchnotes 2013
description: 
published: true
date: 2021-08-31T14:54:09.837Z
tags: 
editor: markdown
dateCreated: 2021-08-31T14:46:17.963Z
---

# Complete changelog of all changes in 2013



## 3628


## 3626


## 3625


## 3624


## 3623


## 3622
This is a huge patch, addressing all kind of bugs and balance problems.

This is the result of a month of work, and we are confident that all changes are for the better.
But if there is any broken change (balance-wise), an emergency patch will be released.
Thanks to Pip, ColonelSheppard, FunkOff and all the testers for their hard work !

### FA Lobby update (thanks to Xinnony) :
- Add Autokick label and remove observer label status
- Reorganised sections for AI settings.
- Displaying if the game is ranked or not.
- Fixed the loading of custom maps options (survivals,….).
- More different colors (thanks to RK4000, pip and some others).
### Ranked (automatch) :
- Ranked games have score disabled.
### Interface enhancements :
- HotStat is integrated in the final score screen (unless the game is not over to avoid cheating). (thanks to Zulan)
- Score panel font is smaller to display more infos (rating,…)
- Score panel is wider for the same reason.
- Score is truncated for more visibility (20.000  will show as 20k)
### Replay :
- The avatar section (under score screen) is hidden in replay.
- Economy panel is hidden on observer mode, and displayed correctly when selecting a player.
- Score is displaying the mass and energy income of all players. (thanks to Zulan)
### Bug fixes :
- Code base is now compatible with retail/DVD version.
- Fixed issues with scores. (“no score” visible with some UI-mods, …).
- Fixed some errors popping up in the logs with transports.
- Fixed the nomads icon not displaying in chat.
- Fixed T1 Aeon bomber and T2 seraphim bomber not dropping bombs.
- Better aurora micro-management (more responsive to orders). (thanks to dstojkov)
- The mantis miss less when moving. (thanks to dstojkov)
- Fixed : Individual trees were giving more mass than group of the same tree. (thanks to Arkansas)
- Fixed : Experimental have now other experimentals and SCUs on top priorities.
- Fixed : SAMs now have EXPERIMENTAL as high priority targets.
### Balance changes  :
#### General
- Reducing energy storage destruction to 1000 (from 2000).
- Remove death weapon on energy storage if self-destroyed.
- Stationary shields overlapping are passing 15% of the damage instead of 50%.
- Aeon ACU Chrono Damperer : mass: 1750 (from 2500), energy: 52500 (from 125000), buildtime: 875 (from 1250). Max range = 35 (from 22)
- Cybran ACU regen rate : 15 -> 18.
- Titan shield & armor HP inverted.
- Soul Ripper veterancy requirements increased : 60-120-180-240-300 (was 40-80-120-160-200).
- UEF tactical nuke “billy” : Energy = 315000 (from 630000), Mass = 5400 (from 10800), BuildTime = 4000 (from 10800). Increased missile health by 2.
- Cybran Frigate : AA weapon damage = 4 (from 3) = 16 DPS (from 12), muzzle velocity = 60 (from 45).
- Cybran Destroyer AA weapon damage = 10 (from 2) = 60 DPS (from 12).
- Turn rate of Cybran frigate and aircraft carriers projectiles increased to 25 (from 12).
#### Air :
#### SAMS :
- Health = 7000 HP (from 10500),
- DamageRadius = 1.5 (from 0);
- Muzzle Velocity = 45 (from 30, except Seraphim, remains at 100)
- Increased veterancy level (24 – 48 – 72 – 96 – 120  was 12-24-36-48-60)
#### ASF
- Aeon ASF : HP = 1750 (from 2500), mass cost = 350 (from 400), wreck value = 45% (from 90%)
- Cybran ASF : HP = 1700 (from 2450),mass cost = 350 (from 400), wreck value = 45% (from 90%)
- UEF ASF : HP = 1850 (from 2600), mass cost = 350 (from 400),wreck value = 45% (from 90%)
- Sera ASF : HP = 1800 (from 2550), mass cost = 350 (from 400),wreck value = 45% (from 90%)
### T2 units buff :
-Obsidian : +0.3 speed (2.6> 2.9)
-Rhino : +0.5 speed (2.7>3.2)
-Pillar : +0.3 speed (2.7>3)
-Ilshavoh : +0.1 speed (2.6>2.7)
-+100 HP to Hoplites.
#### Cybran Firebeetle :
-damage radius = 4.5 (from 3.5)
-MaxRadius = 4.4 (from 4.5)
-Damage = 3000 (from 4500)
-Firing tolerance = 180 (from 4) ; it means the unit doesn’t have to face its target to explode.
-Firebeetles are now immune to each other explosion, meaning they are much more threatening in numbers.
-Added a button that makes instant death explosion, the same way CTRL+k does.
#### SCUs
##### Aeon SCU :
- gun upgrade gets +10 range (total = 40)
##### UEF SCU :
- high ordonance upgrade  + 10 range (= 35)
##### Cybran SCU:
- weapon upgrade gets + 10 range (= 35)
- EMP upgrade cost is reduced to 1000 mass (from 1500) and 2400 buildtime (from 4800) ;
- AOE is slightly buffed to 3 (from 2.5), duration is set to 4 (from 3) and ProjectileLifetimeUsesMultiplier becomes 1.30 (from 1.15) so that the longer range shot doesn’t disappear (because it doesn’t last long enough!!!).
##### Seraphim SCU :
- Nano upgrade cost = 2500 mass (from 1500) because it adds 14000 HP to the health of the unit, so it should be more expensive than the others nano upgrade (and not cheaper). Even at this price, it’s the best defensive upgrade of all the SCU.
- Overcharge cost = 4500 mass (from 3000), energy cost = 300 000 (from 200 000), buildtime = 10000 (from 9000).
- Sensor upgrade : mass cost = 800 (from 1000), energy = 36000 (from 2000), new vision radius = 36 (from 45), new omni radius = 60 (from 80), adds +10 range to main weapon (but not to Overcharge weapon).
### T3 artilleries :
- 20% mass reduction cost :
- Aeon Emissary: 73200 (from 91500)
- Cybran Disruptor: 69600 (from 87000)
- UEF Duke: 72000 (from 90000)
- Seraphim Hovatham :70800 (from 88500)
### Game Enders (except Scathis)
- 25% mass reduction cost :
- Salvation : 202500 (from 270000)
- Mavor : 224775 (from 299700)
- Seraphim Yolona Oss : 187650 (from 250200)
### Scathis :
- Energy = 1500000 (from 93000)
- Mass : 85000 (from 63000)
- Scathis is now amphibious (not floating !)
- Speed 1.5 (from 1)

