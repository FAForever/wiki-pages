---
title: Game & Balance Patchnotes 2016
description: 
published: true
date: 2021-09-08T20:17:33.908Z
tags: 
editor: markdown
dateCreated: 2021-09-02T15:31:25.811Z
---

# Complete changelog of all changes in 2016 {.tabset}


## 3662
### Welcome to the patchnotes for the 3662 patch.
These are the less controversial changes from the finished patch that will get released now. The more controversial changes will be decided after a community vote about the general direction and organization of balancing.

It contains a few bugfixes, some adjustments, additions and improvements to changes of the last patch and new things like the Janus that finally gets some real love.

We wish you good luck and much fun playing with the new patch!

-- The balanceteam

### Land

**Thistle:**
While the bomber changes of the first part can either be beneficial for aeon players and their auroras or not, the t2 nerfs were definitely welcome for them. To even this out a little bit, aeon t1 mma will now not survive a single bomb like the others, and can tank less damage in ground battles, but gets a small compensation in range.
>Health: 360 → 250
Range: 32 → 35

### Air

**Janus:**
The janus bomber already saw significant improvements to its accuracy in the first part of the patch, but it wasn't the end of the process. This change re-works the bomber's firing cycle to ensure a large, even spread. The goal is to make it a more versatile and useful (and being made fun of less) unit, while being different to the other t2 bombers. Where the other t2 bombers are most useful to take out single targets, the role of the janus will lie more in taking out large armies with its AOE.
>Number of Bomb Carpets: 2 → 3
DoTTime (Damage over Time Time, yes that's how it's called): 2.5 → 4
Total Damage (if all bombs hit, for which you need to hit multiple units): 1200 → 1800

**T1 Bombers**
>After observing the bomber changes from the last patch for a while now, and with a greater number of games to judge them, we are able to finetune the new bombers a little bit more.
Mass cost: 120 → 105
Energy cost: 2400 → 2450
Build time: 800 → 700

**Mercy:**
>Mercies shouldn't circle in the air for a long time and run out of fuel before landing anymore.

### Structures

**Aeon TMD:**
The last bugfixes with the Aeon TMD caused it to be even better at stopping missiles than it should have been.
>Rate of fire: 0.32 → 0.25

**T2 Land HQ:**
This is another change where we are able to finetune the numbers as we got more information and feedback about the change since the last patch.
>Mass cost: 1280 → 1170
Energy cost: 11200 → 9100

**Airstaging Platform:**
We decreased the staging 'size' of most aircraft to make docking an easier and quicker process. Air staging platforms are now able to service more higher tech planes at once.

### ACUs
**RAS & ARAS:**
Nerfs to RAS have been discussed for a long time, as the powerful RAS had a couple of negative effects like a much faster jump to T3 air, especially in teamgames. Along with this, RAS SCUs become more expensive in power to make it a bit less easy decision to choose between them or massfabs in the lategame.
>ACU RAS:
>- BuildTime: 1400 → 2800
>- Energy cost: 150000 → 175000
>- Aeon income: 18 mass, 2700 energy → 1700 energy
>- Seraphim income: 16 mass, 3000 energy → 2000 energy
>- UEF income: 14 mass, 3300 energy → 2500 energy
>- Cybran income: 12 mass, 3500 energy → 2700 energy

>SCU RAS:
>- Energy cost: 60000 → 90000

**T2 & T3 Upgrade:**
The tech upgrades get some of their regen back to give ACUs an easy way to regenerate health again, but without making it able to compete with the Nano upgrades. The HP nerf for the T2 ACU gets reduced slightly to reduce the negative effects of it, but is replaced with a small cost increase for the dominant upgrade.

>T2 Upgrade:
>- Health Regeneration: 0 → +10
>- Health: +1500 → +2000
>- Energy cost: 18000 → 21000
>- Mass cost: 720 → 800
>- Build Time: 900 → 1000

>T3 Upgrade:
>- Health Regeneration: 0 → +20

**UEF ACU:**
Several ACU upgrades got reduced cost to allow them to be built earlier and allow for more aggressive ACU action. Especially regarding the nerfs to the T2 upgrade last patch, which reduced the power of both, attacking and defending ACUs, this changes should give players who like to play more aggressive additional tools.
>Nano-Repair System:
>- Energy cost: 44800 → 24000
>- Mass cost: 1200 → 800
>- Build time: 1400 → 800
>- Health: +2000
>- Health Regeneration: +60 → +40

