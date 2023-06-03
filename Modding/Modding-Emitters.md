Supcom uses particle systems for its special effects - each particle is
defined by an emitter - it contains info on everything needed to create
a stream of particles and their properties.

-   to better understand this it can be helpful to open the debug
    emitter creation tool in supcom - the default key binding should be
    **crtl+alt+e** and cheats are required to be on. It shows the
    parameters as interactive graphs which is much easier to visualize
    -   left clickin on a curve moves the nearest point to your mouse
        position
    -   right clicking on a curve adds a point
    -   shift clicking or something changes the points z value, or
        "thickness"

The emitter consists of an emitter blueprint with multiple base values,
and curves. Curves are the way its values change over time, and be
affected with scripts too.

-   curves have an x, y, z value
-   the x value changes over the lifetime of the particle
-   the y value is changed according to the x-reference, and different y
    values at different times can be set in the blueprint or via script.
-   the z value is the range of the y values to randomly pick/merge
    depending on the curve in question

The emitter creates a particle with the specified texture, in greyscale,
and colours it with a ramp. The ramp is a dds file that defines its
colour and opacity. The game scans through its pixels and uses the
colour and opacity of a pixel its referencing to recolour the texture.

-   The x value in the ramp changes over the lifetime of the particle
-   The y value in the ramp changes with the Ramp Selection Curve value
    of the particle, from top to bottom - a y value of 0 is the top
    pixel and a y value of 1 is the bottom pixel.
    -   The pixels are blended so the colours can change smoothly,
        rather than just reading the nearest pixel value
    -   because of how it works, the edge (top and bottom) strips need
        to be at least 2px high to get the pure colour and not a blend
    -   with a properly set up ramp texture its possible to change to
        any colour on the fly, allowing for features like emitters
        coloured by the army colour of a player.
