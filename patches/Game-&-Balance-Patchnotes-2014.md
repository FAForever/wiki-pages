---
title: Game & Balance Patchnotes 2014
description: 
published: true
date: 2021-08-31T15:27:19.992Z
tags: 
editor: markdown
dateCreated: 2021-08-31T15:23:30.189Z
---

# Complete changelog of all changes in 2014

## 3636
## 3634
## 3633
## 3632
This is a quick fix release.
- Fixed Broadsword Damage Per Second (was nerfed by mistake to 33% of the actual value).
- Fixed a bug where units weren’t damaged when a personal shield was in recharge state.
As usual, if you are playing on FAF, you already have the patch.

## 3631
- Tons of little bug fixes in the interface.
- Key binding panel is more robust now.
- When binding a hotbuild key, if the shift/alt key combo is already binded, you will get an option to unbind them so hotbuild will be able use them.
- You can now rotate the templates that are done through hotbuild.
- The balance tweaks & some exploits were not really fixed in 3630 due to a bad merge of the code. They are now in 3631.

## 3630
### Exploits & bug fixes
- Removed dbg_ShowAiPathSpline console command from the game. That command was allowing to see units movements under the fog of war, without triggering the “XX has tried to cheat” warning/error.
- Fixed an exploit were carriers where able to transport any other carrier unit (ie. fatboy, air transports,..) by ground assisting with the carrier and reclaiming the other unit.
- Fixed a bug introduced by the “Duplicating building with wreckages” exploit fix, where building lower/higher tech building over wreckages were canceled.
- Fixed a bug/exploit where splash damage were transferred twice when a shield collapse (noticeable with the Seraphim T4 bomber, but also affecting all area of effect damage).
- Fixed a bug where bombers stop dropping bombs after ground attack on trees.
- Cybran T3 gunships now make a sound when destroyed.
- UEF depth charges now make a sound when launched.
### Performances
- Improved path finding late-game. Previously, some units weren’t answering to move order.
- Fixed a lot of AI related script errors (should slightly improve performances with AIs).
### AI
- Implemented Duncan fixes for AI. Most of them were already there, but the standard AI should behave slightly better (Sorian AI is still way better).
### UI
- Hotbuild & GazUI mods are now implemented in FA :
- Press F1 to rebind keys. A lot of new selection options are now available (Select idling scouts, select all land factories on screen, select all air without transports,….).
- New options are now available in the option menu. They are described in the tool-tip. (Big strategic icons, “draggable” build queues, rotating templates, better economic panel, ..)
- SCU manager is implemented. You have a little icon in the avatar panel (below score) to do upgrades sequentially on SCUs. Two paths are available and configurable : Combat & Engineer. You can also bind the “SCU marker” (F1) shortcut to automatically upgrade SCUs near that marker.
- Hotbuild is a new build mode allowing you to press several time a key to go through all kind of buildings. Works also to build units in factories through the same shortcut. Check the Hotbuilding section of the keymapper (F1)
### Balance tweaks
- Aurora fire randomness while moving reduced to 0.1 from 0.6. It’s likely that the value will be tweaked in the future.
- Engineer will reclaim mass extractors wreck instead of getting the “half-built” bonus when building a lower tech mass extractor than the wreckage. Using the half-rebuilt bonus is always a mistake economically-wise and shouldn’t be allowed.
### Important note for current users of GazUI/Hotbuild.
It’s very likely that a mod version of GAZUI will mess with your game.

Using your current hotbuild mod shouldn’t do anything bad, except that the mod is messing with key-binding. So use it at your own risk.

#### GazUI
All your options should be keep the same way as before. You will get new options for selecting units, as well as fixes for big Strategic icons option and SCU manager fixes.

#### Hotbuild
The existing mod was more an hack than a mod.

But the new way of key binding hotbuild will allow you to rebind it more easily and really fast. The order of the options in they key bind menu (F1) is the same as the original mod.

Meaning that to have the default key bind of the original mod for US keyboard, you should bind, in order:

W,E,R,T,Y,U
S,D,F,G,H,J,K,L
Z,X,C,V,B,N,M

As you can see, it is the key in the order of your keyboard 🙂

The integrated mod will take care of binding the corresponding shift/alt combos.
If there is a shortcut on one of these combo (ie. shift-W is already used), the combo won’t be made, and a warning will show in the log (game.log) :

WARNING: Shift-W is already bind

You can be okay with that or unbind the key. It will retry to make the hotbuild combo immediately (you don’t need to restart FA or your game).


