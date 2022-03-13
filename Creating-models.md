---
title: Creating models
description: 
published: true
date: 2022-03-13T16:36:36.297Z
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
- If you want your unit to be transportable you will need an `AttachPoint` bone that will connect it to a transport,

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

Sup Com textures use a single image for the textures, We are now going to uv unwrap the model, I would reccomend  

## Vertex Groups

