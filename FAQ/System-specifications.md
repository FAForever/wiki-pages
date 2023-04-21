---
title: Minimal system specifications
description: Contains various tips and tricks to help create or to find a computer build that runs FAF seamless
published: true
date: 2023-04-21T05:42:47.237Z
tags: cpu, system specifications, minimal, processor, ram, cache
editor: markdown
dateCreated: 2023-03-16T19:03:53.115Z
---

# System specifications

In Supreme Commander: Forged alliance there are several threads that run the game. There are three main threads that can impact performance:

- (1) Simulation thread
- (2) Render thread
- (3) Sync thread

When one of these threads can not keep up then there will be different consequences. We'll shortly summarize them:

The simulation thread (1) is responsible for the (physics) simulation. A non exhaustive list of responsibilities is to computing the collisions, trajectories, path finding, effects and the AI logic. When the thread can't keep up then the game starts slowing down. During a multiplayer session the simulation needs to run in a similar pace. The player with the slowest computer will therefore determine the simulation speed of everyone involved.

The render thread (2) is responsible for rendering of and interactions with the simulation. A non exhaustive list of responsibilities is to issue draw calls to the GPU and to manage all UI or hotkey interactions. When the thread can't keep up then the game starts showing frame drops. This thread is entirely separated from the simulation. During a multiplayer session any changes to the render thread does not impact other players in that session. 

The sync thread (3) is responsible for the communication between the render and the simulation thread. It can sync information from the simulation to the UI, or initiate callbacks from the UI to the simulation. If it can't keep up then both the simulation and the render thread will stall. Usually the load on the sync thread is minimal, at best.

## Hardware

In this section we'll discuss some details of hardware that is relevant in understanding the adjusted specifications in the next section. A processor consists of one or more compute cores. A compute core can take care of multiple threads, but a thread can only be assigned to a single compute core at a time. Supreme Commander does not have a job-like system, as described in [Multithreading for Gamedev Students](http://www.fragmentbuffer.com/docs/MultithreadingForGamedevStudents.pdf) written by the technical lead of Ubisoft Montreal. It looks very similar to the pipelining architecture as described in the same document. Because of this architectural choice the game can only use one thread for the computing simulation and only one thread for rendering. We'll focus the remainder of this section on the simulation thread.

As a rough sketch, the total performance of a modern processor depends on three aspects:

- (1) The number of compute cores
- (2) The frequency of individual compute cores
- (3) The amount of cache on the CPU die

Supreme Commander performs best on a processor with at least four compute cores. This allows the operating system to assign each thread to a separate compute core. It also leaves some resources for the operation system and other applications. Any further growth of the total performance of the processor through (1) does not apply to Supreme Commander. As an example: a processor with sixteen compute cores will likely perform similar to a processor with four compute cores with the assumption that you are only running Supreme Commander. 

The frequency (ghz) of the compute cores has a significant impact on the simulation. This is most notable when a processor lowers the frequency to preserve power or to prevent overheating. Or when the operating system decides to no longer boost Supreme Commander to a higher frequency. The changes are simple: if you gain 20% frequency then you can run 20% more units. If you lose 20% frequency then you can run 20% fewer units. 

The cache on the CPU die has a significant impact on the simulation too. A new problem emerged due to the high frequency of modern processors: feeding the beast with data! The cache was introduced to help with this. The larger the cache, the less the processor has to wait for data and therefore the faster the simulation. 

## Specifications

In this section we discuss the minimal system specifications to run the average game on Forged Alliance Forever without slowing down the game.

## Adjusted specifications

|Hardware| Adjusted minimal specifications|
|-|-|
|Processor| AMD Ryzen 5 5600G or equivalent |
|Memory|8GB RAM Dual channel memory|
|Hard Disk Space|16GB available solid state space|
|Video Card| integrated graphics or any modern gpu |



|Hardware| Adjusted recommended specifications|
|-|-|
|Processor|AMD Ryzen 7 5800X3D or equivalent|
|Memory|16GB RAM Dual channel memory|
|Hard Disk Space|32GB available solid state space|
|Video Card|any modern gpu|

## Legacy specifications



|Hardware| Minimal specifications|
|-|-|
|Processor|1.8 GHz processor|
|Memory|512 MB RAM|
|Hard Disk Space|8GB available hard drive space|
|Video Card|128 MB video RAM or greater, with DirectX 9 Vertex Shader / Pixel Shader 2.0 support (ATI 9600+, Nvidia 6200+)|



|Hardware| Recommended specifications|
|-|-|
|Processor|3.0 GHz Intel or equivalent AMD processor or better|
|Memory|1 GB RAM or better|
|Hard Disk Space|8GB available hard drive space|
|Video Card|256 MB video RAM, with DirectX 9 Vertex Shader / Pixel Shader 2.0 support (Nvidia 6800 or better)|


## Frequently asked Questions (FAQ)

