---
title: Game & Balance Patchnotes 2017
description: 
published: true
date: 2021-09-08T20:50:42.182Z
tags: 
editor: markdown
dateCreated: 2021-09-08T20:45:18.342Z
---

# Complete changelog of all changes in 2016 {.tabset}








## 3684
### Other
- Fixed a typo that is probably responcible for the rare sim freeze bug that has been happening since 3680
- Fixed a typo which broke some FX on the Ythotha
### Gameplay(Balance)
**Janus**
>- Corrected miscalculation in total damage. Fire pulse count decreased 15 → 10

**Reclaim**
>- Time taken to reclaim unit wrecks doubled. Props and living units unaffected
>- Increased value of split trees by 25% to compensate for it taking longer to reclaim them

**T1 Land/Air Factory + T2 Land/Air Support**
> Aeon Health increased 3100 → 3200
> Cybran
	>- Health increased 2500 → 2750
	>- Regen increased 6 → 9

**T1 Naval Factory**
>Aeon Health increased 3100 → 3700
>UEF Health increased 4000 → 4500
>Seraphim Health increased 3500 → 4000
>Cybran
>- Health increased 2500 → 3200
Regen increased 6 → 10
T2 Land/Air HQ + T3 Land/Air Support
Aeon Health increased 6200 → 6400
Cybran Health increased 5000 → 5500
T2 Naval Support
Aeon Health increased 5000 → 6400
UEF Health increased 6500 → 8000
Seraphim Health increased 5500 → 7000
Cybran
Health increased 4000 → 5500
Regen increased 12 → 20
T2 Naval HQ
Aeon Health increased 10000 → 12800
UEF Health increased 13000 → 16000
Seraphim Health increased 11000 → 14000
Cybran
Health increased 8000 → 11000
Regen increased 30 → 40
T3 Land/Air HQ
Aeon Health increased 12400 → 12800
Cybran Health increased 10000 → 11000
T3 Naval Support
Aeon Health decreased 13000 → 12800
UEF Health decreased 17000 → 16000
Cybran Regen increased 30 → 40
Seraphim Health decreased 15000 → 14000
T3 Naval HQ
Aeon Health increased 20000 → 21000
Cybran Health increased 16000 → 17000
Seraphim Health increased 22000 → 23000
Hydrocarbon
Cybran Regen decreased 6 → 5
Mass Storage
Cybran Regen decreased 4 → 3
Seraphim ACU Second Gun Upgrade
Mass cost increased 3500 → 4800
Energy cost decreased 300000 → 270000
Damage bonus increased 400 → 750
Damage radius increased 2 → 2.
Veterancy
Increased veterancy regen values for Experimentals across the board
Fixed longstanding bug causing Veterancy to heal far too much health
Introduced new veterancy mechanics to allow fine control over instant heal effect
Old system: 1st Vet = Heal for max HP * 0.1. 2nd Vet = Heal for max HP * 0.2 ... etc
New system: Unchanged for ACUs. Other units heal max HP * 0.1 each time
MMLs
Aeon
Missile HP increased 1 → 2
Missile motion parameters changed to be slower
UEF
Now fires 3 missiles in a salvo, 1.8 seconds apart, every 10 seconds
Effective DPS increased 60 → 90
Seraphim
Missile motion parameters changed to be faster
MuzzleVelocity increased 3 → 4
RateOfFire increased 0.15 → 0.1666. Firing cycle from 1 shot every 6.7s to one shot every 6 seconds
Effective DPS increased 60.4 → 67.5
Sparky
Reintroduced Energy drain of 15 for running Jammer
Novax Satellite
Crash damage decreased 3000 → 1000
UEF T1 Bomber
Bomb DoT Duration increased 1.5 → 4.2. Damage remains the same, just more spread out in time T2 Static Flak
Aeon MuzzleVelocity increased 30 → 35
UEF MuzzleVelocity increased 25 → 35
Cybran MuzzleVelocity increased 20 → 30
Seraphim
MuzzleVelocity increased 25 → 35
AOE increased 3 → 4
FiringRandomness decreased 2.5 → 2
Crab Eggs
Corrected T3 Engineer Egg to match new values for the main unit from previous patches
BuildTime of all eggs reduced by 50%
Megalith
BuildRate decreased 180 → 45
Combined with egg changes, effectively doubles egg build time, and reduces Megalith reclaim rate to 25% of before
Aurora
FiringRandomnessWhileMoving increased 0.1 → 0.3
Harbinger
BuildRate increased 3 → 5
Aeon ACU
First Shield upgrade recharge time increased 65 → 90
Contributors
Crotalus
IceDreamer
JaggedAppliance
MrNukealizer
PerticPwnz