## 3629
This is the first release candidate: If you see any problem, please report it as soon as possible in the forums and we will try to fix it. Replays might break during the release candidate period.

### FA Game lobby & Interface
- Caching interface files to remove UI-lag, especially when selecting builders.
- Adding an icon if a player is Dead in Connectivity and Disconnect windows.
- Add Auto-Kick after 3 minutes on Disconnect dialog.
- Adding a new button on the menu to hide/show all settings of this game.
- You can now make game presets.
- Add new unit restrictions : TELEPORT, BILLY, ENGISTATION, SALVATION, MAVOR, SCATHIS, PARAGON, SATELLITE.
- Several speedup in the lobby (connections attempt are now multi-threaded).
- Fixed “Faction not set” when moving from Observer to Player.
- Fixed the possibility to move an Observer to Player with the Observer Button.

Done by Xinnony and Duck42.

### New feature
SCU presets with already upgraded SCUs buildable from Quantum Gateways (The costs of the upgrades are added to the cost of the SCU base).

### Bug fixes and small tweaks
- Fixed an exploit that allowed to duplicate infinite amount of buildings for free (Drag & dropping when rebuilding from a wreck).
- Cybran T2 and T3 Engineers HP fixed.
- Fireball explosion is now red instead of green.
- Cybran SMD BuildTime fixed.
- Czar central target bone removed to reduce the likelihood of ASFs flying right through the beam and being roasted.
- Czar beam weapon has a 75% Damage reduction against ASFs so they are not insta-killed any more when they do fly right through the beam.
- UEF TMD Projectiles fixed. They were dying too soon to kill Tactical Missiles launched from ACUs – Weapon Unpacks = false (From true).
- Several Beam weapons – Small improvements from ShadowKnight’s mod (Not all) to make them deal damage more “Smoothly” and change targets more efficiently.
- Sera T2 Point Defense – 550 damage (From 660) due to beam weapon changes amounting to a buff (137.5 DPS from 165, but will sweep through several units until it deals its full 550 Damage meaning less overkill).
- Tempest MuzzleVelocity reverted to 28 to prevent it to shoot over small targets like mass extractors.
- Firebeetle TurnRate increased to 160 (From 120) and TurnRadius increased to 4 (From 3) for a small handling improvement.
- Rover BuildRadius = 8 to fix an issue where it would not finish the buildings it started to build.
- ASFs can’t shoot Rovers (Prevents them being used to kill Shields and Base Structures late game VS UEF). Special 75% resistance to Czar beam.
- ASF Projectiles Aeon and Seraphim now shoot 1 projectile instead of 3, and have FiringTolerance = 2 (Don’t need to line up totally to fire, the same as the others). Cybran shoots 2 instead of 4. DPS is unchanged (This greatly lowers lag caused by large ASF battles).
- ASF HP changed because the projectile adjustments impacted balance. This corrects it again. UEF = 1800 (From 1850). Cybran = 1725 (From 1700). Seraphim = 1775 (From 1800)
- Seraphim ASF TargetCheckInterval adjusted to 0.5 (From 0.3).
- Seraphim T2 Artillery PitchRange = 90 (From 80) to fix it not being able to fire to maximum range.
- Cybran Strategic Missile Submarine Stealth now hides it from Sonar too.
- Better animations for walking bots – Mongoose, Titan, Brick, Aeon Sniperbot, Percival.
- Out of fuel speed penalty reduced to 65% from 75% to increase the possibility of reaching Air Staging when far away (Also, T1 Bombers won’t drop two times on the same target due to too low speed).
- Cybran T2 Air Support Factory no longer has a weird colour when zoomed out.
- T2 and T3 Engineer price reduction. T2 = 140 Mass/700 Energy/700 BuildTime (From 160/840/800). T3 = 440 Mass/2200 Energy/2200 BuildTime (From 490/3150/2100).
- Seraphim Air Factory overall Engineer production rate reduced via rolloff time (It is still faster than the original but not crazy fast any more, speed similar to Aeon). They already have the best Bomber and have Fobo on water maps, they don’t need to have better Air Factory too.
- T1 Bomber drop chance increased – TurnSpeed and CombatTurnSpeed = 0.75, 0.8 for UEF (From 0.7). LiftFactor = 10 (From 7).
- Bombers targeting a wreck are no longer permanently prevented from firing (By Brute51).
- Janus won’t scorch the earth any more when bombing a Shield.
- Sparky added to Air and Naval factories.
- Teleport has brand new visual and audio effects (By Brute 51).
- Teleportation now deals only 100 Damage to nearby Units and Structures in a small radius (Doesn’t kill T1 Engineers any more).
- Shield Stacking Damage overflow and transfer refactored (By Brute51) to prevent Resonance Effect (First Shields hit no longer take more Damages than the Damage dealt by the weapon in the first place). Overlapping Damage dealt = 15%.
- Cybran build drone bug/exploit fixed (By Brute51).
- DifferentialUpgradeCostCalculation = true, in units/ZAB9602/ZAB9602_unit.bp
### Balance Changes
#### Structures and Weapons
- Cybran TML Split Projectiles Speed = 15 (From 25). Acceleration = 6 (From 25).
- Static Flak buffed with faction diversity in mind.
	- One Projectile at a time = more Range, Better accuracy, more Frontloaded, less Area Of Effect
	- UEF
	>	Damage = 125 (From 102)
		AOE = 3.5 (From 4)
		MuzzleVelocity = 25 (From 20)
		RateOfFire = 1.25 (From 1.5)
		Range = 50 (From 44)
		FiringRandomness = 2 (From 2.5)
	- Aeon
	>	AOE = 3
		MuzzleVelocity = 30
		FiringRandomness = 1.5 (From 2.5)
		Range = 50 (From 44)
		Several Projectiles at once = less Frontloaded but covers more aerial space
	- Cybran:
	>	MuzzleVelocity = 20
		AOE = 5 (From 4)
		FiringRandomness = 4 (From 2.5)
	- Seraphim :
	>	2 Projectiles at once.
		AOE = 3 (From 4)
		MuzzleVelocity = 25 (From 20)
		Damage = 50 (From 53)
		RateOfFire = 1.5 (From 1.25)
