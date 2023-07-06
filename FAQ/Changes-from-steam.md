---
title: Changes-from-steam
description: 
published: true
date: 2023-07-06T06:23:06.693Z
tags: 
editor: markdown
dateCreated: 2021-08-31T09:42:24.933Z
---

Over the years, FAF made a bunch of changes to original game balance as it was in the GPG lobby. The steam version introduces a few changes of its own, this article describes key differences between Steam and FAF balance. You can also check other useful sources below:
- [Patchnotes](https://wiki.faforever.com/en/Infrastructure/patchnotes)
- [Integrated-mods](https://wiki.faforever.com/en/Play/Game-Modifications-(Mods))
- [Unit database](https://unitdb.faforever.com/)

## Bugfixes

Multiple exploits (such as infinite mass exploits or cheap ACU upgrades) have been fixed in FAF.

## Lobby changes

Game lobbies were improved in many ways:

- Maximum player count was increased to 16.
- In addition to unit categories, it's possible to restrict specific     units. If you hate mercies or have a grudge towards UEF T3 gunships,     you have the power to disable specifically them.
- Teams can be set automatically in many different configurations
	- top vs. bottom, left vs. right, even vs. odd slots, and so on.

## Quality of life improvements

Some changes to commands were made to reduce annoyances:

- New command - split attack. Pressing Shift+G after giving an order     to a group of units will split that order into individual orders for     each unit. When used with move command, it lets units clump up tightly around a given point and helps with pathfinding in some situations. When used with multiple queued attack commands, it splits units between targets so that all of them are attacked at the same time.
- Assisting a tech 2 mass extractor automatically queues a ring of mass storages around it.
- Hotkeys can be reassigned in-game with a hotkey menu, available under F1.
- Holding Ctrl+Shift shows mass reclaim values on the map.
- It's possible to queue up multiple building and ACU upgrades.
- Mass/energy overflow is automatically transferred to teammates.

## Changes to gameplay mechanics

### Support factories

In original FA balance, the optimal way to make T2 and T3 units was to massively assist a single T2/T3 factory. Due to rolloff time that made large T2/T3 armies impractical. To fix that, FAF added support factories.

The first T2 factory you build is an "HQ" factory. It has high mass cost just like in original balance, but once built, it allows you to build support factories of the same level. A support factory has slightly less buildpower and is much cheaper, allowing for mass production of higher tier units. If you lose your HQ factory, your support factories lose the  ability to produce units and can only build high tier engineers.

### Overcharge
- Starting energy storage was reduced to 4000, while overcharge requires at least 5000 energy to fire. An energy storage has to be built before overcharge can be used.
- Overcharge was tweaked to require more energy in order to deal more damage. This makes T3 units more effective versus an ACU, since more energy is required to kill them.
- An auto-overcharge was added to ACUs. When enabled, ACUs will automatically overcharge best targets when possible.

### Veterancy

Original veterancy system counted kills, leading to odd situations like cruisers gaining massive veterancy by killing air scouts or experimentals gaining veterancy from large groups of T1 units. FAF replaced this system with mass-based veterancy, where most units have to kill 200% of their own mass cost in order to gain a veterancy level. Veterancy is also no longer gained only by the unit that landed the killing shot, but by all units that damaged the dying unit, proportionally to damage dealt.

### Overlapping shields

In original balance overlapping shields are extremely powerful, since you have to outdamage all the regenerating shields in order to break them. FAF introduced shield damage spill, where damage sustained by one shield "spills over", partially damaging overlapping shields. With this change heavily shielded bases are no longer nigh impenetrable.

### Misc changes
- Naval units leave underwater wreckage.
- Unit groups can be given special targetting priorities, such as engineers first, economy units first, PDs first, and so on. Available via a UI mod.

## Balance changes

For details, refer to the unit database. Most important balance changes
are listed below:

- Most of the atrociously unbalanced units were fixed:
	- Restorers' AA capacity was greatly nerfed.
	- T2 mobile missile launcher rockets no longer home in on their         targets.
	- Other changes that the author no longer remembers.
- T1 transports can no longer transport ACUs. This insane change was introduced in the Steam version.
- T1 air scouts are much cheaper. They also have radar and sonar.
- T1 bombers were tweaked to remove hoverbombing. In exchange, T1 bombers were buffed.
- ACU upgrades were rebalanced across the board.
- Support ACUs were rebalanced to be more useful in the field.
- ACU explosion damage was reduced to 2500 to reduce the number of draws.
- Mobile T3 AA units were added to each faction. This makes late game experimental pushes less susceptible to enemy air.
- Static T3 anti-air is much cheaper.
- Air staging stations can now be built by T1 engineers.
- Czar has a shield and reasonable anti-air attack
