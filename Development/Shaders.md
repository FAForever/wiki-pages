## General

Basically a shader processes the information stored in textures and
performs mathematical operations on them to produce the image that you
see on your screen.

Shaders can be divided into pixel shaders and vertex shaders. Vertex
shaders alter the position of the vertices of the mesh, e.g. the
deformed wrecks after a unit has died. Pixel shaders define the color of
the surfaces. When people speak about „shaders“, most of the time they
mean pixel shaders.

The shaders for Forged Alliance are written in HLSL (high level shading
language) and the code is stored in .fx files in the *effects.nx2*
archive in the gamedata folder. *Mesh.fx* contains the shaders for the
buildings and units in the game.

When starting the game, the shaders are compiled and stored in a cache
folder in *C:\\Users\\Your_Username\\Appdata\\Local\\Gas Powered
Games\\Supreme Commander Forged Alliance*. When the shader files are
edited, the files in the cache need to be deleted to trigger a recompile
at game start.

Shaders are no rocket science, but they involve vector algebra. You
should be familiar with the concept of vectors and know what a dot
product and normal vecors are to understand the shader code.

The shader code is evaluated on all points of the surface with the
specified shader. To produce variation on the surfaces, textures are
used to control the shaders result. Each evaluation uses the color of
the texure at this particular point of the object. Most Pixelshaders in
this game return an RGB-color and an alpha value. The alpha value is
used by the engine to determine how much bloom is added when the color
is bright.

## Textures

Every unit has a diffuse texture (also called albedo) that basically
stores the color of the surface, and a normal map that fakes geometric
details. There is also a specular texture (sometimes referred to as
teamcolspec) that is used to store four greyscale textures in a single
RGBA texture:

-   The red channel determines how much the environment map is
    reflected.
-   The green channel determines how much the sunlight is reflected.
-   The blue channel controls where the areas with bloom are. (These
    generally also have a white albedo color, but not always)
-   The alpha cannel determines where the army color influences the
    albedo texture.

In HLSL the channels of a texture can be accessed like so:

*exampletexture.r* returns the red channel of the texture as a float
value between 0 and 1.

*exampletexture.rgb* returns the red green and blue channel as a vector
with three float values.

The environment map is basically a picture of the sky. In other games it
is sometimes called the skybox. It is used to make shiny materials look
believable. Note that the environment map can be different from the sky
texture that you see in the game, if the mapmaker was not paying
attention.

Every map has a sunlight and an ambientlight (the light that comes from
the sky from all directions). There are no dynamic lights in supreme
commander.

## Editing Shaders

The best way to understand the shaders is to look at the code and then
to alter a line and see how the changes look in game. You can specify a
different shader for each fidelity setting, so if you copy paste the
shader and make single edits you can compare the canges ingame by
switching between the fidelity settings. (the console command
Graphics_fidelity comes in handy here. 0 is low, 1 is medium and 2 is
high). Also look at the textures of a unit to see where which texture is
applied.

The names of the factions in the shader files do not always match the
usual faction name. Insect refers to Cybran, UnitFalloff is used for
Seraphim and NormalMapped is for UEF. A trailing PS indicates a pixel
shader, a trailing VS indicates a vertex shader.