**Seraphim ACU:**
>Nano-Repair System:
>- Energy cost: 90000 → 42000
>- Mass cost: 2000 → 1200
>- Build time: 2800 → 1200
>- Health Regeneration: +75 → +60
>- Health: 6000 → 3000

**Aeon ACU:**
While the first aeon shield was in a good place, the second one was largely unused. The old second shield got removed completely, the old first shield got moved to be now the second shield. The new first shield is a moderately strong and cheap mid-game upgrade.
>Personal Shield Generator:
>- Energy cost: 93750 → 35000
>- Mass cost: 1500 → 1000
>- Build time: 1750 → 1000
>- Shield Health: 29000 → 8000
>- Shield Upkeep: 250 → 150
>- ShieldRechargeTime: 160 → 65
>- ShieldRegenRate: 37 → 30

>Heavy Shield Generator:
>- Energy cost: 1000000 → 93750
>- Mass cost: 4500 → 1500
>- Build time: 3500 → 1750
>- Shield Health: 44000 → 29000
>- Shield Upkeep: 500 → 250
>- ShieldRechargeTime: 200 → 160
>- ShieldRegenRate: 44 → 37

### Bug Fixes
**Flapjack:**
- The Flapjack now does friendly fire damage like all other MMLs.
**Selen:**
- The Selen stealth mechanic has been further improved. Manual toggle shifts selection priority and toggles weapon off now. Motion toggles stealth.
**Aeon naval TMD:**
- Aeon TMD on ships was broken following the previous patch's change to the mechanics of aeon tmd. It should be fixed with this patch.
**Transport drop acceleration:**
- Units will no longer accelerate out of a transport at a target with pre-given orders. This was mainly used when dropping firebeetles to snipe ACUs.

### BlackOps Cloak VFX
The visual effects for cloaked units from the BlackOps mod series have been added to the main game. You can see them at work when your Selen, Mole or Cybran ACU/sACU is cloaked!









