---
title: Technical map requirements for matchmaker
description: An overview of all the technical requirement for a map to be allowed to the matchmaker
published: true
date: 2023-01-03T22:27:43.352Z
tags: mapping, matchmaker
editor: markdown
dateCreated: 2023-01-03T21:29:42.320Z
---

# Technical map requirements

This article represents the technical map requirements for a ladder map. These requirements are technical because they are objective: they either apply, or they don't. 

## Army setup

Ladder uses `Odd vs Even` for the team setup. You can find it as part of the `Team Options` in the lobby:

![odd-vs-even.jpg](/matchmaker/images/odd-vs-even.jpg)

As a practical example, for a 4v4 this means that:

```text
ARMY_1	-> Team 1
ARMY_2	-> Team 2
ARMY_3	-> Team 1
ARMY_4	-> Team 2
ARMY_5	-> Team 1
ARMY_6	-> Team 2
ARMY_7 	-> Team 1
ARMY_8	-> Team 2
```

## Symmetrical

The map needs to slot-symmetrical. This means that a player at a given slot should have equal opportunities as the player on the opposite slot. To describe this visually, the slots with the same colors have the equal opportunities:

![symmetrical-slots.jpg](/matchmaker/images/symmetrical-slots.jpg)

There is no requirement that lanes need to have equal opportunities. A clear example of that is Seton's Clutch, as shown on the left.

As a practical example, for a 4v4 the following players have equal opportunities:
```text
Team 1		 Team 2
-----------------
ARMY_1 <-> ARMY_2
ARMY_3 <-> ARMY_4
ARMY_5 <-> ARMY_6
ARMY_7 <-> ARMY_8
```

## Map scripts

A map can be scripted.
