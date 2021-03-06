---
title: Game & Balance Patchnotes 2015
description: 
published: true
date: 2021-09-08T14:11:00.051Z
tags: 
editor: markdown
dateCreated: 2021-08-31T15:49:02.077Z
---

# Complete changelog of all changes in 2015 {.tabset}

## 3650
### Balance
- HTML-version of this balance oriented changelog available at: http://content.faforever.com/patchnotes/
#### Seraphim and UEF ACU TML
- Missile hitpoints: 3 hp → 2 hp
- Flying height: now similar to normal TML
- Mass cost: 1000 → 1500
- Minimal range: 5 → 15
- Muzzle velocity to 7
- Only for Seraphim:
- Area of effect: 3 → 2
- The flying arc at close range will now be similar to the UEF ACU TML
#### Cybran TML
- TMDs (except Aeon) will now survive a single cybran tactical missile if they have full HP
- TML friendly Fire
- TML missiles no longer deal friendly fire
#### SACU changes
- Hitbox: lasers can now hit SCUs more reliably
- SCUs now leave a normal wreckage with 81% of their mass value when destroyed
- A RAS preset for UEF, Cybran and Aeon is now available for production from the Quantum Gateways.
#### Aeon SCU
- Reacton Cannon (Gun upgrade)
	> energy cost: 36000 → 46200
  	build time: 5040 → 6048
- Heavy Personal Shield
	> hitpoints: 35000 → 40000
  	mass cost = 1500 → 1800
#### UEF SCU
- Personal Shield Generator
	> HP: 32000 → 26000 HP
- Heavy Plasma Cannon (Gun Upgrade)
	> rate of fire x2.5 → x1.82 (DPS 750 → 546)
  	AOE: 2.5 → 2
- Radar Jammer
	> mass cost: 600 → 300
  	energy cost = 18000 → 8000
- Bubble shield
	> energy cost: 400000 → 360800
#### Cybran SCU
- Nano-Repair System
	> regeneration rate: 400 hp/s → 375 hp/s
  	mass cost: 2000 → 2200
- Focus Convertor (Gun upgrade)
	> adds damage: 250 → 200
- Nanite Missile System (SAM Upgrade)
	> DPS: 272 → 400
- EMP duration for Tech1/Tech2/Tech3/SCU: 4/4/4/0 → 4/3.5/3/0.3
- Stealth upgrade
	> mass cost: 600 → 400
  	energy cost: 18000 → 7400
- Cloak upgrade
	> energy cost: 500000 → 382200
#### Seraphim SCU
- Overcharge: now tracks (like ACU overcharge)
- Overcharge
	> reload time: 5 seconds → 7.5 seconds
		damage: 12000 → 10000
		DPS: 2400 → 1333
- Shield
	> mass cost: 1500 → 1200
  	shield hitpoints: 25000 → 20000
#### Seraphim (Yenzyne)
- Build time: 880 → 1050
- Speed on water: 4.3 → 3
- Aeon (Blaze)
	> Build time: 880 → 1050
		Speed on water: 4.3 → 3
#### UEF (Riptide)
- Build time: 1320 → 1600
- Speed on water: 3.7 → 3
- Mass cost: 362 → 360
- Energy cost: 1980 → 2000
#### Hover flak (Seraphim and Aeon)
- Speed: 3.6 → 3
#### Seraphim Tech 2 bot and Tech 3 Tank Changes
We are carefully toning down both areas while keeping the idea behind it intact. Ilshavoh becomes weaker, and Othuum becomes stronger.
#### Ilshavoh
- Turret turn rate: 180°/s → 70°/s
#### Othuum
- Speed: 2.5 → 2.6
#### Harbinger
Will now take longer to make, making it harder to spam them so fast and allowing opponents slightly more time to bring counters into play.
- Veterancy: 15/30/45/60/75 → 18/36/54/72/90
- Build time: 3600 → 4500
- Can no longer fire while reclaiming
#### Sniper bots (Seraphim and Aeon)
It is annoying when sniper bots lose all their damage while moving and trying to shoot. They will hit more often now, even - though using them stationary will still lead to the best results.
- Firing randomness when moving: 0.8 → 0.5
#### UEF T3MAA
Other faction’s T3 MAA were hitting much better than the UEF one. This change is improving its accuracy to similar levels.
- Slight tracking added with small turn rate (20)
- Muzzle velocity: 100 → 110
#### Navy
##### Summit
Is now more expensive, giving other factions more time to beat them before they are able to gather a critical mass.
- Mass cost: 9000 → 10500
- Energy cost: 54000 → 62000
- Build time: 28800 → 33000
- Area of effect: 3 → 2
##### Aeon Frigates
Will now be more effective vs hover, but not vs ships.
- Hit points: 1800 → 1850
- Damage per shot: 140 → 50
- Reload time: 5 seconds → 1.7 seconds (DPS: 56 → 58)
- MuzzleChargeDelay: 0.5 → 0
- Anti-torpedo weapon reload time: 10 → 12.5
#### Air
##### Strategic bombers (all factions)
Increasing the energy cost of strategic bombers to avoid the ability to rush them so easily.
- Energy cost: 105000 → 144000
- Build time: 8400 → 9600
##### Corsair
Reducing the speed of their projectiles to make them as easy (or hard) to dodge as they were before the range decrease.
- muzzle velocity: 35 → 30
##### Torpedo bombers
We made several adjustments to allow torpedo bombers to actually deliver their torpedoes more often.
- Reload time for all torpedo bombers: 12.5 → 10
- Uosioz (Seraphim Torpedo Bomber)
	>Torpedoes get now dropped in front of the bomber (like all other bombers)
	Range: 42 → 35
	Amount of volleys: 2 → 3
	Now ignores torpedo defense (like all other torpedo bombers)
	Multiple adjustments to torpedoes make them less likely to crash on the ground in shallow water