## 3660
### Lobby
- Fixed team number switching slots alongside a player
- Added new feature: Kick Reasons. When kicking a player from your lobby, you get a new dialog. You may type in a reason for the kick to notify the player. If you blank it, or leave the message as presented, it will play the old message.
- Fixed Cheat and Build multipliers for AIs showing 1.0 - 1.9 two times
- Fixed rating labels being shown on the minimap when teams are not set to 'Fixed'
- Made it clearer that there's a search filter in the map selection
- Added new unit share conditions for interesting new gameplay. "Full Share" and "Share Until Death" have been joined by "Traitors", which gifts all your units to the player who killed you (Very interesting for FFA games), "Defectors", which is the opposite of Full Share, gifting your units to the highest scoring enemy, and "Civilian Desertion", which gifts your units to a neutral civilian AI, if there is one.
- Improved the tooltip when hovering over your score in the lobby. It will now show a more detailed explanation including your rating deviation
- Fixed the position of the load button in Skirmish mode when launching offline
- Fixed 'Odd vs Even' autoteam button for random faction being the same as the 'Top vs Bottom'
- Fixed new players joining a lobby being unable to see closed slots as being closed
- Fixed auto team settings not working for games with >8 players
- Changed 'Remove Player' to 'Kick Player' for clarity
- Removed nonfunctional 15 and 30 minute no-rush options
- Fixed the game crashing if you attempted to save a new preset
### Coop
- Fixed cinematics playing in coop games
- Improved AI sACU usage
- Fixed objective protection timer
- Fixed information sent to the server for leaderboard purposes
### Gameplay
- Improved Selen toggle. It now behaves with no abilities by default, then when toggled on it hides and shows based on motion as before
- Added dummy weapon to Aeon T2 Transport to allow LABs to be targeted to specific enemies
- Allowed UEF T2 Transport to be given targets while landed on water
- Enabled templates to be created with modded units as the primary unit
- New feature: Delayed Unit Transfer. Hold shift while giving a unit to another player to have it transfer once it finishes the command queue. Partiicularly useful when used with transports
- New feature: You can now cap mass extractors with storage by right-clicking a T2 or T3 mex, or double-shift-right-clicking an upgrading T1 or T2 mex, with an Engineer
- New feature: All ACUs now begin the game pointed towards the centre of the map, making things fairer between north and south on most maps
- Greatly improved teleport visuals for all ACUs and sACUs. Some of these effects are only used in coop
- T2 Artillery should more rarely shoot the floor in front of themselves in odd terrain situations
- Fixed Mermaid being unable to be hit by Neptune and Seraphim Destroyer fire
- Share Until Death now kills your walls as well. All other modes leave them intact
### Bugs
- Fixed units carried by UEF T2 Gunship from firing from inside a carrier
- Fixed Salvation fire rate slowing at max adjacency instead of speeding up
- Fixed units being able to fire at aircraft docked inside carriers, damaging the carrier
- Fixed games not ending properly with AIs
- Fixed Continental not dying to nukes (Again)
- Fixed upgraded structures not being targetable via radar blip
- Fixed shared unit cap taking civilian armies into account when sharing on player death
- Fixed UEF sACU AOE upgrade removal reducing the AOE too far
- Fixed the Spiderbot's laser beam getting stuck on temporarily while the unit executed the death animation
- Fixed the Cybran ACU wandering off long distance when told to assist various buildings with an enemy in the rough vicinity. It will still happen if the unit is much closer, but we should no longer have ACUs walking across the map to go kill themselves on enemy PD
- Fixed Seraphim ACU weapon trail showing when zoomed out
- Fixed Neptune Class weapon getting stuck on during death sequence
- Fixed a large number of projectiles showing the trails through fog of war
- Fixed T3 Mobile Artillery not quite being able to fire to the edge of their radius in some circumstances
- Fixed Siren ground toggle weapon using air weapon target priorities
- Fixed an error in timer resolution in coop mode
### UI
- Fixed UEF Engineering station strategic icon not matching the tech level
- Added missing strategic build icons used in "Bigger" mode
- Fixed displayed abilities on several units
- Fixed unit descriptions on support factories displaying for the wrong ones
- Fixed game quality displaying a corrupted string
- Fixed the scroll button in ACU enhancements freezing the tooltip popup action
- Added mod icon support for various UI elements
- Added build mode support for SCU presets
- Fixed a large number of tooltips not having proper localization
- Added some tooltips to features previously missing them
- Added ability to toggle reclaim labels. Set to Alt-R by default. You may have to bind this manually in the F1 menu.
- Massively improved reclaim label implementation to remove lag when zooming or panning
- Fixed a bug which caused the menu to block the top-left of the screen in ladder games
### Other
- Removed obsolete strategic icons and corrected file paths inside Hotstats module
- Fixed custom FAF player colours conflicting with Steam launcher
- Added German translation to FAF
### Contributors
Crotalus
Exotic-Retard
IceDreamer
Ithilis
Justify87
SlinkingAnt
Speed2
Uveso


## 3658
### Exploits
- Fixed an exploit where Factories and QGates could be made to build units at half-price
### UI
- UEF T2 Gunship will now display the transport icon when selected and hovering the mouse over one of your units
- Fixed typo in Seraphim ACU description
- Hydrocarbon Plants now use the amphibious background in the build menu
- Added rehost functionality to allow easy rehosting with the same game settings
- Enabled tooltips on queuestack, unitstack, and attachedunit entities (Shows tooltip when hovering over just about any unit build queue icon now)
### Lobby
- Fixed observer messages not showing in chat
- AI can now be swapped with real players
- The map previews now show the rating for each player slot currently assigned, and AI Names
- You can now set up your games via the map previews. Click on two players to swap them. Click an empty spot to occupy it.
- Fixed map preview highlights not going away when you exit the player switch drop-down menu in certain ways
- The colour of your rating text now changes colour, getting darker with higher deviation. This should make identifying smurf accounts easier.
- Added new spawn options: Fixed, Random, Optimal Balance, Flexible Balance
- Added message "Player kicked by host" to chat
### Bugs
- Fixed death animations for Cybran T1 mobile artillery and Seraphim T3 mobile artillery
- Fixed soundbank errors in several units
- Fixed torpedoes colliding with missiles and destroying them
- Paragon no longer does low damage to buildings and ACUs
- Fixed Size 4 buildings such as T2 PD and Flak getting a Rate-Of-Fire adjacency buff from PGens
- Fixed bug in AI Engineer behaviour which let to an engine crash
- Fixed templates not working if a unit added by a mod was the first built in the selection used to form the template
- Fixed Selen radar not enabling on build
- Fixed possible desync trigger in AI games
### Gameplay
- The Ythotha now spawns the energy being no matter the method used to kill it
- The Ythotha energy being only spawns for a completed unit
- Added pause button for Nuke Subs and Seraphim Battleship
- Nuke Launched warning now plays for Observers
- Overhauled bomb-drop aim calculation code. It now takes the Y axis into account, and spaces multi-projectile drops properly. In theory, this should be the last word in bombers missing stupidly.
- Improved AI base management in campaign scenarios
- Sub dive toggle now prioritizes dive in mixed groups
### Balance
**Light Assault Bots**
> Build time reduced 140 -> 120
  Cybran T2 Mobile Stealth
  Energy drain increased 25 -> 75
  Fire Beetle
