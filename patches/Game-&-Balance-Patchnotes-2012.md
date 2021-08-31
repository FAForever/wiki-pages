---
title: Game & Balance Patchnotes 2012
description: 
published: true
date: 2021-08-31T15:05:45.623Z
tags: 
editor: markdown
dateCreated: 2021-08-31T14:14:48.329Z
---

# Complete Changelog of all changes in 2012


## 3620

## 3615
### Known issues
- AZUI (not GAZUI) incompatibility : Breaking the whole UI on start.
### Exploit fixes
- Off mapping air units are now sent back into the map after a short period of time.
- Fixed an exploit were you can build half of a building for free.
- Fixed an exploit were cybran were able to instantly capture a a neutral unit.
- Fixed an exploit that made T2 mass fabricators upgradeable to T3.
### Bugs fixes
- Fixed aeon TMD range category being wrong.
- Fixed a bug with UEF ACU pod upgrade.
- Fixed a bug that make transports sometimes killing units during loading.
### Balance changes
#### General  :
- T3 naval factories cost now 5150 mass (+2000).
- Wreckages falling in the sea worth 50% of the original wreck value (due to corrosion/water dislocation obviously).
- Jamming is replaced by holographic system.
- New veterancy system :
 >	Killing :
	- T1 = 1 xp.
 	- T2 = 5 xp.
 	- T3 = 10 xp.
 	- XP/ACU/SCU = 100 xp.
 	- The interface is showing the current xp level, as well as the amount of xp necessary to gain a level.
 	- Only one level can be achieve on one kill. 
   ie : 
   if your next level (1) is at 5, and the following (2) at 8. Your current XP is 0.
   You kill a T3 unit, you will get to veterancy level 1 - and not 2.
- Implementing the shield interference script : It Reduce the recharge rate when shields are overlapping. :

 > For each shields under the dome of one shield (mobile or fixed, but not personal), 
 the recharge time (after being downed), is increased by 20%, with a maximum of 200%.
### Tier 1
- Air scouts
> Cost 420 E (from 1300), builtime 145 (from 340). 
 Added radar and sonar vision (65 and 30).
- All t1 tank speed increased by 0.1.
- Sera T1 arty :
> Minimum firing radius augmented to 8 (from 6)
 TurretYawSpeed decreased to 60 (from 70)
- Changing medusa randomness from 1.5 to 1.2
### Tier 2
- T2 Gunship : Health reduced to 80% of the original value.
- Siren proto cannon buff to 92.
- Firebeetle enhancements : You can ctrl-k the firebeetle to produce instant damage. They are not sensitive to each other explosions. Increased AOE to 3.5, firing tolerance to 4 and maxradius to 4.5.
### Tier 3
- UEF BattleCruiser :
> mass : 7.000 (from 6.000)
 energy : 60.000 (from 52.000)
 buildtime : 20.000 (from 12.000)
- Seraphim T3 submarine :
> Salvo delay increase to 1.5 (from 1).
 Resulting in a DPS of 223 instead of 335 before. 
- Cybran T3 battleship :
> Mass : 8.000 (from 9000)
 Builtime : 12.000 (from 18.000)

### T4 Changes
#### UEF
- Satellite Station :
>	Energy = 400000,
 	Mass = 20000,
 	BuildTime = 25000,
 	Comsume 1000 Energy.
 	Have a radar radius of 65 and a vision of 32 (from none and 10).
 	Damage increased to 100 (from 75).
#### Cybran
- Soul Ripper :
> Energy = 480000,
 Mass = 28000,
 BuildTime = 20000
- Scathis :
> Energy = 780000,
 Mass = 63000,
 BuildTime = 31500
- Monkeylord Veterancy :
> Level1 = 75
 Level2 = 125
 Level3 = 200
 Level4 = 275
 Level5 = 350
#### Seraphim
- Ythota Veterancy :
> Level1 = 75
 Level2 = 125
 Level3 = 200
 Level4 = 275
 Level5 = 350
#### Aeon
- Tempest cost halfed.
- Galactic Colossus Veterancy
> Level1 = 100
 Level2 = 200
 Level3 = 300
 Level4 = 400
 Level5 = 500

## 3614
### Bug fixes
- You can now pause the anti-nuke missile construction.
- Fixed a warning "info: Warning: \000/projectiles/tananglertorpedo06/tananglertorpedo06_proj.bp\000 has mesh defined both inline and by reference"
- Fixed sera t2 torpedo launcher projectiles going through islands and damaging enemy units.
### Balance changes
- T1 Bomber reload time increased to 4 seconds (from 2), to fix bomb drop exploit/abuse.
- Reverted the T1 Tank speed to 3599 (-0.1 in speed except for mantis).
- Fixing the UEF T3 bomber energy cost. It now costs the same as the other factions.

## 3610
- Scores were not registered correctly.
- Chat was doubled in game.
- Replays were not playing.