## 3682
### Bugs
- Fixed a typo that is probably responsible for the rare sim freeze bug that has been happening since 3680
### Gameplay
- Fixed several unit restriction settings restricting units that did not make sense
- Hotbuild power generators key now also cycles through to power storage
- Fixed hotbuild select nearest scout not selecting the nearest one, and not selecting spy planes
### UI
- Added a new button to the F10/Main Options dropdown ingame to access the key bindings popup directly in case you remapped F1
- Updated the wording of several loading tips
### Contributors
CookieNoob
Fast-Thick-Pants
Hussar
IceDreamer
PhilipJFry
Speed2

Special Thanks
MrNukealizer
## 3681
### Bugs
- Fixed always loading the default or last map, which broke COOP
- Fixed a typo which broke All Faction Templates
### Other
- Reverted the changes to lobby text showing faction colours due to community feedback. This feature will reappear as an option in the future.
### Contributors
Icedreamer
MrNukealizer
## 3680
### Gameplay
- New feature: Dead air unit wrecks now bounce off shields. The amount of bounce depends on the unit's momentum and angle of approach. Some of the crash damage is transferred to the shield. Unit wrecks can only bounce once. Doesn't affect Experimentals.
- Allow units in a transport which is shot down to leave wrecks at the crash site
- Allow the Novax to build a new Satellite if the old one dies. This can only happen if it is impacted by a Nuke or ctrl-k'ed
- Introduced code to slightly improve the way Tempest and Atlantis behave, particularly in being able to fire, in shallow waters
- Enabled fire states on TML and SML structures and units. This allows you to command multiple launchers to fire simultaneously at multiple targets
- Increased reconnect timeout from 45 to 90 seconds to better allow router reboots
- HARMS now sinks to a greater depth on completion
- Assist-Mex-To-Cap is now on by default

### Bugs Fixes
- Fixed ACU reclaiming while shooting
- Fixed ACU building while shooting
- Fixed Auto-Overcharge stopping working randomly until toggled
- Fixed Auto-Overcharge firing while building
- Fixed SML hitboxes so some are no longer immune to T2 PGen explosions
- Increased Beetle hitbox size and declared new targetbones to stop everything missing it if it strafes
- Fixed two move-while-building exploits
- Gave Force damage to several AOE weapons so they now kill trees properly
- Fixed ambient movement sounds continuing to play for sinking units
- Fixed air units occasionally granting infinite intel at the crash site
- Fixed unit restrictions not updating correctly when HQs are transferred between players
- Fixed ancient bug which didn't deselect factory units properly, leading to accidental pausing of those units
- Fixed the 'Select Onscreen Land/Air/Navy' hotkey also selecting the factories of that type
- Fixed the Mex Cap feature somehow allowing storage to be built inside units built via upgrade
- Fixed bug where the Aeon shields didn't visually rotate properly
- Fixed adjacency visual effect being placed on the water surface when dealing with underwater mexes or hydros
- Fixed ships sometimes sinking through land
- Attempted a safety check to try and fix Aeon T2 shields getting the shield up despite having been destroyed in construction
- Fixed cluster bombers (Janus etc) gaining a new target halfway through a bombing run

### Lobby
- Fixed 'Random' faction using 'Random - Unbalanced' tooltip
- Allow filtering of 13-16 player maps in map selection
- Fixed 'Autoteams: Manual' resulting in all players being allied
- Fixed autobalance functions crashing when used with uneven team numbers
- Improved the ping/cpu display column, splitting it into two. The ping column only shows when it matters.
- Observers are now kicked before checking connection issues when Allow Observers is false. This means they will no longer stall game launch if one or more have a connection issue.
- Improved performance of Unit Manager, as well as layout, tooltips, and some icons
- Fixed faction selector panel not updating properly
- Removed ability for people to spam the lobby chat with the observer button
- Fixed several cases of CPU rating not being broadcast properly
- Added a 'New Message' button to the lobby which jumps to bottom of chat, and disabled the chat auto-hopping to bottom with every new message, if you have scrolled up
- Fixed the number of active mods not updating for non-hosts when they enable/disable a UI mod
- Fixed double clicking various elements in the lobby bypassing various restrictions
- Added a tooltip to the map preview top right