- Now takes two transport slots the same as all other T2 units
- UEF T1 Mobile Artillery
	> Health increased 200 -> 205

**Scathis**
> Mass cost increased 85,000 -> 110,000
	Energy cost increased 1,500,000 -> 2,000,000
	Build time cost increased 31,500 -> 50,000
	Weapon range decreased 330 -> 300

**Selen**
>	Reworked hiding ability into a button toggle:
	When pressed, puts the unit in hide mode. The weapon is disabled, all commands are removed from the unit, and it comes to a halt. Counter-intel Stealth and Cloak come online once it's stopped.
	Selens in hide mode have lowered selection priority: They cannot be selected alongside other units.
	Introduced power drain in hide mode - 5 energy/second

**Mobile T1 AA**
>	Mass cost increased 28 -> 55
	Energy cost increased 140 -> 275
	Build time increased 140 -> 220
  
> UEF
	Health increased 200 -> 360
	Speed increased 2.8 -> 3.3
	Damage increased 8 -> 16

> Cybran	
	Health increased 130 -> 260
	Damage increased 8 -> 16
	Removed AA/AG toggle. The weapon will now auto-toggle between modes depending on what is in range, prioritising AA.

> Aeon
	>Health increased 200 -> 360
	Speed decreased 3 -> 2.8
	Damage increased 5 -> 10

> Seraphim
	>Health increased 200 -> 360
	Speed increased 2.5 -> 3.4
	Damage increased 4 -> 8

**T2 Hover Tanks**
>	UEF
		- Increased speed on water 3 -> 3.3

> Aeon
		- Increased speed on water 3 -> 3.5

>	Seraphim
		- Increased speed on water 3 -> 3.5

**T2 Flak**
>	UEF
	- Increased speed 2.8 -> 3

> Cybran
		- Decreased speed 2.9 -> 2.7

>	Aeon
		- Increased speed on water 3 -> 3.5
		-	Decreased speed on land 3 -> 2.6

> Seraphim
		- Increased speed on water 3 -> 3.5
		-	Decreased speed on land 3 -> 2.5

**Engineers**
- T2 Engineers
>	Decreased energy cost 700 -> 650
	Decreased mass cost 140 -> 130
	Decreased build time 700 -> 650
	>-	UEF
		-Increased health 300 -> 400
	>- Cybran
		Increased health 290 -> 390
	>-	Aeon
		Increased health 240 -> 340
	>- Seraphim
		Increased health 250 -> 350

- T3 Engineers
>	Decreased energy cost 2200 -> 1560
	Decreased mass cost 440 -> 312
	Decreased build time 2200 -> 1560
	>- UEF
		Increased health 600 -> 800
	>- Cybran
		Increased health 540 -> 740
	>- Aeon
		Increased health 480 -> 680
		Decreased build rate 40 -> 30
	>- Seraphim
		Increased health 500 -> 700
		Decreased build rate 40 -> 30

**T1 Bombers**
>- Increased energy cost 2250- 2400
>- Increased mass cost 80 -> 120
>- Increased build time 500 -> 800
>- Removed Radar ability
>- Increased RateOfFire 0.25 -> 0.2

> **Cybran and UEF**
>- Decreased FiringRandomness 3 -> 0
	
> **Flight Parameters**
>- Decreased BreakOffDistance 30 -> 24
>- Increased CombatTurnSpeed 0.75 -> 1.5
>- Increased KTurn 0.7 -> 0.8
>- Decreased StartTurnDistance 5 -> 1.4
>- Increased TurnSpeed 0.75 -> 1.5
>- Decreased RandomBreakOffDistanceMult 1.5 -> 1

**Ahwasssa**
>	Decreased StartTurnDistance 15 -> 1
	Increased TurnSpeed 0.65 -> 0.9

