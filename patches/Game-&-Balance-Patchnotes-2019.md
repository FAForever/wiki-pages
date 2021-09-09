---
title: Game & Balance Patchnotes 2019
description: 
published: true
date: 2021-09-09T09:26:41.543Z
tags: 
editor: markdown
dateCreated: 2021-09-09T09:26:41.543Z
---

# Complete changelog of all changes in 2019 {.tabset}


## 3708
### Gameplay
- Added new icons for E storages
- Added missing categories for SACUs
- Made Aeon tmd destroy Billy
- Updated seraphim shader to be more realistic
- Reduced LOD Cutoff from 1000 to 750
- Fixed target bones of Cybran T2 Land HQ
- Changed air staging icon to T1
- Allow to use existing low detail models
- Allow to display the broadsword jammer ring
- Made mass storage targeted after everything else
- Allow to give order to T3 sonars while they are being built
- Allow to build several Eye of Rhianne with a drag build order
- Removed energy from stone reclaim
- Fixed satellite permanently blocking mavor shell against a specific spot
### Bugs
- Fixed Salem floating when killed during landing
- Fixed Hives build effects
- Allow to rebuild ED4 and Aeon air support factory
- Fixed ML exhaust effects playing during construction
- Fixed strats scripts
- Fixed wrecks facing wrong direction
- Fixed a bug allowing air factories to rebuild units on wreck
- Fixed a bug preventing broadsword from draining 25e when built
### Lobby
- Added a curated maps button
- Added an option to fill all lobby slots with AI
### Other
- Updated spelling and punctuation
- Cleaned up UEF units file
- Blacklisted old nomads mod version
- Improved code and mod support
- Removed dummy harms from unit database
### Contributors
speed2
eforgacs
BlackYps
badbwoi
PhilipJFry
KionX
keyser
Exotic-Retard
IceDreamer
Strogo

## 3707
### Bugs
- Revert exe change to stable 3704 exe

## 3706
### Gameplay
- Improved the team kill detection
- Increased the team kill report wait time
- Weapon category fixes
- Mod blacklist update
- Fixed Sera ACU PhaseShield mesh
- Pushed the new (fixed) exe after more testing
### Contributors
speed2
PhilipJFry
keyser
Uveso
FAETHER

## 3705
### Bugs
- Fixed various desync Issues for replays
- Fixed Seraphim Arty Shells not disappearing
- Fixed a bug that gave you free resources by pausing a factory
- Fixed loading AI mod templates being loaded without mods being enabled
- Fixed unfinished unit transfer in full-share games
- Fixed free shield assist bug
### Gameplay
- Improved In Game Cheat Menu <kbd>ALT</kbd> + <kbd>F2</kbd> to support 16 players
- Various AI Improvements
- Changed Novax Background Icon to AIR
- Added a 3 second timer to the teamkill report feature
- Restricted ACU immobilization feature to human players to avoid breaking the AI
- Remove "Assist" command from factory during upgrade
- Added Exit button to the endscreen
- Optimized unitcount for VictoryConditions
- Check for dead status before killing beams
- Improved targeting of torpedo bomber and subs
- Integration of the Supreme Props mod
### Other
- Removed controversial dots from the french translation
- Mod Support
- Enable transport rates to be set vs blueprint
### Contributors
Uveso
Rackover
FAETHER
JaggedAppliance
Strogo
Exotic-Retard
keyser
speed2
svenni_badbwoi

## 3704
### Balance
#### Land
Mongoose
>MaxSpeed: 3.6 → 3.5
MuzzleVelocity: 25 → 30
Muzzle Charge Time: 3 → 2
Gatling Gun Firing Randomness: 0.4 → 0.1
Gatling Gun Damage: 15 → 16

Asylum
>Mass cost: 144 → 220
Energy maintenance: 75 → 30
Overspill modifier: 0.15 → 0.3

Parashield
>Mass cost: 120 → 220
Energy maintenance: 110 → 60
Overspill modifier: 0.15 → 0.3

Athanah
>Mass cost: 540 → 720
Energy cost: 4800 → 6400
Buildtime: 3200 → 3600
Shield Recharge Time: 45 → 40
Energy maintenance: 300 → 175
Overspill modifier: 0.15 → 0.3

Deceiver
>Mass cost: 80 → 160
Energy cost: 800 → 1600
Buildtime: 400 → 800
Energy maintenance: 75 → 40

Wagner
>Torpedo Damage: 6 → 15

Brick
>Torpedo Damage: 4 → 8

Othuum
>Torpedo Damage: 10 → 30

Harbinger
>The Harbinger can once again shoot while reclaiming.

**T1 Mobile Anti-Air**
All Factions
>Mass cost: 50 → 55
Seraphim and UEF
Health: 360 → 310

**T3 Mobile Anti-Air**
Aeon
>Speed: 2.8 → 3.5
Range: 54 → 64

Cybran
>Speed: 2.9 → 3.6
Range: 52 → 62

UEF
>Speed: 2.6 → 3.3
Range: 50 → 60
Damage Radius: 1 → 1.5

Seraphim
>Speed: 2.7 → 3.4
Range: 48 → 58

T2 Engineer
>Speed: 1.7 → 1.9

T3 Engineer
>Speed: 1.5 → 1.9

Scathis
>Mass cost: 110000 → 220000
Energy cost: 2000000 → 4000000
Buildtime: 80000 → 240000
Health: 17500 → 9000
Damage: 3000 → 1600
Damage Radius: 7 → 12
Fire Rate: 0.53 → 0.05
Muzzle Salvo Size: 1 → 20
Maximum Firing Range: 300 → 2000
Minimum Firing Range: 50 → 150