### UI
- Added new option to change the minimum reclaim label size shown in the overlay
- Enabled the STOP button for shields which can be upgraded
- Removed the tech level tick from Mass Storage strategic icon to match energy storage
- Fixed hotkey labels not moving properly when scrolling the build menu
- Pause button is now visible and active in the Enhancements and Selection tabs
- Allowed multiple nuke pings to display simultaneously
- Corrected several incorrect tooltips on SCUs
- You can now search for bindings or actions in the F1 key binding menu
- The buttons for adding and removing key bindings have been moved to be on the same line as the binding
- Added Hotbuild Preset button. This will automatically set your bindings to the Hotbuild Preset. There is also a button to set back to Default Preset.
- Fixed Hotbuild conflicting with other binds
- Fixed keys being able to be bound to two actions at once
- Keybinding UI will now auto-assign shift-bindings to match a newly bound action, if the shift-bind is not in use
- Fixed hotbuild labels in the construction UI not updating when they are re-assigned
- Lots of text around the UI will now change colour to reflect your faction skin again
- New Feature: Helpful tips and tricks will now show briefly on the loading screen
- Fixed language changes not always taking effect on game restart properly
- Removed nonfunctional language change hotloader
- Fixed buttons with a countdown not counting down

### Balance
- Increased Auto-Overcharge rate of fire from 3.3s to 5s

### Other
- Added some mods to blacklist
- Allowed hooking of schook files to help future patch mechanism
- Allow hot-reloading of UI files with EnableDiskWatch
- Uncapped max framerate for people with monitor refresh rates >100
- Fixed desync in COOP
- Allow Salem death sound on land in COOP
- Allowed restricted units to be captured in COOP
- Added a new objective type to COOP
- Added a new icon for the Kill or Capture objective in COOP
- Objective tooltip in COOP now coloured according to faction skin
- Various other extensive COOP-only changes
- Added CZ translation file
- Added PL translation file
- Improved RU translations
- Improved SP translations

### Contributors
CookieNoob
Crotalus
Duk3Luk3
Exotic-Retard
Hussar
IceDreamer
IDragonfire
PhilipJFry
Speed2
TheKeyBlue
ThomasHiatt
Uveso

Special Thanks
Jackherer (French translations)
UnicornNoob (Russian translations)

## 3677
### Bugs
- Added code to log and potentially fix an issue with army index assignment which may be causing rating irregularities
### Contributors
duk3luk3

## 3676
### Welcome to the patchnotes for the 3676 patch.
The focus of this patch is working on improving the implementation of the previous patch. Cybran regen is improved, Seraphim get a buff to their hps, as well as some smaller changes and fixes.

We wish you good luck and much fun playing with the new patch!

-- The Balance Team

### Air
**Janus:**
Janus gets a slight buff again to improve it slightly vs units.
>- Initial Damage: 15 → 20
>- Total Impact Damage: 300 → 400
>- Total Overall Damage: 1500 → 1600
### Structures
**T3 Naval Support Factories:**
T3 naval support facs were found to be too vulnerable considering the cost of the units being constructed within them so we have reduced their hp nerf.
>- UEF HP: 13000 → 17000
>- Seraphim HP: 10000 → 15000
>- Aeon HP: 10000 → 13000
>- Cybran HP: 8000 → 11000
>- Cybran HP Regeneration: 15 → 30

**T2 UEF Naval Support Factory:**
This is a correction of the UEF T2 naval support factory which was missed in testing before the previous balance patch.
>- HP: 6000 → 6500

**Mass Storages:**
Mass storage hp has been given some hp back, so that it is more in line with their cost.
>- UEF HP: 760 → 1200
>- Seraphim HP: 600 → 1100
>- Aeon HP: 600 → 1000
>- Cybran HP: 500 → 800
>- Cybran HP Regeneration: 1 → 4

### Seraphim Structures
In the HP nerf patch Seraphim were given the same HP as Aeon. However we now decided to buff their HP so that they have more than Aeon, but still less than UEF. Seraphim have less unit choices and are not one of the stongest factions so some buffs are warranted and this also increases faction diversity.

**Seraphim T1 Buildings:**
>- Air/Land/Naval Factory HP: 3100 → 3500
>- Power Generator HP: 600 → 650
>- Hydrocarbon Power Plant HP: 1600 → 1700
>- Mass Extractor HP: 600 → 650
>- Wall Segment HP: 2000 → 2500

