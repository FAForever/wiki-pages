---
title: Game & Balance Patchnotes 2013
description: 
published: true
date: 2021-08-31T15:07:58.563Z
tags: 
editor: markdown
dateCreated: 2021-08-31T14:46:17.963Z
---

# Complete changelog of all changes in 2013
## 3628
This patch is a graphic enhancement patch only.

It introduce a better handling of the debris during explosions :

http://www.youtube.com/watch?v=IybuyjVZc10

It is also disabling bloom in all fidelity presets (bloom hide most of the nice particle effects, it may be reworked later).
## 3626
The patch 3626 is now released.
This patch is the result of months of work, and the first step of the “Next” project.

A few months ago, a indiegogo campaign was launched to make Galactic War happening, but also bringing FA to the next step.

This patch include lot of radical changes, new graphics, and overall a major step forward compared to previous patches.

In order to ease the transition to “Next”, most of the featured mod will run patch 3625 until they are ready to make the transition. Here is the list of featured mod that will NOT take 3626 patch as a base version :

- Nomads
- Blackops
- Diamond
- Supreme Destruction
- Xtreme Wars

Nomads will be implemented as part of the Next project in a future patch. Others mods will need their author to be updated to Next.

### Graphics enhancements
- New factories models (thanks to Armageddon and Bokker).
- New shaders for terrains (thanks to KarottenRambo).
- New particles effects and textures (thanks to Luxor144 and Resin Smoker).
- New strategic icons to differentiate some units (thanks to Errorblankfield).
### Interface & New options
- Adding a option for sharing unit cap.
- Adding a restriction for support factories (see below)
- Splitting Attack orders with Shift+G (thanks to Blackops team and johnie102) :
	- Select some of your units. Make them attack a bunch of enemy units.
	![3626-shiftg1.jpg](/patch-images/3626-shiftg1.jpg)
	- Press shift-G.
	- Each of your unit is now attacking a separate group of enemy units.
	![3626-shiftg2.jpg](/patch-images/3626-shiftg2.jpg)
### Bug/exploit fixes
- Fixed a bug where ACUs were able to overcharge  without the necessary energy in storage.
- Reclaim time of group of trees now match individual trees.
- Fixed a bug where the Hive was able to generate mass from thin air.
- Recharging shields no longer receive damage from other, overlapping ones.
- Ahwassa was not leaving a wreck in water.
- Units are sorted by mass cost when given in Full Share.
- Aeon shield Disruptor gets back its specific icon.
- Cybran Deceiver and static stealth radius were not displayed properly.
- All strategic subs now display their tactical missile range.
- UEF Battleship has now a reload bar  for the front canons.
- Galactic Colossus first target bone changed to be the torso instead of the head to help fighter/ bombers hit it properly.
- Czar : SPECIALHIGHPRI category added, so that ASF will target it first without the need to manually target it.
- Aeon SCU RAS cost fixed : 4500 mass, like the other SCU.
### Economy
Multiple t2/t3 factories and t2/t3 engies to build and assist are now cost efficients (Thanks to Rienzilla and Zock) :
- The normal factory is renamed to t2/t3 factory Headquarters.
- If you have at least one Headquarter, you can now build some new, cheap factories (called support factories)
- If you lose all Headquarters, these support factories can make only t1 units until you make a new HQ.
- Lot of build powers are adjusted, check the Unit database for more details.
- You can remove the support factory in the restriction menu of the FA lobby, it will disable this new mechanic.
### ACUs
#### Cybran
- Cybran ACU base regeneration to 17.
- 4 hp regeneration per veteran level instead of 3.
#### Seraphim
- Restoration Field:Radius = 22 (from 15) same as weapon range.
- Rapid Restoration Field : Radius = 30 (from 25) same as upgraded weapon range.
- Refracting Chronotron Amplifier :
- Additional Damage = 400 (from 300)
- Build Cost Mass = 3500 (from 4500)
#### Aeon
- Enhanced Sensor System :
- Build Cost Energy = 10000 (from 12500)
- Build Cost Mass = 400 (from 750)
- BuildTime = 500 (from 625)
#### UEF
- nano upgrade :
	- 1200 mass
	- 44800 energy
	- 1400 buildtime
	- 60 regen.