**Cybran T1 Frigate**
>- Decreased AA MuzzleVelocity 60 -> 45
>- Removed AA projectile tracking
>- Removed AA projectile TurnRate

**Cybran T2 Destroyer**
>	Decreased AA damage 10 -> 5

**Cybran T1 Static AA**
>	Fixed bug preventing it from shooting scouts on certain approaches

**Tactical Missile Launchers**
> **UEF**
>- Decreased clip size 12 -> 6

> **Cybran**
>- Decreased clip size 10 -> 4

> **Aeon**
>- Decreased clip size 16 -> 6

> **Seraphim**
>- Decreased clip size 20 -> 8

**T2 Static Artillery**
> Decreased build time 1608 -> 1200

**Aeon TMD**
>	Adapted weapon collision to prevent flare failing to intercept missiles flying near the top of the range sphere

**Factory Cost Changes**
> **T2 Land HQs**
>- Increased mass cost 800 -> 1520
>- Increased energy cost 7200 -> 13300
>- Increased build time 1600 -> 2600

> **T3 Land HQs (Price increase due to the T2 cost increase)**
>- Increased mass cost 4540 -> 4920
>- Increased energy cost 41100 -> 43900

> **T2 Land Support Factories**
>- Increased mass cost 300 -> 340
>- Increased build time 1300 -> 1600

> **T3 Land Support Factories**
>- Increased mass cost 750 -> 860
>- Increased build time 3000 -> 4000

> **T2 Navy HQs**
>- Increased mass cost 1370 -> 1700
>- Increased energy cost 6600 -> 8500
>- Increased build time 2400 -> 3600
>- Increased build power 60 -> 90

> **T3 Navy HQs**
>- Increased mass cost 5450 -> 7500
>- Increased energy cost 24472 -> 35000
>- Increased build time 8200 -> 11250
>- Increased build power 120 -> 150

> **T2 Navy Support Factories**
>- Increased mass cost 500 -> 800
>- Increased energy cost 2500 -> 4000
>- Increased build time 2000 -> 3000
>- Increased build power 60 -> 90

> **T3 Navy Support Factories**
>- Increased mass cost 800 -> 1100
>- Increased energy cost 3429 -> 5500
>- Decreased build time 4000 -> 3500
>- Increased build power 120 -> 150

**Cybran T3 MAA**
> Removed AA/AG toggle. The weapon will now auto-toggle between modes depending on what is in range, prioritising AA

**Cybran T2 Cruiser**
>	Removed AA/AG toggle. The weapon will now auto-toggle between modes depending on what is in range, prioritising AA
	Decreased AG toggle weapon damage 60 -> 40
	Increased AG toggle weapon rate of fire 0.5 -> 1
	Decreased AG toggle weapon rockets per salvo 6 -> 3
	Increased AG toggle weapon FiringRandomness 0.3 -> 0.9

**All ACUs**
> **T2 Upgrade**
	- Removed health regen bonus
	- Decreased health increase 3000 -> 1500 (UEF, Aeon, Seraphim) 3500 -> 2000 (Cybran)
> **T3 Upgrade**
	- Removed health regen bonus
	- Decreased health increase to respect the T2 adjustment
	- Decreased buildpower 126 -> 100

> **Aeon ACU**
>- Enhanced Sensor System Upgrade
>- Decreased mass cost 400 -> 350
>- Decreased energy cost 10000 -> 5000
>- Decreased omni radius 100 -> 80
>- Increased visual radius 50 -> 80

> **Cybran ACU**
>- Decreased health regen 17 -> 15
>- Changed regen per veterancy level 21/24/27/30/33 -> 19/23/27/31/35
>- Personal Stealth System Upgrade
>- Decreased energy cost 5250 -> 5000
>- Increased build time 350 -> 500

### Contributors
Brutus5000
ckitching
Crotalus
Downlord
Exotic_Retard
IceDreamer
JaggedAppliance
JJ173
Justify87
Shalkya
Sheeo
Speed2
Uveso
ZockyZock




## 3656
### Server Compatibility
- Made teamkill reporting work alongside the server update V0.3
- Change the format of unit statistics to enable server harvesting for achievements
### Contributors
Crotalus
Downlord



