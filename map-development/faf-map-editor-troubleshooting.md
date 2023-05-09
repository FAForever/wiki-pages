---
title: FAF Map Editor Troubleshooting Guide
description: 
published: true
date: 2023-05-09T10:25:36.585Z
tags: mapping
editor: markdown
dateCreated: 2023-05-08T19:23:15.194Z
---

# Introduction
The map editor is a powerful tool for creating custom maps in Supreme Commander: Forged Alliance, but like with any software, you might encounter various technical issues that can prevent you from creating maps that meet your vision. These issues can range from minor annoyances to serious problems that make it impossible to complete your map. In this section, we'll cover some common technical issues you might encounter while working with the map editor and related files.

> This section focusses on the *FA Forever Map Editor* developed for FAF by Ozonex. While the editor is functional, the main developer has since left the FAF project. Resultingly, the editor is stuck in the alpha testing phase, and some features are lacking or broken. Other issues may result from problems inherent to the Forged Alliance base game, or are the consequence of the fact that we're working on a game released back in 2007. Consequently, while known fixes or workarounds exist for most problems, there are certain issues that may be difficult to overcome and may have to be accepted as hard limitations.
{.is-info}

## Error messages
| Error Message | Cause |
|-|-|
| Invalid MIP level | [Custom texture misses correct number of mipmaps](#t-sm)|


## Issues related to importing files

### Heightmaps {#h}
| Description | Cause | Workaround or fix |
|-|-|-|
| Heightmap is not accepted by editor | Heightmaps should be encoded as 16 bit, 1-channel, non-interlaced .raw files | Check filetype and reencode heightmap as necessary
| | Heightmaps should be in the correct resolution (see figure) | Correct resolution |
<br />

### Custom textures {#t}
| Description | Cause | Workaround or fix |
|-|-|-|
| Custom texture is not accepted by editor | [Incorrect filetype](#t-if) | Textures need to be encoded as DXT3 (BC2) type .dds files. |
| | [Improper encoding](#t-ie) | Textures need to be encoded as DXT3 (BC2) type .dds files, and include mipmaps. |
| | [File stored in wrong folder](#t-fs) | Files should be stored under ../env/layers|

#### Incorrect filetype {#t-if}
#### Improper encoding {#t-ie}
#### Texture size and mipmaps {#t-sm}
For unknown reasons, custom textures might result in the 'Invalid MIP level' error when used in stratum layer 1. As a result, the editor replaces the whole layer with a grey colour. While the map is unaffected when viewed in game, the map-preview image will be similarly affected.

Replacing the texture with a default texture and using the custom texture in stratum layer 2–8 provides a workaround for this issue.

#### File stored in wrong folder {#t-fs}
<br />

### Stratum masks {#s}
| Description | Cause | Workaround or fix |
|-|-|-|
| Stratum mask is not accepted by editor | [Incorrect filetype](#s-if) | Encode mask as 8bit RGB, non-interlaced .raw file. |
| | [Incorrect resolution](#s-ir) | Adjust resolution of stratum mask. Check required resolution by exporting a stratum mask for that map and verifying resolution of exported file. |
| Stratum mask has odd artifacts such as stripes | Stratum mask was incorrectly encoded | Verify correct encoding. |
| Stratum mask is not displaying texture properly | Only greyvalues 128 and up are used. | If masks are made using external programs, rescaling using a levels adjustment is required. | 

#### Incorrect filetype {#s-if}
Masks need to be encoded as a RGB, non-interlaced, 8bit .raw file.
>While the heightmap is rendered as a 16bit file, masks are rendered as 8bit. 
{.is-warning}

#### Incorrect resolution {#s-ir}
By default, stratum mask resolution is related to heightmap resolution, where 513px heightmaps required 512px stratum masks etc. However, if the map was edited within the original FA (GPG) map editor, only 256px stratum masks will be accepted. To prevent this loss of resolution, try not to use the GPG editor. The GPG editor is commonly used for actions such as importing and positioning map-wide decals. Jip has created templates for 5km, 10km, and 20km maps containing several placeholding decals that can be replaced and which accept full-resolution stratum masks. These templates may be found here.
<br />

### Custom decals
| Description | Cause | Workaround or fix |
|-|-|-|
| Decal is not accepted by editor | Incorrect filetype | Encode decal as DXT3/BC2 .dds file. |
|  | File stored in wrong folder | Files should be stored under ../env/decals |
<br />

## Assorted odd editor behaviour
| Description | Cause | Workaround or fix |
|-|-|-|
| ['Play Map' functionality isn't working](#PM) | Function has never worked | FAF may be started using the executable rather than the FAF client. Keeping the game open and using the <kbd>Restart game</kbd> button after saving any changes in the editor allows for quick testing. |
| [Map does not look the same in game as it does in editor](#MD) | The editor uses a different shader than the game. | No fix available. |
| [Decalls flicker when zooming in or out](#DF) | Large (local) differences in terrain elevation | Move offending decal to the bottom of the decal stack. |
| [Symmetry-relation between pairs of markers or objects is lost](#SR) | Symmetry tolerance set too low | Increase symmetry tolerance|

#### 'Play Map' functionality isn't working {#PM}
#### Map does not look the same in game as it does in editor {#MD}
#### Decall flickering {#DF}
#### Symmetry-relation between pairs of markers or objects is lost {#SR}
<br />

## Glossary
See [Glossary](/en/Glossary)