### T1 units
- Aurora is missing a bit less and better handling. Muzzle charge delay reduced to 0.1 .
- Medusa Firing Randomness increased to 1.35 (from 1.2)
### T2 units
#### General change
- Target priorities changed : Rhino, Ilshavoh, Riptides, Blazes : target Tech 3, tech 2 then Tech 1 instead of Tech 1 then tech 2 then tech 3.
#### Aeon t2
- Blaze
	- Speed to 4.3 (from 3.7)
	- Muzzle velocity up to 45 (from 40)
	- Firing tolerance reduced to 0 (from 2) to increase hit rate.
- Aeon T2 mobile shield
	- energy consumption decreased to 75 (from 125)
	- size reduced to 15 (from 16).
- Aeon Obsidian
	- health = 1250 hp (from 1000)
	- shield = 1500 (from 1750)
	- shield recharge start time = 3 seconds from 1 second
	- muzzle charge delay reduced to 0.1
	- speed reverted to 2.6 (from 2.9)
	- turret yaw speed reduced to 75 (from 90).
- Aeon Destroyer Exodus
	- muzzle charge delay = 0.1 (from 0.5);
	- turret yaw speed = readjusted to 100 (from 160)
#### Cybran T2
- Rhino :
	- Health = 1900 hp (from 1150)
	- MaxSpeed/max acceleration/maxBrake = 2.7 (from 3.2)
	- Damage = 25 (from 16), rate of fire = 1.8 (from 2) = 90 DPS (from 64)
	- BuildCostEnergy = 1500 (from 990); BuildCostMass = 297 (from 198)
	- BuildTime = 1320 (from 880) ; surface threat level = 5 (from 3)
	- veterancy = 8/16/24/32/40 (from 7/14/21/28/35)
- Cerberus :
	- damage reduced to 10 from 11 = DPS reduced to 100 DPS (from 110)
#### Seraphim t2
- Yenzyne (Seraphim T2 hover tank)
	- speed up to 4.3 (from 3.7)
	- 200 damages (from 175) for 50 DPS (from 43)
	- range increased to 20 (from 18)
	- firing tolerance = 1 (from 2),
	- turret yaw speed = 110 (from 90)
- Ilshavoh
	- speed reverted to 2.5 (from 2.7)
#### UEF t2
- UEF mobile shield
	- size slightly increased to 17 (from 16)
- Pillar
	- rate of fire = 0.8 (from 0.75)
	- DPS = 56 (from 52.5)
### T3 units
#### General change: Veterancy adjustments.
- Brick/Percival veterancy levels = 20/40/60/80/100 (from 9/18/27/36/45)
- Othuum and harbingers veterancy levels = 15/30/45/60/75 (from 9/18/27/36/45)
- ASF veterancy levels = 12/24/36/48/60 (from 6/12/18/24/30)
- Restorer veterancy adjustment: 18/36/54/72/90 (from 12/24/36/48/60)

#### Strategic submarines rework.
- For all strat subs :
	- nuke launcher adjustments : 3.3 speed (from 2.5)
	- range reduced to 410 (from 1024)
	- nuke price is similar to static ones:
	- BuildCostEnergy = 1350000 (from 1764000)
	- BuildCostMass = 12000 (from 16800)
	- BuildTime = 324000 (from 453600) = 5 minutes (from 7 minutes)
#### Sera Battleship Nuke
- cost = same as old strat sub costs.
- damage reduced to 25000 (from 70000)
- BuildCostEnergy = 1764000, (from 1920000)
- BuildCostMass = 16800 (from 19200)
- BuildTime = 453600 (from 518400) = 7 minutes (from 8 minutes)
#### Aeon t3
- Harbinger will now reclaim when on patrol.
- Aeon Battleship
	- muzzle charge delay = 0.1 (from 0.5)
- Torrent Missile Ship
	- AOE = 2 (same as regular tac missile, from 1.5)
