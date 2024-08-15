---
title: 3D Printing Models
description: A guide on how to 3D print units from the game
published: true
date: 2024-08-15T15:36:08.851Z
tags: 
editor: markdown
dateCreated: 2024-05-13T23:21:07.574Z
---

# Part 1: The in-game model
## Step 1: Download the applications you'll need
1. **Blender 4.1** (or whatever version is most current, this guide will be written using 4.1) 
https://www.blender.org/download/
2.  **Add supcom mesh importer to Blender**, instructions are in the link so I will not rewrite them here
[_https://github.com/Solstice245/scstudio_](https://github.com/Solstice245/scstudio)
   3.  **Microsoft 3D Builder**
         [_https://apps.microsoft.com/detail/9wzdncrfj3t6?hl=en-us&gl=US_](https://apps.microsoft.com/detail/9wzdncrfj3t6?hl=en-us&gl=US)
         This is only available for Windows. We'll only be using it to automate much of the hard work of making our models manifold. I'll explain what that means later in the guide, but that word should help you find alternatives for your operating system.
4. **An image editor of your choice**
	It needs to be able to open .dds files, otherwise you might have to use some kind of online converter. I use Photoshop but I understand that isn't accessible to most people.
## Step 2: Get the files you'll need
### Figure out its unit ID
| If it's a FAF unit | If it's a modded unit |
|
| Find it on the unit db [_https://unitdb.faforever.com/_](https://unitdb.faforever.com/) | Host a sandbox game with the mod you want and cheating enabled |
| Find its unit ID, hovering over the unit should make the ID pop up in the bottom. You can also double click on the unit in the table and its ID will be at the top.| Once you launch hit Alt-F2 to open the unit spawn menu |
| ![engineer_id.png](/images/learning/3d_print_guide/engineer_id.png) Unit ID for UEF T1 Engineer is UEL0105 | This may get intercepted by other software like GeForce Experience. You can change it from Alt-F2 in the keybinds menu. Search for “create units” |
| | Filter or search for the unit you want and take note of the unit ID |
| | ![](/images/learning/3d_print_guide/basilisk_id.png)Unit ID for the Basilisk is BRL 0401|

    
### Get the correct units folder
| If it's a default unit | If it's a unit added by FAF, such as T3 MAA or a support factory | If it's a modded unit |
|
|Go to your Steam library, right click on Forged Alliance, then Manage > Browse local files. On GOG this is Manage installation > Show folder| Open the  FAF client, click on the hamburger menu in the top left, and then Show data folder | Have the mod downloaded (duh)|
|Go to the gamedata folder and find units.scd|Go to FAForever > Gamedata and find units.nx2| Open the FAF client, click on the hamburger menu in the top left, and then Show mods folder|
| Copy this folder into a new folder where you’ll be working from| Copy this folder into a new folder where you’ll be working from|Go to the mod you want, and copy the units folder into a new folder where you’ll be working from|
| Rename it to units.zip | Rename it to units.zip | |
| Unzip this folder | Unzip this folder| |


# Step 3: Importing into Blender
1.  Launch Blender
2. Create a new general project
3. Delete the default cube by clicking on it and hitting x
4. Change your units to millimeters by clicking Scene Properties on the right side. Change the length unit to Millimeters and the Unit Scale to 0.001
   ___________ ![blender_scene_properties.png](/images/learning/3d_print_guide/blender_scene_properties.png)
5.  Click on File, then Import, then Supcom Mesh (.scm)
6.  Navigate to the units folder you got in step 2, then the unit ID for your unit of choice, select the file ending in \_lod0, and hit Import SCM
> Always ignore files containing lod1. These are used when zoomed out so the game can use a low resolution version of the file.
{.is-info}

7.  You should now have a blobby gray representation of your unit.  Left click on it to select it if it isn’t already, right click, and select Shade Flat, this will make all the faces visible. Don’t worry you’re not removing any detail, it just turns off Blender’s smoothing in the preview
> 	Those pyramids with spheres are called bones, and are used for posing the model (like making an ACU mid-walk). Posing models is out of scope for this guide, so you can just hide them by clicking the eyeball next to your model in the top right. If you *do* want to pose your model and know how to, make sure you do so now as the next steps will remove the bones.
{.is-warning}


## Step 4: Making it manifold

### What does manifold mean?
A model being manifold means that it could be completely filled with water. It has no holes, no sections divided on the inside, and no intersecting geometry. This article has more details as well as some examples of non-manifold shapes https://www.instructables.com/Non-manifolds-Your-Worst-3D-Printing-Nightmare/.

### Why does it matter if it's manifold?
A non-manifold shape cannot exist in real life, and by extension cannot be printed. The 3D artists for the game had no such restriction, and so every model has all sorts of intersecting geometry that don't matter for the game's purposes. If you try to export it as an STL now your slicer will likely give you a warning, and then try its absolute best to interpret the physically impossible geometry, usually with poor results.
> ![non-manifold_t1_tank.png](/images/learning/3d_print_guide/non-manifold_t1_tank.png) Here's what happens to a UEF T1 tank if I try to slice it without making it manifold first.
{.is-info}

   
 ### Ok I get it, now how do I make sure it's manifold?
 We'll be using Microsoft 3D Builder's repair feature to do most of the heavy lifting, but unfortunately it's not magic. We'll have to do a little bit of the work ourselves.
   1. Select your model in blender by clicking on it
   2. Below File and Edit you should have a button that says "Object Mode". Click on that and then click Edit Mode.
   3. Immediately to the right of that button you should have 3 more. These are your selection buttons. In order they are to select vertices, edges, and faces. Click on the edge selection mode (the middle of those 3).
>    **If your model is symmetrical**, good choice! You now only have have to do half the work. Even more to the right of those buttons you should have some additional options. First click Select > All, then Mesh > Bisect. Click and drag approximately where you want this cut to be, and when you release a window should pop up in the bottom left. If your model is symmetrical left to right then the only things that matter are that Plane Point X, Plane Normal Y, and Plane Normal Z are all set to 0. Now click either Clear Inner or Clear Outer and you'll have a perfectly cut in half model. To mirror it back to both sides, first click on the blue wrench on the right side toolbar where Scene Properties were. Then Add Modifier > Generate > Mirror. It should immediately have the correct settings to make a copy on the other side.
{.is-info}

   4. Look around your model by holding the middle mouse button down and moving your mouse. You should see some holes in the geometry, especially underneath the model. There might also be some floating geometry that you need to connect.
   5. Unfortunately learning how to fix all these kinds of things would take hours of Blender tutorials, but I'll try to have you get by with just two operations: Fill and Extrude
   	**Fill**: Select two edges bordering on a hole. Now right click and select New Face From Edges or hit F. This will create a new face connecting the two edges.
    **Extrude**: Select however many edges. Right click and select Extrude Edges. Your mouse should be directly on top of it when your right click. You can now move your mouse and drag those edges where you might need to fill in gaps or connect geometry. Left click to "drop" those edges. Don't worry about getting the positioning right, dropping the edges will pop up a window in the bottom left where you have fine control by inputting a number along each axis.
>   Don't worry about creating intersecting geometry or any of the other things that make an object non-manifold. 3D Builder will take care of those, we're just making it clear to it what the final result should look like. 
{.is-info}

   6. Once you're happy you've filled in all the holes, go back into Object View, select your model, and then click on File > Export > STL (.stl). Export it into your working folder. Make sure only selection is enabled on the right hand side.
   7. Open Microsoft 3D Builder and click New Scene
   8. Click on the hamburger menu in the top left corner, then Open, and Load Object
   9. Find the STL you just exported through Blender and open that, then hit the check mark labeled "Import Model" in the top left
   10.  An error should pop up once it loads with the message "Click here to repair." Click it
   11.  Open the hamburger menu again and hit Save
   12.  Import this model back into blender, remember you're importing an STL this time, not an SCM. If you click on import SCM the STL file won't show up. 3D Builder also has a habit of scaling the model up, so you might need to reduce the scale to 0.1 by clicking on it and using the scale option in the top right.
>    Don’t replace the old model, I highly recommend keeping multiple copies of your model in the Blender file should you ever mess something up and need to go back a step or multiple.
{.is-warning}

### Why's it still look so bland?
What we just made is the in-game model. Much of the detail you see in game is given by textures, essentially painted on top of the model. This is great for a video game as it is has MUCH better performance, but is unfortunate for 3D printing as our printers cannot print those textures. **If what we've made so far suits your needs, perfect! You can take this right to the slicer and it will turn what you see in Blender right now into a plastic piece you can hold.** 

If you want to add some additional detail... prepare yourself, because things are about to get messy.
   
# Part 2: Adding detail
I have two ways to do this. The garbage way and the "proper way". The garbage way uses immense computer processing power and calculation time to give a result that looks... well its mother would love it. *But* it's much faster and less effort, and depending on how large you plan to print the poor looking elements might be too small to notice.

The "proper" way creates a model that is likely what you were imagining going into this process. It will also be *far* easier to work with should you want to add separate sections for multi-material printing, rotating turrets, or other features.

They both have the same few first steps.

## Creating a reference in Blender
Import the original scm back into Blender. Don't delete any of the work you did in Part 1, we'll still be using that. You might need to move it to the side by clicking and dragging one of the location coordinates under Transform in the top right.  

1. Remember to shade flat by selecting it and right clicking on it
2. On the bottom of the right side toolbar where Scene Properties were, there should be a red sphere. Hovering over it should say "Material". Click on that
3. Create a new material by clicking New. The name doesn't really matter
4. Look down to where it says Base Color, there's a tiny yellow circle right next to it. It doesn't look a button, but it is. Click on that little yellow circle.
5. Under the column labeled "Texture" click Image Texture
6. Now underneath where Base Color was click "Open"
7. Navigate to your working folder, then the folder for your unit ID, and open the file named  [UnitID]_Albedo.dss.
8. Click on the third button here (to the right of the blue one with a white circle) to enter Material Preview, your unit should now have textures.
![material_preview.png](/images/learning/3d_print_guide/material_preview.png)
 
 ## Texturing our manifold version
 1. Select the manifold version, go into edit mode, and go into face select mode
 2. Select all faces (the hotkey to do this is A), right click, and then click UV Unwrap Faces > Smart UV Project. All the default seting should be fine so click OK.
 3. Go back into object mode, select both the manifold and original, textured versions by selecting one, holding shift, and selecting the other.
 4. Right click, and click Join. The manifold tank should now also be textured, but it will be a complete jumble of textures and will look nothing like the in-game version.
 5. At the very top next to File, Edit, Render, ect., you should have a series of tabs. You are in the Layout tab by default, but we need to be in the UV Editing tab. Click on that.
 6. Your window will now be split into two. On the right you'll have a window that you're familiar with, but on the left you're be looking at a blank square. Let's give us something to look at, and then I can explain what UVs are and what this mode is for.
 7. In the top middle of your left window you should have buttons labeled "New" and "Open". Click on "Open" and then open the Albedo.dds file for your unit. You'll now have something that looks like you took an origami version of your unit and unfolded it.
 8. Now put your your right window into Material mode using the options in the top right corner. Immediately to the left of those options you'll have an option that looks like two squares on top of each other. This toggles X-ray mode, it allows you to see (and select) through objects. Toggle that on.
 9. Select all the faces of the original model by just dragging a rectangle covering all of it. You'll now have have a bunch of shapes light up on the left window.
 10. *Now* I can explain what a UV map is. Any time you want to apply textures to a 3D model you need a way to tell the model where those textures go. Those shapes that appeared on the left window represent each face of the model, and where each part of the texture goes. Hence why it's called a map.
 11. Select your manifold version of the model. Notice that the the arrangement is shapes is completely different to the original. This is why it looks like a mess of textures. It's using the correct texture, but the map to tell where to put each part of the texture is incorrect.
 12. This is the where the first tedious part of adding detail comes in. We'll need to manually map *each face* to its proper position on the texture. First turn X-ray mode back off. Then select the same group of faces on each model, making sure they're connected in on the texture window.![both_faces_selected_2.jpg](/images/learning/3d_print_guide/both_faces_selected_2.jpg) The original is to the rear right, and my manifold version is in the front left.
 13. You'll notice in the texture window that not only are the manifold faces (in orange) in a completely different location, they're a different shape that doesn't match 1:1 to the original in white. That's part of why we made it manifold, if it matched 1:1 then we'd have the same unprintable mess as we did originally. Now you'll have to move, rotate, and stretch the manifold face to match the original. [Example of me doing it.](/facematching.mp4) It doesn't need to be exact, but make sure to check your material preview to make sure you have things the right way round. Rectangles can be completely upside down if you don't check!
 14. Rinse and repeat for every face on the model. Faces which don't exist on the original (usually underneath the model) you can just scrunch up into a random black area, it doesn't matter if they overlap. This sounds like an impossible task but it shouldn't take more than a few hours, although I completely admit it's tedious.
 
 
 # Only Written to this extent, the rest are simply draft notes for writing the rest.

<    3.  Match UVs
    4.  Separate
    5.  Make a stencil
        1.  Open your texture in an image editor
        2.  Change it to indexed color mode of as few as possible colors to preserve most of the features but get rid of most of the shading. Usually 2 or 3. How exactly to do this depends on your image editor, and should be fairly easy to look up
        3.  Change the background color to pure white. Again, depends on your image editor but selecting that color range and painting over it with white is what works best for me in Photoshop
        4.  Save this work of art. PNG is probably the best format here, but it shouldn’t matter too much as long as Blender can understand it
    6.  Mirror it back
    7.  **Make a copy**
    8.  Dumb garbage way
        1.  Tris to quads
        2.  **SAVE**
        3.  Subdivide surface simple (6 should be sufficient, you can try 7 but results may vary)
        4.  Displacement modifier
            1.  Can try both albedo and normal maps (normal should have a negative strength, albedo positive), but both will probably look pretty bad
            2.  Inspect results in solid view not material view
                1.  You *can* make changes to one of the texture files with an image editor like Photoshop to make a more useful displacement, but at that point you might as well do it the “proper” way
            3.  IF you’re happy with results (very big if)
                1.  Apply displacement modifier
                2.  SAVE
                3.  Merge vertices by distance
                    1.  0.02mm works for me, but do some trial and error
                4.  Planar decimate
                5.  Planar decimate yet again. Highest degree you can without losing too much detail
                6.  Export the model as an stl
                7.  Import into 3D builder
                8.  Have 3D builder fix it
    9.  “Proper” way
        1.  Bisect if symmetrical
        2.  Select some faces where you want to add detail
        3.  Select the knife tool
        4.  Make cuts in the faces along the texture lines
            1.  Yes, this is a long and tedious process, but remember the level of detail you capture is completely up to you. You don’t have to capture every tiny nook and cranny, and depending on the size you plan to print your printer might not even be able to recreate those anyway.
            2.  Can take days depending on your model and desired level of detail.
        5.  You will probably have a few levels of depth you’d like to extrude. I usually use 2 or 3
        6.  **Make a COPY**
        7.  Select all faces you’d like to extrude to the same depth, let’s say depth A.
            1.  Inset them to depth A
        8.  Repeat for depths B, C, and however more you have
        9.  Mirror
        10.  Export, import into 3D builder, and have it fix anything that might have gone wrong
        11.  Export it from 3D builder and it should be ready to print!>