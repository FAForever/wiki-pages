---
title: 3D Printing Models
description: 
published: true
date: 2024-05-13T23:34:34.351Z
tags: 
editor: markdown
dateCreated: 2024-05-13T23:21:07.574Z
---

# Step 1: Find the unit you want to print

### Figure out its unit ID

1\. If it’s an unmodded unit

![](/images/learning/3d_print_guide/uef_engineer_id.png)

Unit ID for UEF T1 Engineer is UEL0105

    a. Find it on the unit db [_https://unitdb.faforever.com/_](https://unitdb.faforever.com/)

    b. Find its unit ID, hovering over the unit should make the ID pop up in the bottom 

2\. If it’s a modded unit

![](/images/learning/3d_print_guide/basilisk_id.png)

Unit ID for the Basilisk is BRL 0401

    a. Host a sandbox game with the mod you want and cheating enabled

    b. Once you launch hit Alt-F2 to open the unit spawn menu

        i. This may get intercepted by other software like GeForce Experience. You can change this in the keybinds menu. Search for “create units”

1.  Filter or search for the unit you want and take note of the unit ID
2.  If it’s a default unit
    1.  Go to steam, right click on Forged Alliance, and manage > browse local files
    2.  Go to the gamedata folder and find units.scd
    3.  Copy this folder into a new folder where you’ll be working from
    4.  Rename it to units.zip
    5.  Unzip these folders
3.  If it’s a FAF unit, such as T3 MAA or a support factory
    1.  Open the client, click on the hamburger menu in the top left, and then select show data folder
    2.  Go to FAForever > Gamedata and find units.nx2
    3.  Copy this folder into a new folder where you’ll be working from
    4.  Rename it to units.zip
    5.  Unzip this folder
4.  If it’s a modded unit
    1.  Have the mod downloaded (duh)
    2.  Open the client, click on the hamburger menu in the top left, and then select show mods folder
    3.  Go to the mod you want, and copy the units folder into your working folder
5.  Download blender 4.1 (or whatever version is most current, this guide will be written using 4.1) https://www.blender.org/download/
6.  Add supcom mesh importer to Blender [_https://github.com/Solstice245/scstudio_](https://github.com/Solstice245/scstudio)
    1.  Instructions are in that link so I will not rewrite them here
7.  Launch Blender
    1.  Delete the default cube
    2.  File > Import > Supcom Mesh (.scm)
    3.  Navigate to the units folder you got in steps 2-4, then the unit ID for your unit of choice, select the file ending in \_lod0, and hit Import SCM
    4.  You should now have a blobby gray representation of your unit
    5.  Left click on it to select it if it isn’t already, right click, and select Shade Flat, this will make all the faces visible
        1.  Don’t worry you’re not removing any detail, it just turns off Blender’s smoothing in the preview
        2.  Those pyramids with spheres are called bones, and are used for posing the model (like making an ACU mid-walk). Posing models is out of scope for this guide, so you can just hide them by clicking the eyeball next to your model in the top right. If you do want to pose your model and know how to, make sure you do so before step 9 as this will remove the bones.
8.  Make sure it’s selected, click on material, then new
    1.  Click on the yellow dot next to Base Color, then select Image Texture
    2.  Select Open Image then navigate to the unit’s folder and select the one ending in \_Albedo.dds
    3.  Click on this button to open material preview and your unit should now be shaded
9.  Making it manifold
    1.  \[What does manifold mean?\]
    2.  Download 3D builder
        1.  [_https://apps.microsoft.com/detail/9wzdncrfj3t6?hl=en-us&gl=US_](https://apps.microsoft.com/detail/9wzdncrfj3t6?hl=en-us&gl=US)
    3.  Select your model in blender, export it as an STL, make sure only selection is enabled
    4.  Open the model in 3D builder
    5.  An error should pop up, have it repair the model
    6.  Export it again as an stl
    7.  Import it back into blender, don’t replace the old model
    8.  Mesh bisect if model is symmetrical
    9.  Planar bisect, ~2° should be sufficient
    10.  Merge vertices by distance
    11.  Fine tune some geometry to make manifold or easier to print
    12.  Triangulate faces
10.  Adding detail
    1.  Smart uv unwrap
    2.  Join with previous model
    3.  Match UVs
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
        11.  Export it from 3D builder and it should be ready to print!

![](https://lh7-us.googleusercontent.com/jogimI1d5iwfMKArcpr4cOxpszpR3ZzPADrmMe6Qbow3xRlrU2I5wLv6oWAtSPBirPLNcmiHKgU8MRSsOFrmgmz2iW7wnsNnuqAdFzW0CCvASkBgr9dOnRE1JCi_w-SwVyZqgo8V4VzU4gdOkCQjR8I)