### Land Units:
#### ACUs
- Seraphim ACU Restoration Field 1
	>Adds 1000 HP to ACU
	2% HP Regeneration (From 0.5), but capped at 15 (From 75)
- Sera ACU Rapid Restoration Field
	>Name changed to Advanced Restoration Field
	Adds 1500 more HP to ACU
	Adds 10% HP to units nearby, as it used to do.
#### T1 Land
- Aurora
	>Speed = 2.9 (From 3.1) ;
	FiringRandomnessWhileMoving = 0.6 (From 0). It’s a very small randomness and only when the Auroras move. They will still hit most of the time but this gives a chance for other tanks to survive longer. This value can be adjusted to make Auroras not as efficient when retreating, but good when they are still.
- Medusa
	>Stun duration for T2 units = 2 seconds (From 3)
	Reload time = 6 seconds (From 5)
	Damage = 230 (From 195)
	Roughly the same DPS (38.33 instead of 39)
- Lobo
	>Damage = 400 (From 480)
	Reloads every 8.33 seconds (from 10) for the same DPS (48)
- T1 Mobile AA
	>Vision Radius = 20 (From 18)
#### T2 Land
- Mongoose
	>TurnSpeed = 90 (From 150). TurretTurnSpeed = 80 (From 50). This means the unit tracks and targets enemy units better
	FiringTolerance = 1 (From 0.1)
	Grenade Weapon adjusted:
	Damage = 50 (From 65)
	RateOfFire = 0.15 (From 0.1) for 30 DPS (From 26),
	FiringRandomness = 2.5 (From 2),
	PitchRange = 55 so that it can shoot to its fullest range.
- Ilshavoh
	>Veterancy Nerf: Threshold = 10 (From 9).
### T3 Land
- Aeon Sniper
	>Damage = 950 (From 1350)
	Reload = 7 seconds (From 10)
	DPS unchanged
	FiringRandomnessWhileMoving = 0.75 (From 0.8)
	FiringTolerance = 0 (From 2)
- Seraphim Sniper
	>Damage = 580 (From 775)
	Reload = 5 seconds (From 6.7)
	FiringRandomnessWhileMoving = 0.75 (from 0.8)
	FiringTolerance = 0 (from 2)
	Sniper Mode = 2000 Damage (From 2800)
	Reload = 14.5 seconds (From 20)
	FiringRandomnessWhileMoving = 0.6 (from 0.8) because Speed is reduced greatly
