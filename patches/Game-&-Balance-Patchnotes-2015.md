---
title: Game & Balance Patchnotes 2015
description: 
published: true
date: 2021-08-31T15:49:02.077Z
tags: 
editor: markdown
dateCreated: 2021-08-31T15:49:02.077Z
---

# Complete changelog of all changes in 2015





## 3646
Patch 3646 released as a bugfix update to 3644.

A new versioning scheme has been implemented where even-numbered patches are stable and odd numbered versions are beta, starting with beta 3645.

### Bugs
UEF buildbots no longer explode after being built with ‘no-air’ restriction enabled
Commanders no longer explode immediately with the ‘no-land’ restriction enabled
Upgraded hives are no longer invincible
Destroyer intel works again
Beam weapons will no longer keep firing their lasers after designated targets have died
Nukes will always penerate personal shields again
Paused units which start work on a building will no longer consume resources
Coop will freeze less often because of an update to the core game. Please keep testing coop and provide feedback!
### Enhancements
Units with sonar no longer have it enabled while on land
Added ‘no T3 air’ restriction
Multiline messages in chat no longer time out faster than non-multine
New messages no longer ghost previous ones
### Contributors
ckitching
codingsquirrel
bamboofats


## 3644.1
This patch is a minor update for 3644 containing just some UI fixes
### Improvements
“More unit info” mod has been improved and integrated. It’s on by default, but can be turned off in the “interface” section of game options
An improved mod manager that allows us to blacklist incompatible mods, which should help with alleviating some problems people have been having with outdated UI/normal mods.
Old versions of maps are no longer displayed in the map options dialog in the lobby (There’s an option to “Show obsolete”)


## 3644
### Bugs
AI now works again
Unpausing engineers works again
Units currently being built no longer hang around when transferring or reclaiming the factory the were being built in.
Seraphim units render correctly on medium fidelity
### Enhancements
Jammer field from crystal now stops working when the crystal is reclaimed
Jammer crystal reclaim increased to (5000e, 50bt)
### Contributors
Ckitching
Sheeo
CodingSquirrel
Crotalus
Speed2


## 3643
### Bugs
Fixed issue with half built units from naval factories
Fixed issue with sometimes being unable to quit the game
Cybran and UEF buildbots / drones no longer explode with the no air restriction
Fixed issue with being unable to reclaim mexes that are being upgraded
Seraphim ACU minimum range for normal gun and OC adjusted to be the same as other ACU’s
Seraphim destroyer surfaces itself after building again
Seraphim T2 transport no longer allows active shields on board
Seraphim ACU restoration field now works for allied units
Aeon T3 battleship TMD is no longer completely unable to stop TML’s
### Enhancements
Added ability to see unit data (xp/regen rate) as observer
Firebeetles can no longer detonate in the air
Upgrade hotkey now works for T2 naval and air support factories
### Contributors
CodingSquirrel
Crotalus
Gorton
Sheeo
ckitching
ggwpez

## 3642
### Bugs
Obsidians and Titans die to overcharge again
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
New option: Show reclaim value of wreckage on map by pressing Ctrl-Shift (need to enable it in Options / Interface and restart game)
Smart selection feature allowing hotkeys to select units by category
Remove owner-check on text pings so anyone can delete them
Reclaim/second now shown
Reclaimed mass now counts towards the score table
UEF ACU and SCU drones now have an on-drone button to toggle if they are rebuilt at death
Now possible to pause units to make them pause execution of queued up orders
Debug window: Searching for units now supports unit name and substrings
Cybran engineering build bots no longer display the heads-up consumption overlay
“Commander under attack” now plays for shielded ACUs
34 new taunts
Added a button to unbind key mappings
Drop shadow for chat messages
Chat Option: Add background to chat messages when chat window is closed
Chat Option: Allow chat to timeout normally in the feed after closing window
Reclaim window merged with main resources UI
#### Other
Engineering Station units now pause on transfer from one player to another
Cybran build bots now can assist next build project without respawning
The least valuable units are destroyed at unit transfer if unitcap is hit
Absolver shield disrupter now hovers higher, so it’s less likely to hit the floor with the very low mounted gun
UEF SCU Drone can now capture, the same as the ACU ones
Tiny changes to make Fatboy/Megalith/Spiderbot weapons symmetrical in behaviour where they should be
Added templates for all support factories. AI in coop missions is now able to rebuild support factories
Assist now prioritize building over repair
Share Until Death is now default
Mod size reduced by about 30 MB
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