---
title: Creating AI friendly maps
description: Tips for ways to make maps more AI friendly
published: true
date: 2023-03-23T22:14:43.991Z
tags: mapping
editor: markdown
dateCreated: 2023-03-23T22:14:43.991Z
---

# Introduction
The below points are intended to highlight examples of map design that are more likely to cause issues with AI.  It is not an exhaustive list, and whether the point is relevant will depend largely on the AI in question.
Just because a point is noted below as causing problems for AI, it doesn’t mean the issue should always be avoided.  In many of the points noted the issue is also due to a flaw/limitation in the approach commonly used by AI that could in theory be resolved by the AI.
Common AI approaches to games
While the approach an AI takes to the game is very heavily dependent on the AI being considered, the following is a relatively common approach:
- At the start of the game, identify the hostile player (i.e. human or AI) that is closest to the AI on a straight line distance, and prioritise attacks on this enemy.
- Various decisions will be made based on the distance of units to a particular point.  For example, deciding to attack when a unit is within a certain distance, or considering enemy threats within a certain distance of a start position.  Most of the time, such distance checks are based on a straight line distance, as opposed to considering how long it would take for a unit to travel there.  Depending on the map design this can often lead to unintended consequences for the AI (with its choice of how to respond to threats and where to send units) if a straight line distance check would result in a significantly different result to a land pathing result.