## 3654
### Reverted
- The change in 3652 which refreshed intel for a blip on upgrade had unintentional free intel side effects we have been unable to solve. As such, that change has been reversed
### UI
- Fixed reductions in MaxHealth resulting in UI displaying 10000/9000 HP
- Added slot numbers in the lobby
- Toggling the shield on a selection of units with a mix of active and inactive shields now toggles them ON instead of OFF
- The tooltip now shows for ACU and sACU upgrades that are not yet buildable
### Bugs
- Reclaiming something under construction won’t stall out any more
- Drones no longer display build-range rings
- UEF Drones no longer leave wrecks
- Fixed Seraphim Regen Aura level two not applying to newly built units
- Fixed Billy using the full ‘Ignore shields’ nuke code
- Fixed a typo in the Seraphim ACU which prevented the Gun upgrade from being completed
- Fixed Chrono Dampener getting jammed by Overcharge
- Fixed FX bug on Deceiver
### Other
- Removed unused code
### Contributors
Crotalus
duk3luk3
IceDreamer
Sheeo
Softly
Uveso


## 3652
### Lobby
-Name filter when selecting map
-Prevent host from changing player teams while he is ready
-Game quality in lobby now visible again
-Reduced autobalance random variation to get team setups with better overall quality
- Default to score off
- Stopped the map filter preventing the map selected in prefs from prior games from showing
- Tiny fix to flag layout
- Fixed descriptions for the AIx Omni option and Lobby Preset button
### UI
- Introduced Russian translations of many FAF additions to the game (Exotic_Retard and PerfectWay)
- Translate some FAF additions to Italian
- New keybindable action: 'soft_stop'
- Soft-stop will cancel all orders of a factory except their current one, if you soft-stop a factory with only one order it will get cleared
- Hold down Alt when giving a factory order to soft stop factory before issuing next order
- Multi-upgrade: Added UI support to upgrade structures several levels at once (i.e: cybran shields, hives, mexes, factories etc)
- Auto-overcharge: It's now possible to let overcharge fire automatically whenever you have the required power
- Order repair on a wreck to rebuild it if possible by some of the selected engineers. Those not able to rebuild the wreck will assist after the build starts.
- Units explicitly repairing (not assisting) a structure that dies will automatically try to rebuild it
- Refactor the income economy overlay not to show reclaim values appearing in the generated income column and do correct rounding of the numbers.
- Fixed bug with unit regen debuff not being visible in UI
- Fixed bug with buildpower not visible in unitview
- Score display in the top-right no longer counts reclaim into the Mass/Energy income shown in observer mode
- Allow Hotbuild to find Support Factories
- Allow the UI code to search active mods for unit icons. Mods will have to have the icons in the right place (/modname/icons/units/xxx_icon.dds). Confirmed working for Total Mayhem at least, and probably many more.
- Show ren_networkstats in Connectivity Screen (F11)
- Show name of the one resuming a paused game
- Reverted the change to T1 PD icons from 3641, so now they don't give free intel on mouse-over when trying to fake PD-wall with all-wall radar ghosts.
- Render build range of engineers using native overlay system instead of decal hack
- Enabled Pause button in replays
- In Units Manager, added more preset restrictions (e.g. No T1 spam, No Snipes, No TMLs)
- In Units Manager, separated some existing preset restrictions (e.g. game-enders, nukes) for better selection
- In Units Manager, added custom restrictions for all FA units
- In Units Manager, added custom restrictions for modded units when mods are activated
- In Units Manager, added mechanism for restricting units using preset restrictions and/or custom restrictions
- In Units Manager, added grouping of units based on faction, type, purpose, and tech level
- In Units Manager, added detailed tooltips with stats for weapons, defense, and eco for all units
- In Units Manager, added visualization of modded units using small purple icon with letter M
- In Units Manager, improved description of preset restrictions
- In Mods Manager, added filters for UI/Game/Disabled mods
- In Mods Manager, improved sorting mods by their activation status and names
- In Mods Manager, added cleanup of mod names with mismatching mod versions
- In Mods Manager, added mod versions next to mod names
- Added pre-loading and caching of blueprints for usage in the Units Manager
### Gameplay
- Teamkill is now detected and a player can make an explicit report
- Air units are now able to fire at water-landed transports
- Hoplite now calculate their aim correctly when firing at a fleeing target
- Slightly increased unit size(not hitbox) of T3 sniper bots, Othuum and Rhino to alleviate their weapon's ground-hitting ability
- Seraphim Experimental Nuke now deals damage to itself
- Cybran drones no longer leave wreckage when killed
- Defense structures now start rotated at their nearest enemy when built, if no enemies found they default at middle of map
- Removed friendly fire on Atlantis AA
- Locations of enemy civilian structures are now revealed at start of the game (lobby option)
- Navy units now should respect their max-range better when having move-attack order
- Set GuardReturnRadius to 3 as default, will make guarding / patrolling / move-attacking units less prone to move off their designated mission while hunting something
- Units moving on sea bottom now leave tread marks - they disappear faster though
- Re-enabled death animation on non-naval units
- Seraphim GW now uses all its 3 exits
- Spread attack targets are now spread more uniformly among all units during the initial attack orders, further ones are random.
- Diplomacy now allowed in Coop mode
- Allow Fatboy, Atlantis, Tempest and Czar to fire while building units
- Beam weapons now kill missiles they impact instead of wasting DPS for several ticks
- Aeon ACU upgrade "Chrono Dampener" won't stun allied units any more. Additionally, it will fire at predetermined ticks so the effects of multiple acu's do not stack.
- Increased TMD range by 1 and ROF by 0.2s to prevent a single TML killing a single TMD by using ground-fire to impact before the second TMD shot fires.
- Fixed Cybran T3 MAA doing friendly damage on 1 of its 2 AA weapons
- Fixed Cybran T3 MAA hitbox/bones making lots of units miss
- Fixed Seraphim T1 sub not being hit by torpedoes 80% of the time while surfaced.
- Enemy civilians are now colored in a unique red color
- Fixed bomb drop code and enabled it for Janus, and UEF/Cybran T1 Bombers to attempt improvement to bomb drop characteristics
- Allowed Aeon Aircraft Carrier to build Bombers and Gunships, same as the others.
- Fixed restriction system on Sim side such that it cannot be compromised by UI mods
- Fixed restriction system that prevented removing restrictions on already restricted units in scenario scripts
### Bugs
- Fixed free mass exploit with Megalith eggs
- Fixed bug with Cybran SCUs getting EMP for free
- Fixed bug with units getting invincible after a visit to their nearest carrier
- Fixed bug with not able to target a blip of a given / upgraded structure
- Fixed bug which caused silo missiles to disappear at launch stage
- Fixed bug with water sounds not playing while a unit was submerged
- Fixed bug with omni buff instead getting radius of radar
- Fatboy and Cybran cruisers shouldn't engage enemies way outside their range anymore
- Fixed bug with commander not always being selected at start
- Fixed wrecks not giving resources in Coop mode
- Fixed Coop missions getting stuck at completion
- Added missing Seraphim objective icons
- Shields now overkill damage correctly based on their type
- Fixed nukes overkilling bubble shield base structure when out of range and shield up
- Fixed Continental taking damage from AOE when it has the shield up
- Fixed regen buffs from different sources not stacking properly. This should mean every possible interaction between veterancy, upgrades, and the Seraphim Regen Aura field all play nice
- Fixed Underwater Vision not being initialized on unit completion
- Fixed Engineers not properly reclaiming the target of an assisted, then stopped, Engineer
- Fixed UEF Drones being untargetable by Interceptors
- Fixed UEF Drone collision detection, making it much easier for ground-based AA to hit them
- Fixed UEF AI unit templates in coop mode
- Fixed an exploit with being able to upgrade restricted enhancements
- Fixed a rare bug with builders getting near zero HP after a naval building gets destroyed the same tick as it finishes.
- Fixed shields sometimes not turning off due to lack of Energy
- Fixed buffs from enhancements being applied too often after unit transfer
- Fixed submersible naval units leaving full reclaim mass
- Nuclear explosions now behave predictably, always bypassing/ignoring bubble shielding
### Performance
- Optimization of score accumulation
- Tweaks to hive build effects to reduce performance impact
- Cleanup of enhancement sync code to make it faster and more secure
- Entities now re-use repeated sound FX instead of creating new ones every time
- Reduce load on render thread
- No net_lag in single-player to increase UI response speed
### Other
- Added game-side support for future achievement system
- Tech-level filter in debug window now works as intended
- Log-spam from various known events heavily reduced
- Lots of work adapting and improving AI behavior for coop gameplay (speed2)
- Scale aeon build effects according to build progress
- Show wreckage debris in reclaim beam
### Contributors
Sheeo
IceDreamer
Crotalus
speed2
Exotic_Retard
duk3luk3
HUSSAR
Downlord
madformuse
quark036
CodingSquirrel
PerfectWay