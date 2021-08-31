---
title: Game & Balance Patchnotes 2011
description: 
published: true
date: 2021-08-31T12:44:10.511Z
tags: 
editor: markdown
dateCreated: 2021-08-31T12:44:10.511Z
---

# Complete Changelog of all chnages in 2011

## 3605

### Engine
- video, CPU, and sound performance optimizations.
### Lobby
-   12 Players lobby support, and infinite numbers of observers.
-   Adding big preview of the map.
-   Adding random map selection.
-   Adding share condition : The given units can disappears when you die.
-   Adding automatic formation of teams (Top/Bottom, right/left, odd/even slot)
-   Adding more units limits options.
-   Adding more colors.
-   'No Game ender' restriction changed to restrict T3 & T4 Artillery, Paragon, Novax and Yolona Oss
-   'No Nuke' Build restriction now correctly also restricts nuke carrying naval vessels, strategic
### Bug Fixes
-   Bug fix to prevent commander upgrades to be acquired at a lower cost through cancelling.
-   Fixed restoration field upgrade and advanced restoration field upgrade to not repair the ACU.
-   All Units shooting at the Seraphim ACU now aim at the correct bones instead of the feet.
-   Pausing a Mass Extractor while in mass deficit does now correctly stop mass consumption
-   Bomb drop prediction corrected on all T1 T2 T3 bombers
-   Seraphim Battleship now correctly plays a 'nuclear launch detected' sound when launching a nuke.
-   The Novax now correctly launches its satellite when the player is at pop cap.
-   Cybran Nuke Warheads now correctly detonate at their impact altitude, and not 20 units above
-   Nano Regeneration now gives Seraphim SCUs the correct amount of hitpoints (14k instead of 45k)
-   Seraphim SCU is no longer reclaimable
-   Seraphim Battleship nuke no longer flies at very high altitude.
-   Cybran Missile health normalized so that the parent missile has 1 health and the child missiles have 1 health each as well.
-   Gifting Units to allies bugs fixed
-   Change Naval yards to be hit with torpedoes, collision box lowered by 1
-   Hoplite now uses the correct amount of transport clamps
-   Fix Fatboy, Monkeylord, Megalith and the brick being able to fire from shallow water, being unattackable from land while doing so.
-   Increase lifetime & Speed on T3 Torpedo bomber torpedoes to avoid units outrunning them.
-   Fixed a bug that caused UEF ACU to deal damage to friendly units
-   UEF T2 Cruiser now can correctly use all weapons simultaneously
-   Seraphim Advanced Regeneration Field no longer provides a health bonus. It was permanent and wasn’t removed if the unit left the aura.

### Balance

#### General

##### Structures
-   Overcharge and Energy Storage gameplay improvement.
	>	- Energy Storage now costs 250M 1200E (from 120M 2400E), stores 5000E (from 2000E)
	> - Explodes for 2000 damage in a 5 radius (from 500 damage 3 radius), and has 500 health (from 1200)
	> - Start resources go to 4000E from 5000E, ACUs now generate 20E instead of 10 to compensate.
	> - Overcharge has an increased damage radius of 2.5 (from 2), and a reload of 0.3 (from 0.2).
  > - Overcharge now costs 5000E (from 3000). Damage vs Units is unaltered, damage vs ACUs is 400 (from 100), vs buildings 800 damage  from 500)

-   Factories and Engineers no longer increase Energy Storage.
-   T3 Air and T3 Naval Factories changed: mass cost equals land t3
    factory now.
-   T3 Air Factory energy cost increased (72000). Mass cost reduced to
    2750 from 3150.
-   T1 Anti-Air Turret

`Reduced mass and energy cost by 25%`
`Reduced build time by 25%`
`Reduced health to 800 from 1200`

-   T2 Artillery Installation

`Reduced mass and energy cost by 25%`
`Reduced build time by 25%`

T2 Anti-Air Flak Artillery

`Reduced mass and energy cost by 30%`
`Reduced health by 30%`

-   T1 Mass Extractor Health reduced to 600 from 800
-   T3 SAMs costs reduced significantly from 1400M 12000E to 800M 8000E