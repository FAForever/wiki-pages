---
title: Modding Emitters
description: 
published: true
date: 2024-06-23T17:31:55.157Z
tags: modding
editor: markdown
dateCreated: 2021-10-24T20:36:49.905Z
---

# Modding Emitters
Supcom uses particle systems for its special effects - each particle is defined by an emitter - it contains info on everything needed to create a stream of particles and their properties.
- To better understand this it can be helpful to open the debug emitter creation tool in supcom - the default key binding should be crtl+alt+e and cheats are required to be on. It shows the parameters as interactive graphs which is much easier to visualize
	- Left clickin on a curve moves the nearest point to your mouse position
	- Right clicking on a curve adds a point
	- Shift clicking or something changes the points z value, or "thickness"

The emitter consists of an emitter blueprint with multiple base values, and curves. Curves are the way its values change over time, and be affected with scripts too.
- Curves have an x, y, z value
- The x value changes over the lifetime of the particle
- The y value is changed according to the x-reference, and different y values at different times can be set in the blueprint or via script.
- The z value is the range of the y values to randomly pick/merge depending on the curve in question

The emitter creates a particle with the specified texture, in greyscale, and colours it with a ramp. The ramp is a dds file that defines its colour and opacity. The game scans through its pixels and uses the colour and opacity of a pixel its referencing to recolour the texture.
- The x value in the ramp changes over the lifetime of the particle
- The y value in the ramp changes with the Ramp Selection Curve value of the particle, from top to bottom - a y value of 0 is the top pixel and a y value of 1 is the bottom pixel.
	- The pixels are blended so the colours can change smoothly, rather than just reading the nearest pixel value
	- Because of how it works, the edge (top and bottom) strips need to be at least 2px high to get the pure colour and not a blend
	- With a properly set up ramp texture its possible to change to any colour on the fly, allowing for features like emitters coloured by the army colour of a player.

---
WIP expansion on the article:

---

Supreme Commander uses a particle system for all kinds of special effects. The base entity in this system is the emitter. As the namee would suggest, the emitter emits particles, as well as holds all the information about itself and the particles. Emitters are stored in  dedicated blueprint files.

> Working with emitters requires manipulating game files, so follow the steps on github to setup a FAF development environment on your system. Once that is done, work with emitters can start. Remember that if you get stuck on any step of the process, you can always ask for help from the community - either on the forums or in the discord server.
{.is-info}

## Creating a particle emitter
Creating a particle emitter is quite simple. Simply run the game from your development environment, and start a skirmish game - consider enabling cheats and sandbox mode, as well as disabling fog of war (particles can't be seen if they are hidden by the fog of war by default). Once in game, hold "Ctrl + Alt + E", and a default emitter will spawn in on the position of your mouse. In addition to that, a separate "Emitter Editor" window should open. It often gets "hidden" behind the game window, so you might have to move it around to be able to access it. Multiple screens make it much easier to handle, but you can also set your game to windowed mode, and reduce its size.
![default-emitter.png](/particle-emitter/default-emitter.png)
![default-emitter-editor-marked.png](/particle-emitter/default-emitter-editor-marked.png)

> If you can not see the default emitter and its particles, which resemble a fire, it probably means the particles aren't being rendered - make sure to zoom in more, and that the emitter wasn't created inside fog of war. You can also disable the "Only Emit if Visible" option in the LOD menu.
{.is-danger}

## Emitter editor
Emitter editor is your primary tool for determining particle looks and behavior. You could also directly edit an emitter blueprint, but that is in general slower, and you don't get the instantaneous feedback. Lets look at all the parts of the editor and explain how they work.
### [1] The menu bar
The menu bar holds three items: File, Options and LOD.
**File** menu allows for creating a new, saving and opening existing blueprints, as well as holding the action buttons to add a texture and a ramp file to the emitter.
**Oprions** menu has a lot of additional options affecting how generated particles behave:
- Use Local Velocity: *TBD*
- Use Local Acceleration: *TBD*
- Gravity: *TBD*
- Lock Particles to Velocity: *TBD*
- Interoplate Emitter Position: *TBD*
- Align Initial Rotation to the Bone: *TBD*
- Particles are flat in world space: *TBD*
- Snap To Waterline: *TBD*
- Only Emit on water: *TBD*
- Enable Particle Resistance: *TBD*

**LOD** menu menu holds 3 options that affect particle rendering:
- Only Emit if Visible: particles won't be emitted if camera distance is furthen than the LOD Cutoff Distance
- Catch up when Visible: *TBD*
- Only Create if Visible: *TBD*
### [2] Emitter and particle variables
This second section of the emitter editor contains some variables that define fixed parameters for the emitter and particles. In addition to this, it features a timeline. The fixed parameters are:
- Life Time: the life time of the **emitter** , measured in game ticks (1/10th of seconds). Setting it to -1 makes it infinite.
- Repeat Time: length of the emitter cycle, measured in game ticks.
- Blend mode: *TBD*
- Fidelity: determines at which video fidelity level the emitter will emit.
- Frame Count: *TBD*
- Strip Count: *TBD*
- Sort Order: *TBD*
- LOD Cutoff Distance: determines how far the camera can move from the emitter before it stops emitting and rendering particles.
- Playing: used to pause/play the emitter cycle. Note it does not stop the emitter from emitting, just from cycling.

In addition to the variables above, this part of the interface also displays the path for the currently used Texture and Ramp files. These can be changed in the **File menu** as mentioned in [1].

As is mentioned in the "Repeat Time" description, an emitter has a cycle. Cycles have a certain amounts of steps, and the total amount of steps determine both the length and the resolution of a cycle. The length and the resolution, in turn, determine how the particles emitted in a particular moment of the emitter's life time will look like, as defined by a property curve. Let's take a look at our base particle that was modified in a few ways. First, what you can not see from the gif below is that the **Emit Rate** was increased to 4. Additionally, **Life Time** and **Repeat Time** were both set to 40, and the **Particle End Size** was set to be a constant 0.2.

You can see that the **Particle Start Size** curve was modified to contain two points (instructions on how to do this later). The first point is at *tick = 10* with *value = 0.2*, and the second is at *tick = 30* *(ignore the small .08 error)* and *value = 1.8*. Note how this affects the shape of the curve. It is flat from the start (left) to the first point, as well as from the 2nd point to the end (right), and has a constant slope in between the two points. As the name suggest, this variable determines how large the particle is at the beginning of the **particle's lifetime**, and the function determines how this value is changed over the **emitter's cycle**. And we can see that behavior in the GIF below - the particles are initally emitted with a starting scale of 0.2. Then, when the mark on the timeline reaches 10th tick, they start slowly growing to 1.8 scale until the cycle mark reaches the 30th tick. When it does, the particles stop growing, and maintain the 1.8 scale.
Note that a "point" is formed towards the top of the column of particles. This is because the *Particle End Size* curve is just a flat line with *value = 0.2* as previously mentioned, meaning particles will always end being size of 0.2, regardless of how big they start off.



![emitter-cycle-showcase_2.gif](/particle-emitter/emitter-cycle-showcase_2.gif)