- Aeon snipers 
	- mass cost reduced to 640 (from 800).
	- buildtime to 3600 (from 4800).
	- doesn’t need to deploy, inacurate when moving.
	- 1350 damages (from 1300) to prevent massive overkill on Percival.
	- strategic icon is now a straight horizontal line
- Aeon strat sub 
	- tac missile range increased to 175 (from 128),
	- missile hp
	- OE increased to 3 (from 2)
#### Seraphim t3
- Othuum Thau canon (the slow and weak weapon with 100 DPS) range = 32 (from 25) with indirect fire (yellow) ring.
- Sera t3 shield : mass cost slightly reduced to 540 (from 640)
- Sera sniper :
	- mass cost reduced to 640 (from 800)
	- buildtime to 3600 (from 4800)
	- has a turret now
	- inacurate when moving (0.8)
	- 775 damages (from 750) to prevent overkill on Percival
	- strategic icon is now a straight horizontal line
#### UEF t3
- Percival
	- Builtime increase to 6000 (from 4800)
	- uses a new strategic icon (x) to distinguish it from Titan (+)
- Continental (T3 transport)
	- shield energy consumption = 400 (from 250)
	- veteran adjusted to : 12/24/36/48/60 (from 3/6/9/12/15)
	- energy price normalized with other t3 air units (cf.3603 patch) : 52500 energy (same as Broadsword, less than Restorer) (from 29531 energy). Reason: GPG forgot the Continental when they made all t3 air units much more energy demanding in 3603.
- UEF strat sub 
	- tac missile range increased to 175 (from 128)
#### Cybran t3
- Brick :
	- Builtime increase to 6000 (from 4800)
	- uses a new strategic icon (x) to distinguish it from Loyalist (+)
- Cybran Strategic sub gets stealth + Tac missile range increased to 200 (from 150)
### T4 units
#### General change : Veterancy levels adjustments.
- Ythotah : 70/140/210/280/350 (from 75/150/225/300/375)
- Galactic Colossus and Megalith : 90/180/270/360/450 (from 100/200/300/400/500)
- Monkeylord : 45/90/135/180/225 (from 75/150/225/300/375)
- Fatboy : 40/80/120/160/200 (from 75/150/225/300/375)
#### Atlantis
- max speed =2.8 (from 2.5)
- Atlantis AA gets same AOE as SAM = 1.5 (from 0)
#### Monkeylord
- 19k mass (from 21k)
- stealth field (radius = 30, same as laser) instead of personal stealth
- stealth energy consumption = -400 (instead of – 250).
### Balance Team credits :
Pip, Blackheart, Crazed, Lu_Xun_17, Nombringer, TAG_Chosen, Voodoo, Zock

## 3625
This a quickfix to 3624.
- Reduced the Cerberus cybran DPS.
- Removed the SCU teleport stun.
- Added a teleport beacon on SCU teleport.
## 3624
This is a quick fix, solving two small “imbalances” and some bugs, all thanks to Pip.

### Balance change :
- Mantis: turret turn = 100 (from 120), +10 compared to 3621 and before.
- Titan Health and shield HP switch was forgotten.
- Adding a blast radius effect (not dealing any damage) after a SCU teleport.
- Adding a 10 seconds stun after a SCU teleport.
### Bug fixes :
#### Colors :
- Fixed order of colors so that blue and red are first (for automatch).
- Changed red to “Cybran red”.
- Removed light green that is too similar to white.
- Changed light grey into a darker grey.
- Checked that all the first 8 colors are not to difficult to distinguish for common color blind people.
### In-Game fixes :
- Fixed SAM homing missile not reaching their target with the new Area of Effect.
- Fixed Aeon ships with Oblivion weapon (Destroyer, Battleship, Tempest) missing when turning.
- Fixed the Rhino and Cerberus projectiles not able to hit moving targets.
- Cerberus and Rhino lasers are now visible even if you don’t see the “source”.
- Fixed the UEF Janus dropping its bombs often in a small zone in front of the target, dealing no damage or almost

## 3623
This patch is a quickfix release for 3622
- A tree blueprint was missing a line.
- Fixed : Score not displaying at the end of the game.
- Fixed : Sera ACU and SCU nano were overriding regen.
- Aeon Chrono Damperer radius was not 35.

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