**Seraphim T2 Buildings:**
>- Air/Land Factory HQ HP: 6200 → 7000
>- Naval Factory HQ HP: 10000 → 11000
>- Air/Land Support Factory HP: 3100 → 3500
>- Naval Support Factory HP: 5000 → 5500
>- Power Generator/Mass Extractor HP: 1900 → 2000

**Seraphim T3 Buildings:**
>- Air/Land Factory HQ HP: 12400 → 14000
>- Naval Factory HQ HP: 20000 → 22000
>- Air/Land Support Factory HP: 6200 → 7000
>- Naval Support Factory HP: 10000 → 15000
>- Power Generator/Mass Extractor HP: 6200 → 7000

### Cybran Structure Regeneration
The initial Cybran regen values were found to be too low to be a relevant feature, so we have increased Cybran regen across the board.

**Cybran T1 Buildings:**
>- Air/Land/Naval Factory: 3 → 6
>- Power Generator/Mass Extractor: 1 → 2
>- Hydrocarbon Power Plant: 1 → 6
>- Wall Segment: 3 → 6

**Cybran T2 Buildings:**
>- Air/Land Factory HQ Regen: 10 → 20
>- Naval Factory HQ Regen: 15 → 30
>- Air/Land Support Factory Regen: 3 → 6
>- Naval Factory Regen: 6 → 12
>- Power Generator/Mass Extractor Regen: 3 → 6

**Cybran T3 Buildings:**
>- Land Factory HQ Regen: 20 → 40
>- Air Factory HQ Regen: 20 → 40
>- Naval Factory HQ Regen: 30 → 60
>- Air/Land Support Factory Regen: 10 → 20
>- Naval Factory Regen: 15 → 30
>- Power Generator/Mass Extractor Regen: 10 → 20

### Miscellaneous
**Wall segments:**
Destroying Wall Segments now grants 0.1 veterancy instead of 1. Killing walls for vet was an abuse which became more prevalent since the wall hp nerf.

**T2 Radar:**
We have reduced the maintenance cost of T2 radars to encourage this intel option in the midgame.

>- T2 Radar energy Mainentance cost: 250 → 200
## 3675
### Bugs
- Fixed a small bug that led to the game not ending properly when a player died with Share Unit Cap turned on

## 3674
### Welcome to the patchnotes for the 3674.
This patch contains the HP changes that have been in testing and discussion for a long time, and some Ythotha buffs on top. As always, you can post your feedback and opinion on the forums.

We wish you good luck and much fun playing with the new patch!

-- The balance team


### Land
**Ythotha:**
A buff to the Ythotha has been long planned and wished, but buffing it in a way that makes the unit more dynamic and interesting turned out to be difficult. We have decided to improve it by making it more nimble and also allowing it to shoot 45 degrees backwards so that it can be microed to a much greater degree. It also gets a slight range increase to help with this goal. We will closely observe if this new microability in certain situations gives the Ythotha the power it should have, or if further adjustments are needed.
>- TurnRate: 40 → 60
>- EyeWeapon Range: 45 → 47
>- LeftArm Range: 45 → 47
>- RightArm Range: 45 → 47
>- AA Range: 45 → 47
>- AA AOE: 1.5 → 4
>- RightArm, LeftArm and EyeWeapon can now shoot 45 degrees behind them.
>- AA can shoot at a slightly greater angle to eliminate blindspots.
>- Added UseFiringSolutionInsteadOfAimBone = true for better AA performance. Credit to EQ for this AA change.

**Stun:**
- Stun effects will no longer affect air units.

### Air
**Janus:**
The Janus change in the last patch worked well but was found to be too strong. The napalm's burn time is increased to allow players to react and move out of the damage radius before all damage has been dealt. The initial damage of the bombs is also decreased.
>- DoTTime: 4.2 → 6
>- InitialDamage per bomb: 30 → 15

### Structures
**HP Reductions (Part 1)**
The goal with all the HP reductions in general is to allow more options for aggressive play, especially in the lategame and to bring the game closer to how it is working with the current low t2 pg HP and its impact on the game.

The goal with increasing the HP differences between the factions is to make them a relevant and interesting part of the game, rather than a visual difference without much impact. The changes are aimed to increase faction diversity and attempt to even out the current differences in power between the factions by giving them more unique strengths and weaknesses, rather than making them more equal. This are rather big changes, but we believe they will make the game more diverse and interesting.

To compensate cybran a bit for the rather large nerfs, and to accompany their new weakness with a strength that fits to them, all their nerfed buildings do (very slowly) regenerate health now in return. They are more vulnuable, but if you don't kill them they will be back at full HP after about 10 minutes for each building.