### SCUs
- Veterancy adjusted to 25/50/75/100/125 (From 20/50/90/140/200)
- SCU Engineering Upgrade cost = 800 Mass (From 1000). BuildTime = 4200 (From 5040). Also fixes Aeon SCU having the wrong cost
- UEF SCU Drone Mass = 380 (From 480). BuildRate = 35 (From 20)
- UEF SCU Bubble Shields now considered a Mobile Shield (Like Shield Boat) and will suffer from overlapping
### Air Units
#### T1 Air
- Scorcher (UEF T1 Bomber)
	>4 Bombs with 3 AOE (Instead of 5 with 2.5 AOE)
	Bombs are more spread out, and each deals 47.5 Damage instantly + 10*4 = 40 damages over 1.5 seconds = 350 total (It will never deal 350 Damage except on Factories. The maximum amount on Units and small Structures is 267.5)
	TurnSpeed = 0.8 (From 0.7)
	BreakOffDistance = 26 (From 18)
- Jester
	>Range = 20 (From 16). This fixes the fact that they stop shooting when attacking moving targets or are on Attack-Move orders)
	Veterancy nerf: Threshold = 5 (From 3)
#### T2 Air
- Janus
	>Ground weapon Range = 60 (From 45)
	LiftFactor = 10 (From 7) to increase the chance of dropping
	Deals half its Damage instantly and the rest over time (Instead of all Damage being dealt over time)
- Seraphim Fighter/Bomber
	>Ground weapon Range = 60 (From 45).
	LiftFactor = 10 (From 7) to increase the chance of dropping.
- Corsair
	>Anti-Ground weapon Range = 40 (From 45) so that it doesn’t completely out-range Mobile Flack (No longer able to kill them without suffering any damage)
#### T3 Air
- Heavy Gunships
	>Speed + 2
	Cost and DPS cut by roughly 25%
- Wailer :
	>MaxAirSpeed = 10 (From 8)
	Mass = 1260
	BuildTime = 6400
	Energy = 42000 (From 52500)
	Damage = 140 (From 150)
	RateOfFire = 1.6 (From 2). DPS = 224 (From 300)
- Broadsword
	>MaxAirSpeed = 10 (From 8)
	Mass = 1260
	BuildTime = 6000
	Energy = 42000 (From 52500)
	Damage = 90 (From 100)
	RateOfFire = 2.5 (From 3). DPS = 225 (From 300)
	AA Damage = 8 (From 2). DPS = 12 (From 3)
- Restorer
	>BuildTime = 6000 (From 4800)
	Health = 6000 (From 6500)
	Veterancy buff: Threshold = 15 XP (From 18)
#### T4 Air
- Soul Ripper
	>Veterancy adjusted to 80/160/240/320/400 (From 60/120/180/240/300)
### Naval Changes
#### T1 Navy
- Frigate Veterancy threshold = 6 XP (From 8)
- UEF and Cybran Frigate Damage adjusted to be more efficient against Zhtuee
	- UEF
	>	Damage = 85 (From 140)
		RateOfFire = 0.588 (From 0.35)
	- Cybran
	>	Damage = 45 (From 40)
		RateOfFire = 1.36 (From 1.53)
		DPS is unchanged
#### T2 Navy
- Seraphim Destroyer
	>Front Gun DPS = 125 (From 105). Rear Gun DPS = 65 (From 95)
	TurretYawRange = 120 (From 140)
	TurretYawSpeed = 60 (From 90)
	Attack Angle = 70 (From 60)
	It will be slightly less efficient when micromanaged.
#### T3 Navy
- T3 Strategic Missile Submarines
	>Tactical Missile Range = 256 (From 175). This is the same as a TML. This will expand the sniping potential of these units.
	Mass = 9000 (From 10000). This is the same as the Seraphim Battleship
	Nuke inner ring Damage = 22000 (From 25000)
	Nuke outer ring Damage = 3000 (From 500). This means units which escape the inner ring take some real Damage (500 is nothing for Naval units)
- Seraphim T3 Sub
	>SizeY = 0.9 (From 0.8). This is a slightly higher hitbox to ensure Riptides and other surface weapons can hit them normally while they are surfaced.
	Range = 65 (From 70)
	AA DPS = 200 (From 240)
	Health = 4000 (From 4500)
- Cybran and Seraphim Aircraft Carriers can now build Gunships and regular Bombers.
### T4 Navy
- Tempest
	>Torpedoes are now Depth charges, which totally ignore all forms of Torpedo Defence.
	Damage = 350 (From 235)
	RateOfFire = 0.2 (From 0.25)
	DPS = 420 (From 352)
- 2 Atlantis and their equivalent mass cost in T3 Seraphim subs still win convincingly, but the Tempest can now put up a fight even when submerged.