---
title: Orders - Queue manipulation
description: 
published: true
date: 2024-03-04T13:34:58.153Z
tags: hotkeys, keys, queue, command queue
editor: markdown
dateCreated: 2023-08-26T12:07:22.650Z
---

# Orders - Queue manipulation

The following hotkeys manipulate the command queue of the units in your selection.

## Distribute orders

The distribute orders feature supersedes the spread attack feature. The spread attack feature is removed. All UI mods that relied on the spread attack feature will no longer be functional.

The distribute orders feature takes the command queue of one unit and distributes the orders in that command queue over the units of your selection.  There are three hotkeys that interact with this feature:

-  Distribute orders (with shift version)
-  Distribute orders from the unit beneath the mouse cursor (with shift version)

The first hotkey is the default that is assigned to `shift + g`. It uses the command queue of the unit in your selection that is nearest to your mouse location. The second hotkey uses the command queue of the unit that your mouse is on top of. The orders are distributed over all units in your selection and are applied immediately.

The new implementation is not [idempotent](https://en.wikipedia.org/wiki/Idempotence). In layman's terms: do not apply it two or more times in a row to a selection. In the average case, you'll lose orders as you do that. There is on-screen text to help players understand that the distribute command is issued.

The distribute order feature breaks formations. Any formations (direct, or indirect) are lost when you process the command queue using the distribute order feature.

### Build orders

All build orders are applied. When there are more orders than batches then the first batches will receive additional orders.

<br>

<video style="border-radius: 10px" width="1200" height="500" controls>
  <source src="/hotkeys/orders-queue-manipulation/distribute-build.mp4" type="video/mp4">
</video>

### Move orders

All move orders are applied. When there are more orders than batches then the first batches will receive additional orders.

<br>

<video style="border-radius: 10px" width="1200" height="500" controls>
  <source src="/hotkeys/orders-queue-manipulation/distribute-move.mp4" type="video/mp4">
</video>

### Attack move orders

All attack move orders are applied. When there are more orders than batches then the first batches will receive additional orders.

<br>

<video style="border-radius: 10px" width="1200" height="500" controls>
  <source src="/hotkeys/orders-queue-manipulation/distribute-attack-move.mp4" type="video/mp4">
</video>


### Attack orders

Attack orders have redundancy. The implementation attempts to assign each order to each batch of units. Redundancy falls off at 10 or more orders.

<br>

<video style="border-radius: 10px" width="1200" height="500" controls>
  <source src="/hotkeys/orders-queue-manipulation/distribute-attack.mp4" type="video/mp4">
</video>

### Patrol orders

Three patrol orders are applied to each unit. The patrol orders that are applied are chosen pseudorandomly.

<br>

<video style="border-radius: 10px" width="1200" height="500" controls>
  <source src="/hotkeys/orders-queue-manipulation/distribute-patrol.mp4" type="video/mp4">
</video>

### Reclaim orders

Attack orders have redundancy. The implementation attempts to assign each order to each batch of units. Redundancy falls off at 3 or more orders.

<br>

<video style="border-radius: 10px" width="1200" height="500" controls>
  <source src="/hotkeys/orders-queue-manipulation/distribute-reclaim.mp4" type="video/mp4">
</video>

### Assist orders

All assist move orders are applied. When there are more orders than batches then the first batches will receive additional orders.

<br>

<video style="border-radius: 10px" width="1200" height="500" controls>
  <source src="/hotkeys/orders-queue-manipulation/distribute-assist.mp4" type="video/mp4">
</video>

### Load orders

All orders _before the load orders_ are **ignored**. This is intentional. The implementation prefers to use higher-tech transports and prefers to load in higher-tech units first. The implementation prefers to fully load a transport. Not all transports are necessarily used.

<br>

<video style="border-radius: 10px" width="1200" height="500" controls>
  <source src="/hotkeys/orders-queue-manipulation/distribute-load.mp4" type="video/mp4">
</video>

### Sacrifice orders

Sacrifice orders are applied as there are engineers to sacrifice.

<br>

<video style="border-radius: 10px" width="1200" height="500" controls>
  <source src="/hotkeys/orders-queue-manipulation/distribute-sacrifice.mp4" type="video/mp4">
</video>

### Capture orders

All capture orders are applied. When there are more orders than batches then the first batches will receive additional orders.

<br>

<video style="border-radius: 10px" width="1200" height="500" controls>
  <source src="/hotkeys/orders-queue-manipulation/distribute-capture.mp4" type="video/mp4">
</video>

### Combining orders

You can combine orders. They are processed in groups of orders, where a single group represents a type of order. Each group is processed by the type of order. As a few examples:

#### Move + attack orders

<br>

<video style="border-radius: 10px" width="1200" height="500" controls>
  <source src="/hotkeys/orders-queue-manipulation/distribute-combined-move-attack-01.mp4" type="video/mp4">
</video>

<video style="border-radius: 10px" width="1200" height="500" controls>
  <source src="/hotkeys/orders-queue-manipulation/distribute-combined-move-attack-02.mp4" type="video/mp4">
</video>

#### Load + build orders

<br>

<video style="border-radius: 10px" width="1200" height="500" controls>
  <source src="/hotkeys/orders-queue-manipulation/distribute-combined-load-build.mp4" type="video/mp4">
</video>

## Copy orders

Applies the command queue of the unit that your mouse is on top over to your selection. The orders may have different behaviour than the orders of the original queue. As an example: move orders that are issued directly by the user use a platoon-like formation. Move orders that are copied do not apply the formation. All units move to the waypoint in question.

<br>

<video style="border-radius: 10px" width="1200" height="500" controls>
  <source src="/hotkeys/orders-queue-manipulation/copy.mp4" type="video/mp4">
</video>

