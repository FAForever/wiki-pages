---
title: Creating models
description: 
published: true
date: 2022-03-13T15:09:17.248Z
tags: 
editor: markdown
dateCreated: 2022-03-13T12:01:05.252Z
---

# CREATING MODELS #

This is a guide on how to create units for the game supreme commander forged alliance forever, all the software we will be using is open source and freely available  
  

## Software Used ##

[Blender](https://www.blender.org)    
[Blender tutorial](https://www.blender.org/support/tutorials/)  
Blender manual can be found in help menu
  
[Gimp](https://www.gimp.org/)    
[Gimp Tutorials](https://www.gimp.org/tutorials/)  
  
[paint.net](https://www.getpaint.net/)  
  
[Supcom addon for blender](https://github.com/Exotic-Retard/SupCom_Import_Export_Blender/tree/Blender2.80)  
  

# Method #

We won't be going through how to model in this guide, we will be focusing on the specfics of what is needed for faf, how to get a model ready for exporting and what is needed for the textures.  

## Mesh ##  
here we have our basic model (pay close attention to the arrow and xyz gimble for model direction)

![tank001.png](/images/modding/creating-models/tank001.png)

## Bones ##

At the moment it is just a mesh we need to add some bones to it, sup com works with only one bone as the parent and it uses single point bones so in blender the bottom ball on the bone is where the bone will be in game. In this example we have a turret which needs

- A bone for yaw,
- A bone for pitch (yaw and pitch can be combined in one bone if desired),
- A muzzle bone,
- If you want recoil a bone for that,
- Bones for effects,
- If you want your unit to be transportable you will need an `AttachPoint` bone that will connect it to a transport.

bones showing hierarchy 
![tank002.png](/images/modding/creating-models/tank002.png)
bones with model
![tank003.png](/images/modding/creating-models/tank003.png)

