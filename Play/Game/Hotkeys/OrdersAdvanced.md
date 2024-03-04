---
title: Orders - Advanced
description: 
published: true
date: 2024-03-04T13:33:50.713Z
tags: 
editor: markdown
dateCreated: 2023-08-26T15:12:20.626Z
---

# Orders - Advanced

The following hotkeys usually combine several interactions into one. They exist as quality-of-life features towards users.

## Filter engineers

Filters your selection based on tech. All engineers that are of a lower tech assist the higher tech engineers.

<br>

<video style="border-radius: 10px" width="1200" height="500" controls>
  <source src="/hotkeys/orders-advanced/filter-engineers.mp4" type="video/mp4">
</video>

## Load into transports

Loads all transportable units of your selection into the transports of your selection. The implementation prefers to use higher-tech transports and prefers to load higher-tech units first. The implementation prefers to fully load a transport. Not all transports are necessarily used.

Units are loaded in three stages:

- (1) Load in tech 3 units
- (2) Load in tech 2 units
- (3) Load in tech 1 units

This is intentional. Due to an engine bug, the transports may assign tech 1 units to slots that then end up blocking tech 3 units. It can negatively impact the time that it takes to load the transports in comparison to other methods.

<br>

<video style="border-radius: 10px" width="1200" height="500" controls>
  <source src="/hotkeys/orders-advanced/load-into-transport.mp4" type="video/mp4">
</video>


## Interrupt navigation of engineers

Cancels the navigation of the engineers in your selection. A lot of orders have a navigational element in them. For this example, we'll take the assist order. The unit will first move in formation around the target that you intend to assist. Usually, this is a lot closer to the target than what is technically required. Using this new hotkey you can manually abort the navigation and immediately proceed to apply the order.

<br>

<video style="border-radius: 10px" width="1200" height="500" controls>
  <source src="/hotkeys/orders-advanced/abort-navigation-01.mp4" type="video/mp4">
</video>

The same applies to any order with a navigational element to it. Specifically, it is interesting for the build, reclaim, capture and attack move orders.