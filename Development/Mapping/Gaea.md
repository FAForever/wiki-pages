---
title: Advanced mapping with Gaea
description: 
published: true
date: 2023-08-26T08:37:27.924Z
tags: mapping, gaea
editor: markdown
dateCreated: 2023-05-09T10:38:02.040Z
---

# Making high quality maps with Gaea - A tutorial series
<img align="right" src="/images/mapping/gaea/gaea_general.png" width="60%">Welcome to the Gaea Map-Making Tutorials for Forged Alliance Forever (FAF).

I am IndexLibrorum (AKA Prohibitorum) and I've been trialblazing the use of Gaea in FAF mapping. An overview of my work can be found [here](https://forum.faforever.com/topic/6066/index-librorum-s-maps-assorted-projects-and-gaea-tutorials). Being the inexhaustible fount of charity and enlightenment that I am, I have decided to write out this series of tutorials, in which I will explain to you how to make maps in FAF without having to do such tedious things as handpaint terrain and masks. With this series, I aim to save you from the pain that is trying to figure out why your masks somehow have stopped behaving as they should for the 11th time in an hour, and catapult you straight to map-making mastery.

Gaea is a powerful industry-standard terrain generation software that allows you to build hyper-realistic looking terrain for such projects as block buster movies, games by Ubisoft and Blizzard, and whatever NASA has used it for that got their logo to show up on Quadspinner's website. You can also use it to build maps for a—somehow still active—15 year old RTS. Whether you're a seasoned map maker or relatively new to the world of terrain generation, these tutorials should provide you with the basic knowledge and techniques to bring your map-making skills to the next level.

Because the length out these tutorials fairly quickly got out of hand, I've split this series in  chapters. Please note that these tutorials assume you have some basic understanding of map making. While I will discuss some of the basics whenever I feel they are relevant, I'd like to recommend you refer to the various tutorials available on the wiki if you get stuck with anything that is not directly related to Gaea.

> This section uses [*Gaea*, a third-party software developed by Quadspinner](/en/https://quadspinner.com/). As of June 2023, they offer the indie version of their software for free on their website. The indie version is limited to a maximum render resolution of 1k. As a consequence, you will require an upgraded license if you are planning to make maps that are bigger than 20x20km.
{.is-info}

## Terminology
In my conversations with others in the FAF discord's mapping-general channel, I've come to realize that explaining certain concepts can be a bit challenging, primarily due to the lack of clear definitions for some elements. To ensure that we're all on the same page, please refer to the [terminology page](/en/Development/Mapping/Terms) for definitions of mapping-related terms.

>Note that the terminology list does not include the specific names for less common terms, such as the names of elements of Gaea, as those are defined in their respective tutorials.
{.is-info}

# Basic introduction to mapping with Gaea:
In this tutorial, we'll discuss the fundamentals and guide you through the basics of using Gaea for map creation. We'll explore the user interface, essential tools and techniques for generating terrain, setting up the scale and dimensions, and discuss how to render your heightmap for use in the FAF map editor. Additionally, we'll discuss how you may generate realistic terrain features, including mountains, crater fields, canyons, and more, using the power of procedural generation.

- [A basic introduction to mapping with Gaea*Basics of the software*](/en/Development/Mapping/Gaea/Basic-Introduction)
{.links-list}

# Producing Terrain Masks in Gaea:
Terrain masks are crucial for defining texture distribution on your map. In this tutorial, we'll dive into the process of creating terrain masks using Gaea's powerful procedural algorithms and functions.

- [Producing terrain masks in Gaea*Producing stratum masks for texturing*](/en/Development/Mapping/Gaea/Terrain-Masks)
{.links-list}

# Texturing in Gaea:
This tutorial on texturing in Gaea will teach you how to set up a texturing prototype using the masks you learnt to generate in tutorial two. Using this prototype, you can quickly evaluate your masks and make changes where needed. Additionally we will discuss the use of Satmaps in preparation for creating the map-wide albedo generation, for which a seperate tutorial is made available. Lastly, we will discuss how to create custom textures to further improve the aestethics of your map.

[Link to tutorial]

# Creating Map-Wide Assets:
With the terrain created and textured, we will take a look at the map-wide assets we can create to bring our maps to the next level. We will discuss how to create a map-wide albedo decal, map-wide normal-map decal, and map-wide shadow decal. Together, these decals will add the final touches to bring your map to life.

[Link to tutorial]

# Help and frequently asked questions
To help you on your way, all tutorials include a section on common mistakes and their fixes. If these sections do not help you when you are stuck, please feel free to ask for help in the [FAF discord's](https://discord.gg/6F54xXrEkb) mapping-section. The mapping-channels in the FAF discord include two threads containing my research notes and comments on Gaea, which you might find useful. Alternatively, [contact Prohibitorum](https://discord.com/channels/@me/prohibitorum/) on discord directly.
