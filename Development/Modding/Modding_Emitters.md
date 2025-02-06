---
title: Modding Emitters
description: 
published: true
date: 2025-02-06T12:42:49.216Z
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

Supreme Commander uses a particle system for all kinds of special effects. The base entity in this system is the emitter. As the name would suggest, the emitter emits particles, as well as holds all the information about itself and the particles. Emitters are stored in dedicated blueprint files.

> Working with emitters requires manipulating game files, so follow the steps on github to setup a FAF development environment on your system. Once that is done, work with emitters can start. Remember that if you get stuck on any step of the process, you can always ask for help from the community - either on the forums or in the discord server.
{.is-info}

## Creating a particle emitter

<div style="display: flex">
  
  <p style="padding-right: 2%; text-align: justify">
    Creating a particle emitter is quite simple. Simply run the game from your development environment, and start a skirmish game - consider enabling cheats and sandbox mode, as well as disabling fog of war (particles can't be seen if they are hidden by the fog of war by default). Once in game, press "Ctrl + Alt + E", and a default emitter will spawn at the position of your mouse. In addition to that, a separate "Emitter Editor" window should open. It often gets "hidden" behind the game window, so you might have to move it around to be able to access it. Multiple screens make it much easier to handle, but you can also set your game to windowed mode, and reduce its size. 
  
  </p>

  <img src="/particle-emitter/default-emitter.png"/>
  
</div>

> If you can not see the default emitter and its particles, which resemble a fire (see image above), it probably means the particles aren't being rendered - make sure to zoom in more, and that the emitter wasn't created inside fog of war. You can also disable the "Only Emit if Visible" option in the LOD menu or increase the LOD Cutoff Distance.
{.is-danger}

## Emitter editor

Emitter editor is your primary tool for determining particle looks and behavior. You could also directly edit an emitter blueprint file, but that is in general slower, and you don't get the instant feedback you do with the editor. Lets take a look at all the parts of the editor and explain how they work.

![default-emitter-editor-marked.png](/particle-emitter/default-emitter-editor-marked.png)


---


<div style="font-weight: bold; font-size: 130%; color:rgb(220, 50, 40)">
[1] The menu bar
</div>

The menu bar holds three items: File, Options and LOD.
**_File_** menu allows for creating a new, saving and opening existing emitter blueprints, as well as holding the action buttons to load texture and ramp files to the emitter.
**_Options_** menu has a lot of additional options affecting how generated particles behave:
- **Use Local Velocity:** *TBD*
- **Use Local Acceleration:** *TBD*
- **Gravity:** *TBD*
- **Lock Particles to Velocity:** *TBD*
- **Interpolate Emitter Position:** *TBD*
- **Align Initial Rotation to the Bone:** *TBD*
- **Particles are flat in world space:** *TBD*
- **Snap To Waterline:** *TBD*
- **Only Emit on water:** *TBD*
- **Enable Particle Resistance:** *TBD*

**_LOD_** menu holds 3 options that affect particle rendering:
- **Only Emit if Visible:** particles won't be emitted if the emitter is not within camera PoV (including LOD Cutoff Distance)
- **Catch up when Visible:** particles that would have been 
- **Only Create if Visible:** *TBD*


___


<div style="font-weight: bold; font-size: 130%; color:rgb(250, 220, 100)">
[2] Emitter and particle variables
</div>

This second section of the emitter editor contains some variables that define fixed parameters for the emitter and particles. In addition to this, it features a timeline. The fixed parameters are:
- **Life Time:** the life time of the **emitter** , measured in game ticks (1/10th of seconds). Setting it to a negative value makes it infinite (default -1). Value of 0 disables the emitter.
- **Repeat Time:** length of the **emitter cycle**, measured in game ticks.
- **Blend mode:** ***TBD**, has to do with how rendering of particles is done*
- **Fidelity:** determines at which video fidelity level the emitter will emit.
- **Frame Count:** determines how many frames a strip of texture has (in how many pieces a texture should be chopped up vertically).
- **Strip Count:** determines how many strips a texture has (in how many pieces a texture should be chopped up horizontally).
- **Sort Order:** ***TBD** (probably to do with which particles render first)*
- **LOD Cutoff Distance:** determines how far the camera can move from the emitter before it stops emitting and rendering particles.
- **Playing:** is used to pause/play the emitter cycle. Note it does not stop the emitter from emitting, just from cycling. Useful for checking how the emitter behaves in a particular part of its cycle. Life time must be a positive value.

**The Cycle timeline** shows the span of the emitter's **cycle** and the current time in the cycle (marker). The marker can be moved around (ideally while paused) to observe the emitter's behavior at any given point in its cycle.

In addition to the variables above, this part of the interface also displays the path for the currently used Texture and Ramp files. These can be changed in the **File menu** as mentioned in <span style="font-weight: bold; font-size: 100%; color:rgb(220, 50, 40)">[1]</span>. Note that the name is often cutoff for longer texture/ramp file paths.
___
As is mentioned in the "Repeat Time" description, emitters have a cycle. Cycles have a certain amounts of steps, and the total amount of steps determine both the length and the resolution of a cycle. The length and the resolution, in turn, determine how the particles emitted in a particular moment of the emitter's life time will look like, as defined by a particular property curve. Let's take a look at our base particle that was modified in a few ways. First, what you can not see from the gif below is that the **Emit Rate** was increased to 4. Additionally, **Life Time** and **Repeat Time** were both set to 40, and the **Particle End Size** was set to be a constant 0.2.

You can see that the **Particle Start Size** curve was modified to contain two points (instructions on how to do this later). The first point is at *tick = 10* with *value = 0.2*, and the second is at *tick = 30* and *value = 1.8*. Note how this affects the shape of the curve. It is flat from the start (left) to the first point, as well as from the 2nd point to the end (right), and has a constant slope in between the two points. As the name suggest, this variable determines how large the particle is at the beginning of the **particle's lifetime**, and the function determines how this value is changed over the **emitter's cycle**. And we can see that behavior in the GIF below - the particles are initially emitted with a starting scale of 0.2. Then, when the mark on the timeline reaches 10th tick, they start slowly growing to 1.8 scale until the cycle mark reaches the 30th tick. When it does, the particles stop growing, and maintain the 1.8 scale.

Note how a "point" is formed towards the top of the column of particles. This is because the *Particle End Size* curve is just a flat line with *value = 0.2* as previously mentioned, meaning particles will always end being size of 0.2, regardless of how big they start off.

![emitter-cycle-showcase_2.gif](/particle-emitter/emitter-cycle-showcase_2.gif)

So what happens when an **emitter's** lifetime is different from its repeat time? In case the life time is less than repeat time, then the particular property will only be simulated partially. If we reduced Life Time in the example above to 20, that would result in the last particle emitted to have **Particle Start Size** value equal to 1.0 - half way along the curve, which coincides with middle of the rising part of the function (between 0.2 and 1.8).

If, on the other hand, the life time is longer than repeat time, then our "timeline" will be cycled through multiple times (and possibly partially as well, if the two times aren't a multiple of each other). Note that there's no automatic smooth transition, so if we had a life time of 80 in the case above, after the 40th tick, the particles emitted on the 41st tick would have the **Particle Start Size** value equal to 0.2 (the start value of the function).

The image below depicts how the total span of the timeline (defined by **Repeat Time**) projects onto a property curve. 

<span id="emitter_curve">![emitter-cycle-showcase.png](/particle-emitter/emitter-cycle-showcase.png)</span>


___


<div style="font-weight: bold; font-size: 130%; color:rgb(150, 190, 240)">
[3] Property curves
</div>

Property curves part of the editor is where a lot of things can be tweaked. Note that all of the curves follow the same emitter cycle principle - how far along the cycle you are projects onto how far along the property curve you are, and that value is used for the particle that is **_generated in that moment_** - again, we are editing the emitter's behavior over time, and not the behavior of the particles themselves. Particles will change in time, but based on fixed parameters which are determined at the moment the particle is created. Once a particle is created, we can not affect it any more.

### The Curve editor
Curve editors are same for all the properties. They have 5 parameter boxes as well as a curve manipulation panel. The panel itself displays 5 values in addition to the curve itself (see <a href="#emitter_curve">previous image</a>). The values are:
- **Parameter name** (top-left)
- **Window Max** (top) and **Window Min** (bottom)
- 1st (indexed 0, on the left) and last (right) tick of the **emitter cycle**.

**Window Min** and **Window Max** values affect both the "zoom" level of the parameter curve, but also the minimum and maximum **Value** we can set for any of the nodes of the curve. They can be found and edited on the right above the curve panel [or using the mouse wheel to scroll - not very precise].

The curve itself is a segmented red line, which has nodes serving as ends points. Additionally, the left and right edge of the curve panel serve as a node, which has the same parameters as the node closes to that edge. Currently selected nodes are represented with a cyan square, while other nodes are represented with a red square. A selected node can be edited with the 3 parameters to the left and above of the curve panel:
- **Tick:** represents the ticks position of the node. You can think of it as the x-axis of the curve graph.
- **Value:** represent the value of the parameter of the node. You can think of it as a y-axis of the curve graph.
- **Range:** is, in essence, an integrated randomness generator. It defines the total offset from the defined **Value** a parameter can have - minimum being *-**Range** / 2*, and maximum being *+**Range** / 2*. Upon generating a particle, a random value between ***Value** - **Range** / 2* and ***Value** + **Range** / 2* is chosen.

While node parameters can be edited via the 3 fields, you can also edit them directly in the curve panel using your mouse. By LMB clicking on the panel, the closest node x-axis-wise is selected (true for other mouse-actions) and moved to the position of the mouse. If you hold the LMB down, you can move the node around in both the x (Tick) and y (Value) directions. You can edit the Range value of a node by holding the MMB down and moving your mouse up and down.

Adding nodes is done by clicking with the RMB anywhere on the panel, and a new node will be added at your mouse position. If you want to remove a node, you can use the Ctrl + RMB

> Mouse controls for the curve adjustment:
LMB - move a node around, changing its Value and Timing
MMB - drag to adjust the Range parameter of a node
RMB - create a new node
Ctrl + RMB - delete a node
Scroll - change Min and Max values (centered on their average)
{.is-info}

### The Properties


Let's look at what type of properties we can manipulate first. The properties themselves are split into several tabs, so we'll group them like that in this documentation as well, with the exception of first two tabs, which will be grouped together.

---
Below this is a work in progress.
___

#### Spacial
Even though this is not the first tab, it will be covered first. The reason is that, as the name would suggest, spacial parameters determine the position the particles when they are first emitted - their origin. To affect the particle spawn position, we have 4 parameters:
- **Emitter Size:** defines a radius centered around emitter position. Particles will spawn randomly within this radius.
- **X Position:** offset of the spawn point from the emitter position in X-axis (horizontal).
- **Y Position:** offset of the spawn point from the emitter position in Y-axis (vertical).
- **Z Position:** offset of the spawn point from the emitter position in Z-axis (horizontal).

> Note the order of axis in the emitter editor menu: it's X, Y and then Z. The Y axis is used to define vertical parameters, an this will be true of all parameters that will be discussed in this document. The X and Z are the two horizontal components.
{.is-info}


#### Direction, Rate, Lifetime & Forces
These two tabs contain values that determine particle rate and life time, as well as how they move in relation to their origin.
- **Emit rate:** determines how often a particle is emitted. The rate is ***Emit Rate** / 1 Tick*. Note that if this value is greater than 1, several particles are emitted in a span of a single tick, and if the value is equal or less than 1, a particle is emitted at the end of the time span (if the rate is 0.2, particles will be emitted at the 5th, 10th, etc. tick, and not 1st, 6th, etc. tick).
- **Lifetime:** determines how long (measured in ticks) a particle will exists after it was emitted.

The three direction properties, together with the **Velocity** property from the Forces tab, determine how fast and in what direction the particle will move. In general, you can assume that the final velocity of a particle is determined as a vector sum of the three cardinal direction vectors. Each of the cardinal vectors can be determined by multiplying the Velocity value with the direction value of the particular direction. In that sense, the three direction properties are simply factors for the Velocity value. Additionally, the acceleration properties function as one might expect - they determine how a particle's speed will change over time.
- **Velocity:** determines the base speed of a particle
- **X and Z Direction:** are factors that determine the direction and intensity of the velocity vector in the flat plane
- **Y Direction:** is a factor that determines the particle's vertical velocity component.
- **X, Y and Z Acceleration:** determines the acceleration of a particle. 
- **Resistance:** *TBD*

#### Size and Rotation
Size and rotation parameters are quite self-explanatory. Note that the size parameters are scale factors of the particle texture:
- **Particle Start Size:** determines size of a particle when first emitted.
- **Particle End Size:** determines the size of a particle at the end of its lifetime (as determined by Lifetime parameter).
- **Particle Rotation:** determines the starting orientation of the particle, measured in degrees.
- **Particle Rotation Rate:** determines the rate of rotation of a particle, measured in degrees/tick.

Note that the particle will smoothly change its size between the start and end value, as well as smoothly rotate (dependant on framerate, and not ticks).

#### Animation and Selection
Animation and selection tab parameters allow us to manipulate the texture and the ramp files used by our emitter. You may only attach a single texture and a single ramp file to each emitter. Lets first tackle the ramp file, since it's arguably simpler if you don't have previous experience with sprites.

The ramp file is a simple *.dds* image file that is used to "color" the texture file. The guide will get into all the possible "Blend" modes later, but for now we will use the "Add" blend mode. The way the emitter system uses the ramp is as follows:
The width of the ramp_file.dds is subdivided to represent the lifetime of a particle. Let's assume we have a ramp file that is a single row of pixels which is 50 pixels wide. If the 