---
title: Creating Models
description: 
published: true
date: 2022-03-14T17:52:01.760Z
tags: 
editor: markdown
dateCreated: 2022-03-13T12:01:05.252Z
---

# CREATING MODELS 

This is a guide on how to create units for the game supreme commander forged alliance forever, all the software we will be using is open source and freely available  
  

## Software Used 

[Blender](https://www.blender.org)    
[Blender tutorial](https://www.blender.org/support/tutorials/)  
Blender manual can be found in help menu
  
[Gimp](https://www.gimp.org/)    
[Gimp Tutorials](https://www.gimp.org/tutorials/)  
  
[paint.net](https://www.getpaint.net/)  
  
[Supcom addon for blender](https://github.com/Exotic-Retard/SupCom_Import_Export_Blender/tree/Blender2.80)  
  

# Method 

We won't be going through how to model in this guide, we will be focusing on the specfics of what is needed for faf, how to get a model ready for exporting and what is needed for the textures.  

## Mesh 

Here we have our basic model (pay close attention to the arrow and xyz gimble for model direction)
![tank001.png](/images/modding/creating-models/tank001.png)

---

## Bones 

At the moment it is just a mesh we need to add some bones to it, Sup Com works with only one bone as the parent and it uses single point bones so in blender the bottom ball on the bone is where the bone will be in game. In this example we have a turret which needs

### Turret Bones 

- A bone for yaw,
- A bone for pitch (yaw and pitch can be combined in one bone if desired),
- A muzzle bone,
- If you want recoil a bone for that,

### Extra Bones

- Bones for effects,
- An `AttachPoint` bone that will connect it to a transport,
- Bones for anything you want to animate
- Bones for units to target

Once we have our bones set up we need to switch back to the mesh and parent it to the bones, and add an armature modifier connected to the bones but don't apply it

Bones showing hierarchy 
![tank002.png](/images/modding/creating-models/tank002.png)

---
Bones with model
![tank003.png](/images/modding/creating-models/tank003.png)

---
Adding the armature modifier
![tank004.png](/images/modding/creating-models/tank004.png)

---
How your bone hierarchy should look
![tank005.png](/images/modding/creating-models/tank005.png)

---

## UV Map

We are now going to UV unwrap the model, I would reccomend creating a duplicate of the entire model, Then deleting all the parts that are the same so in our tank example I will be removing one the treads then duplicating it after unwrapping one, also in this example we will have scrolling treads which require us to place them at the bottom of the texture

> 1024x1024 : The bottom 52px are the left side then the next 52px are the right side  
512 x 512 : The bottom 26px are the left side then the next 26px are the right side
{.is-info}

A treads template
![supcomtreads.png](/images/modding/creating-models/supcomtreads.png)

---
An example from the game
![uel0201_albedo_no_alpha.png](/images/modding/creating-models/uel0201_albedo_no_alpha.png)

---

The UV unwrapped from our example model
![uv_test0102.png](/images/modding/creating-models/uv_test0102.png)

---

## Vertex Groups

All vertices need to be in a group with the same name as the bone you want then attached to, vertices can only be in one group.

The groups we should have for our example
![tank006.png](/images/modding/creating-models/tank006.png) 

---

## Textures


### Aeon Shader (Aeon), UEF Shader (Unit) , Cybran Shader (Insect)

#### diffuse:
 - r = Albedo red channel
 - g = Albedo green channel + shininess multiplier
 - b = Albedo blue channel
 - a = Alpha channel

#### normals:
 - r = ?
 - g = X direction (left / right)
 - b = ?
 - a = Z direction (front / back)

#### specular:
 - r = Reflectivity multiplier (of environment set by map)
 - g = Shininess multiplier
 - b = Glowing mask
 - a = Team color mask

### Seraphim Shader (Seraphim)

#### Albedo

#### Normals

#### Spec Team

- R :

- G :

- B :

- A :

## Animation 

Animation need to pused down the nla stack before exporting.