##### Skimmer (Aeon T2 Torpedo Bomber)
- Depth charges get now dropped in front of the bomber (like all other bombers)
- Range: 42 → 35
- Amount of volleys: 2 → 3
- Multiple adjustments to depth charges make them less likely to crash on the ground in shallow water
##### Solace (Aeon T3 Torpedo Bomber)
- Range: 42 → 32
- Projectile turn rate increased
##### Ahwassa
Added armor to ASF to guard them from the bomb, reducing their damage taken to 10%
- Veterancy: 50/100/150/200/250 → 100/200/300/400/500
- Reload time: 10 → 12
#### Other
##### Quantum Gateway
We are reducing the adjacency bonus for mass fabricators next to Quantum Gates to a more normal level.
- Tech 2 mass fabricator: 2.5% → 0.75%
- Tech 3 mass fabricator: 15% → 2.25%
- Tech 3 power generator: 18.75% → 5%
- Preset names improved
##### T3 Land HQ
- Build time: 9400 → 11000
##### Sonars
##### T2 sonar
-	Mass cost: 120 → 150 (sera stays 180)
-	Energy drain: 100 → 150
-	UEF/Aeon T3 sonar
	>Mass cost: 400 → 1000
	Energy drain: 100 → 250
##### Cybran T3 sonar
- Mass cost: 480 → 1200
- Energy drain: 250 → 400
- Energy/Mass overflow
### Bug Fixes
The bug, that caused resources to disappear when they got shared to several teammates and one of them had full storage does not exist and is a FAF urban legend. If a teammate has full storage, the resources get properly shared to a different teammate instead. It is not needed to use any mods to prevent resources from getting lost or to inform others about this "bug".

No change required


## 3646
Patch 3646 released as a bugfix update to 3644.

A new versioning scheme has been implemented where even-numbered patches are stable and odd numbered versions are beta, starting with beta 3645.

### Bugs
- UEF buildbots no longer explode after being built with ‘no-air’ restriction enabled
- Commanders no longer explode immediately with the ‘no-land’ restriction enabled
- Upgraded hives are no longer invincible
- Destroyer intel works again
- Beam weapons will no longer keep firing their lasers after designated targets have died
- Nukes will always penerate personal shields again
- Paused units which start work on a building will no longer consume resources
- Coop will freeze less often because of an update to the core game. Please keep testing coop and provide feedback!
### Enhancements
- Units with sonar no longer have it enabled while on land
- Added ‘no T3 air’ restriction
- Multiline messages in chat no longer time out faster than non-multine
- New messages no longer ghost previous ones
### Contributors
ckitching
codingsquirrel
bamboofats


## 3644.1
This patch is a minor update for 3644 containing just some UI fixes
### Improvements
- “More unit info” mod has been improved and integrated. It’s on by default, but can be turned off in the “interface” section of game options
- An improved mod manager that allows us to blacklist incompatible mods, which should help with alleviating some problems people have been having with outdated UI/normal mods.
- Old versions of maps are no longer displayed in the map options dialog in the lobby (There’s an option to “Show obsolete”)


## 3644
### Bugs
- AI now works again
- Unpausing engineers works again
- Units currently being built no longer hang around when transferring or reclaiming the factory the were being built in.
- Seraphim units render correctly on medium fidelity
### Enhancements
- Jammer field from crystal now stops working when the crystal is reclaimed
- Jammer crystal reclaim increased to (5000e, 50bt)
### Contributors
Ckitching
Sheeo
CodingSquirrel
Crotalus
Speed2