**UEF T1 Land Factory.pngT1 Land/Air/Navy and T2 Land/Air Support Factories**

>- UEF HP: 4100 / 4100 / 4800 and 4500 / 4500 → 4000
>- Aeon HP: 3700 / 3700 / 4400 and 4100 / 4100 → 3100
>- Seraphim HP: 3700 / 3700 / 4600 and 4300 / 4300 → 3100
>- Cybran HP: 3500 / 3500 / 4200 and 3900 / 3900 → 2500
>- Cybran HP regeneration: 3 hp/s

**UEF T2 Land Factory HQ.pngT2 Land/Air HQ and T3 Land/Air Support Factories**

>- UEF HP: 9000 and 4500 / 4500 → 8000
>- Aeon HP: 8200 and 10000 → 6200
>- Seraphim HP: 8200 and 10500 → 6200
>- Cybran HP: 7800 and 9500 → 5000
>- Cybran HP regeneration: 10 hp/s

**UEF T3 Land Factory HQ.pngT3 Land/Air HQs**

>- UEF HP: 22000 → 16000
>- Aeon HP: 20000 → 12400
>- Seraphim HP: 21000 → 12400
>- Cybran HP: 19000 → 10000
>- Cybran HP regeneration: 20 hp/s

**UEF T2 Naval Factory.png T2 Navy Support Factories**

>- UEF HP: 9000 → 6000
>- Aeon HP: 8000 → 5000
>- Seraphim HP: 8500 → 5000
>- Cybran HP: 7500 → 4000
>- Cybran HP regeneration: 6 hp/s

**UEF T2 Naval Factory HQ.png T2 Navy HQs / t3 Navy Support Factories**

>- UEF HP: 18000 / 20000 → 13000
>- Aeon HP: 16000 / 18750 → 10000
>- Seraphim HP: 17000 / 19000 → 10000
>- Cybran HP: 15000 / 17000 → 8000
>- Cybran HP regeneration: 15 hp/s

**HP Reductions (Part 2)**

**T1 Mass Extractors and T1 Power Generators:**

>- UEF HP: 600 → 760
>- Aeon HP: 600
>- Seraphim HP: 600
>- Cybran HP: 600 → 500
>- Cybran HP regeneration: 1 hp/s

**T1 Mass Storage:**

>- UEF HP: 1600 → 760
>- Aeon HP: 1600 → 600
>- Seraphim HP: 1600 → 600
>- Cybran HP: 1600 → 500
>- Cybran HP regeneration: 1 hp/s

**T2 Mass Extractors and T2 Power Generators:**

>- UEF HP: 3000 / 2160 → 2500
>- Aeon HP: 3000 / 2160 → 1900
>- Seraphim HP: 3000 / 2160 → 1900
>- Cybran HP: 3000 / 2160 → 1800
>- Cybran HP regeneration: 3 hp/s

**T3 Mass Extractors and T3 Power Generators:**

>- UEF HP: 8400 / 9720 → 9000
>- Aeon HP: 8400 / 9720 → 6200
>- Seraphim HP: 8400 / 9720 → 6200
>- Cybran HP: 8400 / 9720 → 6000
>- Cybran HP regeneration: 10 hp/s
>- Explosion Damage (only t3 Power Generator): 8000 → 5500

**Hydrocarbonplants:**

>- UEF HP: 1600 → 1800
>- Aeon HP: 1600
>- Seraphim HP: 1600
>- Cybran HP: 1600 → 1400
>- Cybran HP regeneration: 1 hp/s

**Walls:**

>- BuildTime: 10 → 20
>- UEF HP: 4000 → 3000
>- Aeon HP: 4000 → 2000
>- Seraphim HP: 4000 → 2000
>- Cybran HP: 4000 → 1500
>- Cybran HP regeneration: 3 hp/s
## 3672
### Bugs
- Fixed non-default team balance option breaking the anti-rating-bug code
## 3671
### Bugs
- Fixed an unintentional bug with hosting games with an AI introduced with the rating bug fixes below
## 3670
### Bugs
- Fixed the game reporting incorrect army indexes to the server on game start, leading to incorrect rating calculations on game end
## 3669
### Bugs
- Reverted that last one for a bit to fix an idiot bug
## 3668
### Bugs
- Fixed the game reporting incorrect army indexes to the server on game start, leading to incorrect rating calculations on game end