Selen
>The Selen gets some fixes to its stealth/cloak toggle.

#### Air
Renegade
>Mass cost: 240 → 270
Energy cost: 4800 → 5400
Buildtime: 1600 → 1800

Notha
>Bomb Damage: 1175 → 1250

Torpdo Bombers
>Mass cost: 240 → 270
Energy cost: 4800 → 8000
BreakOffDistance: 34 → 45
TurnSpeed: 0.48 → 1
Sonar Radius: 90 → 45

Restorer
>Speed: 8 → 10
Damage: 24 → 28

Wailer and Broadsword
>Will no longer chase air units which fly past

Novax
>Mass cost: 28000 → 36000
Energy cost: 400000 → 512000
Buildtime: 30000 → 44800
Damage: 50 → 60
Radar radius: 150 → 200
Omni radius: 50 → 60
Vision radius: 40 → 60

#### Navy
Bulwark
>Speed: 7 → 5
Turn Rate: 60 → 45
Overspill Damage Modifier: 0.25 → 0.35
UniformScale: 0.09 → 0.135

Beacon
>The torpedo defense of the aeon frigate works more effectively

Siren
>The cybran cruiser now shoots its anti-air missiles in a faster and more effective way.

Exodus
>AoE: 1 → 1.4

**Battleships**
Galaxy
>Health: 47000 → 44500

Summit
>Mass cost: 10500 → 10000
Buildtime: 33000 → 31600

Omen
>Range: 104/114 → 110

Tempest
>Mass cost: 24000 → 22000

Yathsou (T3 submarine)
>WaterVisionRadius: 45 → 55

#### Structures
Tactical Missile Defense
>Buildtime: 600 → 400

T2 Land HQ
>Buildtime: 2600 → 2300

T2 Artillery
>Buildtime: 1200 → 1600
Minimum Range: 5 → 50

Eye of Rhianne
>Energy Storage: 0 → 10000

T2 Static Flak
>Mass cost: 392 → 400
Energy cost: 3920 → 4000
Buildtime: 958 → 540

T2 Radar
>Energy Maintenance: 200 → 150

Airstaging
>Tech level: 2 → 1
Repair Mass cost: 0.5 → 0
Repair Energy cost: 5 → 30
Buildtime: 534 → 450

Nuke Launchers
>BuildPower: 1080 → 1500
Missile Buildtime: 324000 → 450000

**T2 static shields**
Aeon
>Recharge Time: 16 → 24
Buildtime: 701 → 950

UEF
>Recharge Time: 15 → 23
Buildtime: 845 → 1150

Seraphim
>Recharge Time: 17 → 25
Buildtime: 958 → 1250

Cybran
>ED1
Recharge Time: 18 → 20
Buildtime: 600 → 700
Buildpower: 15.53 → 19.2
ED2
Recharge Time: 16 → 22
Buildtime: 466 → 775
Buildpower: 13.34 → 21
ED3
Recharge Time: 18 → 25
Buildtime: 1067 → 2200
Buildpower: 30.575 → 29.3

**T3 static shields**
Cybran
>**ED4**
Recharge Time: 20 → 25
Buildtime: 3667 → 3515
Buildpower: 11.81 → 50.7
**ED5**
Shield Health: 15000 → 16500
Buildtime: 1654 → 7100

UEF
HSD Pulse
>Shield Health: 15000 → 17000
Mass cost: 3000 → 3300
Energy cost: 50000 → 55000

T3 Static Artillery
Emissary (Aeon)
>Buildtime: 30764 → 120000

Hovatham (Seraphim)
>Buildtime: 29792 → 110000

Duke (UEF)
>Buildtime: 30278 → 115000

Disruptor (Cybran)
>Buildtime: 29308 → 105000

#### Game Enders
Mavor
>Buildtime: 99900 → 300000

Paragon
>Buildtime: 125100 → 325000

Salvation
>Buildtime: 90000 → 100000

Yolona Oss
>Buildtime: 125100 → 250000

### ACUs
Regen Aura
>Mass cost: 600 → 700
Energy cost: 4500 → 18000
BuildTime: 600 → 700
Added ACU HP: 1000 → 500
Range: 22 → 30
Max Health Multiplier: 1 → 1.1
Min Regen: 0 → 3

Advanced Regen Aura
>Mass cost: 1500 → 1800
Energy cost: 31250 → 42000
BuildTime: 1250 → 1500
Added ACU HP: 2500 → 1500
Range: 30 → 35
Max Health Multiplier: 1.1 → 1.2
Min Regen: 0 → 15

Aeon Personal Shield
>Shield Recharge time: 90 → 75
Chrono Dampener
Additional Health: 0 → 3000
Stun Time: 3.5s → 2.5s

#### Other
**Projectiles**
Tactical missile
>Mass cost: 180 → 250
ACU Tactical Missile
Mass cost: 180 → 250
Buildtime: 300 → 450

### Contributors
Strogo
JaggedAppliance
Farmsletje
keyser
Petricpwnz
PhilipJFry
speed2
TurinTurambar

## 3703
### Bugs
- Fixed a bug in lobby related to obsolete maps
- Fixed a bug causing weapons to miss the Salem while on land
- Other miscellaneous bug fixes
### Lobby
- Switched the position of the github and close button on the changelog screen
- Mod Support
- Remove hardcoding on nuke weapon for mod support
### Contributors
speed2
Strogo
Exotic-Retard
PhilipJFry
Rackover