## 3643
### Bugs
- Fixed issue with half built units from naval factories
- Fixed issue with sometimes being unable to quit the game
- Cybran and UEF buildbots / drones no longer explode with the no air restriction
- Fixed issue with being unable to reclaim mexes that are being upgraded
- Seraphim ACU minimum range for normal gun and OC adjusted to be the same as other ACU’s
- Seraphim destroyer surfaces itself after building again
- Seraphim T2 transport no longer allows active shields on board
- Seraphim ACU restoration field now works for allied units
- Aeon T3 battleship TMD is no longer completely unable to stop TML’s
### Enhancements
- Added ability to see unit data (xp/regen rate) as observer
- Firebeetles can no longer detonate in the air
- Upgrade hotkey now works for T2 naval and air support factories
### Contributors
CodingSquirrel
Crotalus
Gorton
Sheeo
ckitching
ggwpez

## 3642
### Bugs
- Obsidians and Titans die to overcharge again
### Notes
Please remember to update your mods to the latest versions for compatibility with 3641+

## 3641
### Exploits
- Instant crash exploit partially fixed
- No longer possible to give away units in progress of being captured
- No longer possible to bypass unit restrictions with sneaky UI mods
- Fixed being able to remotely destroy wreckage anywhere on the battlefield
### Bugs
#### Hitboxes
- Seraphim sniper bot is able to hit Cybran MML again
- Fixed SCUs not being hit properly by laser weapons
- Fixed units aiming too high on the UEF and Aeon SCUs
- Torpedo/sonar platforms no longer confuse surface weaponry
#### Visual
- Fixed shield structure glows and rotations not playing
- Fixed bug with capture progress bar not being synced if using multiple engineers
- Optimised the range-rings shader to reduce the way FPS falls off a cliff
- Fixed bug with instantly disappearing wrecks due to garbage collection
- Fixed wrong regen values being reported on UI-side
- Disable build effect beams on sinking engineers
- Reload bar refill rate now scales with RateOfFire buffs
- Legacy checkbox UI code working again
- Fixed Engineers spawning the wrong tarmacs when building Seraphim buildings
- Engineering stations no longer exhibit a model bug when rebuilt by an assisting SCU
- Fuel indicator no longer falls off the unit detail window
- Seraphim ACU and SCU no longer show the tac missile counter if they don’t have the upgrade
#### Physics
- Projectiles no longer collide with sinking units
- UEF T3 Transport now leaves wreck in water
- Cybran ACU can now fire the laser when standing in water
- Fixed Seraphim T1 Mobile Artillery not firing at fast targets properly
- Yolona Oss now deals damage to itself
- Flares and depth charges no longer draw in friendly projectiles
- Fix shots sometimes going right through Walled PD
- Increased Aeon T3 Artillery MuzzleVelocity to allow it to fire at its maximum range
#### Other
- T3 Torpedo Bomber can use Attack-Move properly again
- Units with weapon range upgrades now stop at maximum range when using attack-move
- Shield disruptor now works on personal shields
- Fixed wrong consumption when repairing ACU after an upgrade finished
- Support factories no longer lose progress if they are damaged during upgrade
- Aeon SCUs with nano + vet now get correct regen rate
- Fixed share until death bug with dual-given units
- Mini map now remembers whether to show resource icons or not
- Current command mode no longer reset if an engineer dies in the current selection
- Fixed bug with chat messages having wrong recipients in replay
- Seraphim T2 shields can now pause while upgrading to T3
- Fixed RateOfFire buffs not being applied correctly
- SCUs will no longer rebuild buildings they lack to ability to build
- Upgraded buildings rebuilt by assisting SCUs will now cost the correct amount
- FAF no longer blows up if the game hasn’t first been launched to create a profile
### Enhancements
#### Visual
- Scathis now has Amphibious build icon
- Attack and Nuke reticles now scale with impact radius
- TMLs now show the splash damage radius in targeting mode
- Cybran Engineers now display a build beam to clearly show what they’re tasked to
- Cybran factories now have red build beams
- Number of Cybran build bots scale with buildpower of the engineer, to a maximum of 10
- Ping values under “Connectivity” (F11) now update during game stop/stall
- Added Yolona Oss to Mavor/Salvation/Scathis build restriction and renamed it Super-Game-Enders
- ASF effects tweaked for performance (less effects on low fidelity)
- Cybran engineering build bots now crash when their owner dies rather than just vanishing
- Quantum Gateways now can assist each other
- Enhanced Seraphim tarmacs
- Beams originating inside Fog of War will no longer be invisible
- Cybran buildbots are no longer invisible to other players
- Mex, T1 PD, and Radar strategic icons will appear above other building icons when zoomed out
#### UI
- New option: Show reclaim value of wreckage on map by pressing Ctrl-Shift (need to enable it in Options / Interface and restart game)
- Smart selection feature allowing hotkeys to select units by category
- Remove owner-check on text pings so anyone can delete them
- Reclaim/second now shown
- Reclaimed mass now counts towards the score table
- UEF ACU and SCU drones now have an on-drone button to toggle if they are rebuilt at death
- Now possible to pause units to make them pause execution of queued up orders
- Debug window: Searching for units now supports unit name and substrings
- Cybran engineering build bots no longer display the heads-up consumption overlay
- “Commander under attack” now plays for shielded ACUs
- 34 new taunts
- Added a button to unbind key mappings
- Drop shadow for chat messages
- Chat Option: Add background to chat messages when chat window is closed
- Chat Option: Allow chat to timeout normally in the feed after closing window
- Reclaim window merged with main resources UI
#### Other
- Engineering Station units now pause on transfer from one player to another
- Cybran build bots now can assist next build project without respawning
- The least valuable units are destroyed at unit transfer if unitcap is hit
- Absolver shield disrupter now hovers higher, so it’s less likely to hit the floor with the very low mounted gun
- UEF SCU Drone can now capture, the same as the ACU ones
- Tiny changes to make Fatboy/Megalith/Spiderbot weapons symmetrical in behaviour where they should be
- Added templates for all support factories. AI in coop missions is now able to rebuild support factories
- Assist now prioritize building over repair
- Share Until Death is now default
- Mod size reduced by about 30 MB
### Contributors
CodingSquirrel
Crotalus
DukeOfEarl
Eximius
IceDreamer
ResinSmoker
Sheeo
Speed2
anihilnine
bamboofats
ckitching
quark036
shalkya
pip
zock
#### Special Thanks To
Softly
Exotic Retard
Nyx

