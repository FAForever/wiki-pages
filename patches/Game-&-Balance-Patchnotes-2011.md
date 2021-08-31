---
title: Game-&-Balance-Patchnotes-2011
description: 
published: true
date: 2021-08-31T13:03:27.674Z
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
- Overcharge and Energy Storage gameplay improvement.
	- Energy Storage now costs 250M 1200E (from 120M 2400E), stores 5000E (from 2000E)
  - Explodes for 2000 damage in a 5 radius (from 500 damage 3 radius), and has 500 health (from 1200)
  - Start resources go to 4000E from 5000E, ACUs now generate 20E instead of 10 to compensate.
  - Overcharge has an increased damage radius of 2.5 (from 2), and a reload of 0.3 (from 0.2).
  - Overcharge now costs 5000E (from 3000). Damage vs Units is unaltered, damage vs ACUs is 400 (from 100), vs buildings 800 damage  from 500)

- Factories and Engineers no longer increase Energy Storage.
- T3 Air and T3 Naval Factories changed: mass cost equals land t3 factory now.
- T3 Air Factory energy cost increased (72000). Mass cost reduced to 2750 from 3150.
- T1 Anti-Air Turret
	- Reduced mass and energy cost by 25%
	- Reduced build time by 25%
  - Reduced health to 800 from 1200
- T2 Artillery Installation
	- Reduced mass and energy cost by 25%
	- Reduced build time by 25%
- T2 Anti-Air Flak Artillery
	- Reduced mass and energy cost by 30%
	- Reduced health by 30%
- T1 Mass Extractor Health reduced to 600 from 800
- T3 SAMs costs reduced significantly from 1400M 12000E to 800M 8000E
##### Air
- T1 Bomber cost decreased to 80M 1400E from 100M 2250E
- T1 Bomber decreased build time to 400 from 500
- T1 Air Scout : Reduced energy cost to 1300 from 1600 and Reduced build time to 17 from 20
- Cost (M, E, time) of T2 Gunships decreased by 20%
- Lowered T3 Bomber maxairspeed by 1 (18 -> 17)
- T3 Air Energy costs increased 50%, with the exception of the Solace and Air superiority Fighters, who increased +100%. The Mass cost and buildtime on all these Units stays the same.
##### Land
- ACU Death nuke now does 2500 inner ring, 500 outer ring.
- T2 Mobile missile launchers damage increased 50%
- T3 Mobile missile launchers damage increased 100%
- Made T2 tanks slightly tougher and slower. T2 tanks now move at a 2.5 - 2.7 speed now, and have 20-25% more hitpoints in return. Cybran t2 tank got buffed more as it was too weak compared to the others. 
- Land Experimental cost increased \~20%, the cheaper ones increased more than the expensive ones (percentage wise).
- Increase striker, aurora and thaam movement speed by 0.1 (from 3 -> 3.1 or 3.3 -> 3.4)
- Landscout diversification:
	- Uef damage = 4 (+2)
	- Cybran cloak energy drain -5
	- Aeon radar range +5, new health = 20 (-3)
	- Seraphim radar range +5
- T2 Mobile Shields
	- Mobile Shield Generator: Asylum. Shield Health set to 3800. Shield Regenrate set to 58 Now requires 105 E to operate.
	- Shield HP reduced by 500
	- Energy consumption reduced by 10
	- built time increased by 10% (Aeon: 792 from 720/UEF: 660 from 600)
##### Sea
- Buffed Cruiser Anti Air damage by 25%
- Decrease T3 ship costs (\~15%) and buildtime (cut in half for many).
- Decreased Frigate & t1 submarine cost by 10%
- Increase frigate anti-air dps to 15, attack boat anti-air dps to 35, and Battleship Antiair dps to 60
#### UEF
- UEF Lobo t1 artillery health changed from 205 to 200
- UEF Mongoose health decreased from 900 to 650
- UEF Engineering Station Rover rebuild cost increased to 250M 2500E 750 time from 50M 500E 150 time (only applies if its shot down). Build rate decreased to 15.
- Billy reload timeout increased to avoid rapid firing through assisting
- Increase Shield ship cost by 30% from 1040M 10400E to 1300M 13000E
- Decrease T3 Air Transport costs by 30% (final E cost further adjusted by other changes)
#### Cybran
- Cybran Hoplite health decreased from 650 to 450.
- Cybran Engineering Stations: T1 cost increased to 500M 2500E from 450M 2250E. T2 build rate decreased to 25 from 30. T3 build rate decreased to 35 from 45.
- T1 Assault Bot: Mantis : Increased turret yaw speed to 90
- T2 Shield Generator: ED5 : Decreased mass cost to 1800, decreased energy cost to 26666, decreased build time to 1400, increased shield health to 15000
- Increased Cybran Deceiver (t2 mobile stealth generator) speed, acceleration and brake to match the values of other factions t2 mobile shields 
- T2 Point Defense dps increased damage to 13
- Firebeetle changed to deal 4500 damage, health lowered to 300, Firing tolerance increased to 100.
#### Aeon
- Aeon T3 Engineer build rate increased to 20 from 15
- Mercy fuel increased from 70 to 110
- Restorer max airspeed reduced to 8 from 10, health reduced to 6500 from 7200 and anti ground damage per shot reduced to 24 from 32. AA weapon damage increased to 71 \* 2 from 65 \* 2. • Restorers cost 50% + 400 more energy than a Air Superiority fighter now.
- Transferred 2600 from the Harbringer’s shield to its health
- Eye of Rhianne remote viewing radius decreased from 45 to 25.
- T4 Experimental Aircraft Carrier: CZAR : -Increased health to 58000 from 48000 -Decreased crash damage from 15000 to 10000