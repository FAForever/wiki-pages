**This is experimental** and works from Client version 0.16.1-rc.1
onwards. (Python Client only)

The Python Client can use either OpenGL or ANGLE/D3D for rendering
itself. By default, it will use ANGLE+DX9. You can change this by
editing System Environment Variables.

To switch between OpenGL and ANGLE, set the 'QT_OPENGL' variable to
"desktop" or "angle" respectively.

When using ANGLE, the 'QT_ANGLE_PLATFORM' variable can be used to switch
between DX9, DX11, and software rendering, by setting the variable to
"d3d9", "d3d11" or "warp".

<figure>
<img src="Env_vars_start.png" title="Env_vars_start.png" width="200" alt="Env_vars_start.png" /><figcaption aria-hidden="true">Env_vars_start.png</figcaption>
</figure>

To get to the Environment variables dialog, open your start menu and
type "Environment", and you will see links to "Edit environment
variables"

Alternatively you can press win+r and write/paste "rundll32
sysdm.cpl,EditEnvironmentVariables" and press enter.

You will first have to add the environment variables using the "New..."
button, and then afterwards use "Edit..." button to edit variables.

**Important**: After editing an environment variable, you must close the
"Environment Variables" Window (by clicking "OK") and then restart the
FAF Client.

## Examples

Environment set for OpenGL rendering:

![Environment set for OpenGL
rendering](Env_vars_desktop.png "Environment set for OpenGL rendering")

Environment set for ANGLE warp (software) rendering:

![Environment set for ANGLE warp
rendering](Env_vars.png "Environment set for ANGLE warp rendering")