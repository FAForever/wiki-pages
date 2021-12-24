This guide is intended to teach you how to get models for units to show
up in the game. This is also applicable to other meshes such as trees,
rocks, props and projectiles. We will only be covering aspects of
modelling specific to Supcom, and cover some common mistakes when
dealing with Supcoms specifics.

Requirements:

-   A knowledge of modelling - this guide will show the supcom-specific
    aspects of making the model. If you are new to modelling in general
    you should pick a software of your choice and become profficient in
    that first.
-   Blender or 3DSMax - Forged Alliance uses a proprietary mesh file
    format, and there are custom exporters written for these two
    programs. In our example, we will be using Blender to export the
    model for the game.
-   The appropriate Supcom exporter for the above program. The Blender
    version can be found
    [here](https://github.com/Exotic-Retard/SupCom_Import_Export_Blender)
    (blender 2.80+ not yet fully supported). The 3dsMax Version can be
    found
    [here](https://drive.google.com/drive/folders/0B606xLlwY0t4Q2NUUzVfVnB2a3c).

## Making The Model

While making your model, it is good to plan ahead so that you can save
yourself time when it comes to unwrapping and texturing it later, as
well as how it will move, if needed. To help guide us through the
process we will be following the development of the T3 ASF for the
Nomads faction, a custom faction added in a mod to Supcom.

The idea of the unit was worked out beforehand, and a complexity was
kept in mind - Supcom models are low poly, so making the models with as
few polygons as needed ensures that it wont suffer from performance
issues, while not compromising on quality beforehand. To get an idea of
how many polygons to use, export some models with similar uses from the
game and check how many they have.

-   Supcom uses Tri-based geometry, and does not support bezier curves,
    quads or solid geometry. So we will be using simple flat surfaces
    for the model.
-   In our case, the ASF of the other factions have 300-1100 vertices
    depending on the faction, with Seraphim being the most complex. So
    we don't want to end up with more complexity than that.
-   We know that our unit is going to be symmetrical, so we will be
    modelling only half of it and then duplicating it later, so that the
    UV unwrapping process is easier. To aid this we are splitting it in
    half early on in the process, and know which parts to keep identical
    in advance, such as its 4 wings.

<File:Model_Nomads_ASF01.png>\| A rough model of the ASF, in Sketchup.
This was just imported from Maya, along with some sample wing positions.
This will be cleaned up before being imported into Blender
<File:Model_Nomads_ASF02.png>\| The geometry has been completed. Note
the position of the origin and that the model has been modeled as two
mirrored objects. Some faces will be removed prior to importing.
<File:Model_Nomads_ASF03.png>\| The model as it is imported into
Blender. The model is split in half and some faces are cut away to save
on geometry, such as the front light and engine intakes.

### UV Unwrapping

The model needs to be unwrapped so that it can be textured. UV
unwrapping is not covered in this guide, but there are some
considerations:

-   Supcom uses one square texture per mesh, so when unwrapping ensure
    that all the UV faces are in the same material.
-   Typical texture sizes are 256x256 - 1024x1024. Lower for
    projectiles. In our case we will be using a 512x512 texture. Larger
    textures cause the game to slow down while loading them so they
    should be kept as small as possible.
-   Maximising the use of the texture is strongly encouraged, so
    designing units where textures are reused by faces, symmetrical
    geometry and culling uneeded faces is encouraged.

The basic unwrapping process is as follows:

-   Start with a model that has finished geometry as will be used in
    game.
-   Remove all faces that will be sharing texture coordinates, so that
    only one instance of each remains.
-   Unwrap all the faces in the left over model. Use simple unwrapping
    to ensure that the UV islands are not warped. This is especially
    important for hard surfaces.
-   Arrange all the islands in a horizontal line, in order of texture
    priority. The more visible faces will be larger and so should be
    placed first to ensure they have enough space.
-   Scale all the islands so that they would all roughly fit on the
    texture space.
-   If the model has treads (or other scrolling textures!), place them
    now according to the specification on the texture.
-   Arrange the islands on the texture space, starting with the highest
    priority islands.
    -   When placing, ensure that there is a 2px gap between the
        islands, and a 1px gap between the islands and the edge of the
        texture to avoid colours bleeding over.
    -   When placing, ensure that the most important edges of the UV
        islands are aligned orthogonally to minimise edge artifacts.
-   Once all textures are placed, duplicate the model geometry that was
    removed previously. The UV islands will be shared automatically.

<File:Model_Nomads_ASF04.png>\| A model of the ASF. Here, the model is
unwrapped before being mirrored. Highlighted are wing segments, which
show them using the same UV space for efficiency.
<File:Model_Nomads_MAA01.png>\| A model of the T1 Nomads AA/Arty ready
for export. Annotations detail how to avoid various pitfalls during the
process. Treads are placed at the bottom of the texture, and will scroll
when the unit moves. <File:Model_Nomads_MAA02.png>\| Tread scrolling
requires the textures to be placed as shown. Note the lack of gap from
the edge of the texture. Always check in game that the treads are
working correctly, they require correct sizing, spacing and orientation.

### Creating Bones

-   Supcom uses point bones that have an orientation, but no length. For
    this reason they may appear somewhat strange in Blender, whose bones
    also have a length. This is not an issue however.
-   The model needs to be rigged correctly, and all the bones should
    have a unique name. The base bone name will be what the exporter
    exports the mesh file as, but it can be renamed.
-   Bones with more than one parent are in theory supported by the
    engine but so far only single parent bones have been made to work.

### Animations

Animations are supported by supcom, but exporting them again makes them
hard to edit

### Texturing

Supcom has a custom texture set that has some quirks unique to the game.
The textures used depend on the shader - for example units have a
different set from projectiles, however the overall principles are the
same.

All textures should be made using the DTX5 format, for DDS textures.
They can be in theory any size, but sizes larger than 1024x1024 are not
recommended. The textures should be square, but dont have to be.

For units, the texture set is as follows (the shader is NOT physically
based):

-   Albedo - This is the base colour the unit uses. (Diffuse) It has 3
    channels, R,G,B. When converting from a PBR workflow, combining base
    colour and ambient occlusion tends to give good results.
-   SpecTeam - Units use a normal mapped shader, which also takes into
    account specular, reflectivity, and glow. The team colour is also
    added in this texture.
    -   R - Reflection - makes the texture more shiny, reflecting the
        sky. Glossiness (inverse of roughness) from a PBR workflow gives
        good results.
    -   G - Specular - makes the texture change colour according to its
        environment. If you use/can convert a specular/reflectivity
        channel from a metalness, this should give good results.
    -   B - Brightness - adds bloom to the texture, taking the colour
        from the base colour. Specific effect depends on the type of
        shader used. Useful for lights and glowing areas on the unit.
    -   A - Team colour - overrides the base colour with the colour of
        the units army.
-   NormalsTS - the game uses a non standard set up for normals. There
    are only two channels, X and Y. Z is calculated during runtime and
    is not needed. It is very important to get the orientation right,
    and can be very confusing when converting normal maps for use by
    Supcom.
    -   RGB - Y - White = UP - This is a greyscale input. All the rgb
        channels should be the same.
    -   A - X - White = LEFT - This is the alpha channel
    -   Furthermore, there appears to be a need to have the channels at
        different brightnesses. The RBG channel flat value is #080808,
        while to achieve a flat value on the alpha channel a value of
        #949494 is better. The conversion factor between them is 0.79 or
        1.27 (for use with the levels adjustment)