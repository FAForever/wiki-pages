---
title: Orders - Mouse context
description: 
published: true
date: 2023-11-05T05:44:27.678Z
tags: 
editor: markdown
dateCreated: 2023-08-26T15:44:55.485Z
---

# Orders - Mouse context sensitive

The following hotkeys behave different depending on the context of your mouse. As an example: these hotkeys may behave different depending on the unit (type) that you're hovering over.

## Cycle templates

Cycles a set of [pre-defined build templates](https://github.com/FAForever/fa/blob/deploy/fafdevelop/lua/ui/game/hotkeys/context-based-templates-data.lua) based on the context of your mouse and your selection. You can cycle by applying the hotkey multiple times. Through UI mods you can remove existing or add your own templates. You can learn more about that [here](/Development/Modding/managing-context-based-templates).

FAForever ships with the following build templates:

- `Hover over an extractor`: Cap with storages
- `Hover over an extractor`: Cap with storages and fabricators
- `Hover over a radar`: Cap with tech 1 power generators
- `Hover over a tech 2 artillery`: Cap with tech 1 power generators
- `Hover over a tech 3 artillery`: Cap with tech 3 power generators
- `Hover over a tech 3 fabriactor`: Surround with storages
- `Hover over land`: Capped tech 1 Point defense
- `Hover over land`: Tech 1 anti air defense
- `Hover over water`: Tech 1 torpedo defense
- `Hover over water`: Tech 1 anti air defense
- `Hover over a mass deposit`: Tech 1 extractor
- `Hover over a mass deposit`: Tech 2 extractor with storages
- `Hover over a mass deposit`: Tech 3 extractor with storages
- `Hover over a mass deposit`: Tech 3 extractor with storages and fabricators
- `Hover over a hydro deposit`: Hydrocarbon plant

<br>

<video style="border-radius: 10px" width="1200" height="500" controls>
  <source src="/hotkeys/orders-context/cycle-templates.mp4" type="video/mp4">
</video>

## Apply target priorities

Applies target priorities to your selection to prioritize the unit type that your mouse is hovering over. This doesn't necessarily mean that your selection will fire at the specific unit that your mouse is on top of. It generalizes, take as an example when we apply it to a Titan:

- `categories.uel0303`
- `categories.TECH3 * categories.UEF * categories.DIRECTFIRE * categories.LAND` 
- `categories.TECH3 * categories.DIRECTFIRE * categories.LAND` 
- `categories.DIRECTFIRE * categories.LAND` 
- `categories.LAND`

Your selection will first prefer to target any unit with the `uel0303` category. . Then it generalizes to units with the `TECH3`, `UEF`, `DIRECTFIRE` and `LAND` categories, then to units with the `TECH3`, `DIRECTFIRE` and `LAND` categories, then to untits with the `DIRECTFIRE` and the `LAND` categories and last to any units with the `LAND` category. 

<br>

<video style="border-radius: 10px" width="1200" height="500" controls>
  <source src="/hotkeys/orders-context/apply-target-priorities.mp4" type="video/mp4">
</video>

## Cap a structure

To cap a structure is the process of surrounding the target structure with other structures for adjacency. A well-known example is a mass extractor surrounded with storages. This hotkey makes it easier for you to cap structures that you'll usually always want to cap. The hotkey is less restricted than the in-game 'assist-to-cap' interactions and it doesn't issue an assist order on the target.

- `Hover over an extractor`: Cap with storages
- `Hover over an extractor and hit the hotkey twice`: Cap with up to 8 fabricators
- `Hover over a radar`: Cap with tech 1 power generators
- `Hover over a tech 2 artillery`: Cap with tech 1 power generators
- `Hover over a tech 3 artillery`: Cap with tech 3 power generators


*Behavior without the shift modifier where orders are cleared*

<br>

<video style="border-radius: 10px" width="1200" height="500" controls>
  <source src="/hotkeys/orders-context/cap-structure.mp4" type="video/mp4">
</video>

*Behavior with the shift modifier where orders are queued*

<br>

<video style="border-radius: 10px" width="1200" height="500" controls>
  <source src="/hotkeys/orders-context/cap-structure-shift.mp4" type="video/mp4">
</video>


## Upgrade a structure

Attempts to upgrade the structure you're hovering over. Favors upgrading to a support factory when possible. There is a secondary alternative hotkey that also pauses the structure. This works in synergy with the 'Assist to unpause' feature in the game options.

<br>

<video style="border-radius: 10px" width="1200" height="500" controls>
  <source src="/hotkeys/orders-context/upgrade-structure.mp4" type="video/mp4">
</video>