## 3640
- Adresses an issue that causes the game to crash with core dumps during long games.
- The root cause is an obscure engine bug, that only happens in very narrow circumstances.

## 3639
### General changes
- Christmas presents for reclaim have been removed
- Score viewing:
- Score button no longer exits the game forcefully
- Viewing of score screen when scores were set to off is re-enabled
### Exploit fixes
- Fixed a regression of the free ACU upgrade exploit
### Game improvements
- Cartographic map previews are now being generated even for maps that do not contain colour information for them.
### Bug fixes
- Fixed air wrecks floating mid air on certain maps
- Fixed air wrecks sinking to bottom of water, then jumping back up to surface
- Fixed continental not dying to nukes
- Improved GuardScanRadius:
- Scouts no longer engage at long range, value was set to 10
- Harbinger will automatically engage at range again
- Range tuned down a bit so units will not run off too much
- Fixed Seraphim T3MAA targetbones (Units will no longer aim above it)
- More mod compatibility
- Give Eye of Rihanne restriction a new description
- Fixed hoplite not firing at landed air units
- Added BOMBER category to Ahwassa, Notha
- Added FACTORY category to Megalith, allows queuing of units while being built
- Improve new unit share code (Units dying after being transferred multiple times)
- Fixed sinking wrecks blocking projectiles where the unit used to be
### Lobby changes (Version 2.6.0, also shown in game)
- Fix the rating not showing up for observers
- Font-size for observers reduced
- Chat font-size adjustable from options
- Remove debug messages
- Connection dialog no longer appears below lobby slots
- Fixed issue with players not being removed from slots on disconnect
- Fix integrated replaysync
- 'Set ranked options' button works again
- Tooltips for various buttons fixed and text revised
- More detailed large map preview
- Seraphim icons normalized
- Both players get ready flag cleared on swap
- Removed extra space around Rerun CPU benchmark button
- Made 'Random faction' skin load the chosen faction skin (Before it would always be UEF)
- Fixed a problem preventing player colours from being updated correctly
- Prevented CPU benchmark from running once the game starts
- General performance improvements

Thanks to pip, briang and Alex1911 for translations

### Contributors
- ChrisKitching
- Crotalus
- IceDreamer
- Partytime
- Santa Claus
- Sheeo
- Xinnony

## 3638
- Added christmas presents for reclaim
Big thanks to ozonex for this contribution!

## 3637
### Bug fixes
- Selection Range Overlay works for multiple units again
- Score no longer flickers when watching replays
- Targeting issues, especially related to the seraphim ACU have been adressed
- Compatibility with certain mods restored
- Lobby 2.5b included (Changelog shown in game)
### Notes
- On some maps air wrecks may still appear in midair
- It's still likely that there are incompatibilities with mods. Please let us know your exact setup of the game when reporting issues