---
title: FAF Map Editor Troubleshooting Guide
description: 
published: true
date: 2023-05-08T22:47:34.801Z
tags: mapping
editor: markdown
dateCreated: 2023-05-08T19:23:15.194Z
---

# Introduction
The map editor is a powerful tool for creating custom maps in Supreme Commander: Forged Alliance, but like with any software, you might encounter various technical issues that can prevent you from creating maps that meet your vision. These issues can range from minor annoyances to serious problems that make it impossible to complete your map. In this section, we'll cover some common technical issues you might encounter while working with the map editor and related files.

> This section focusses on the *FA Forever Map Editor* developed for FAF by Ozonex. While the editor is functional, the main developer has since left the FAF project. Resultingly, the editor is stuck in the alpha testing phase, and some features are lacking or broken. Other issues may result from inherent problems in the Forged Alliance base game, or are the consequence of the fact that we're working on a game released back in 2007. Consequently, while known fixes or workarounds exist for most problems, there are certain issues that may be difficult to overcome and may have to be accepted as hard limitations.
{.is-info}

## Error messages
| Error Message | Solution |
|-|-|
| Text | See [heightmaps](/en/map-development/faf-map-editor-troubleshooting#heightmaps) |
| | |

## Issues related to importing files

### Heightmaps
| Description | Cause | Workaround or fix |
|-|-|-|
| Heightmap is not accepted by editor | Heightmaps should be encoded as 16 bit, 1-channel, non-interlaced .raw files. | Check filetype and reencode heightmap as necessary
| | Heightmaps should be in the correct resolution (see figure). | Correct resolution |
<br />

### Custom textures
| Description | Cause | Workaround or fix |
|-|-|-|
| Custom texture is not accepted by editor | [Incorrect filetype](#t-i-f) | Textures need to be encoded as DXT3 (BC2) type .dds files. |
| | [Improper encoding](#t-i-e) | Textures need to be encoded as DXT3 (BC2) type .dds files, and include mipmaps. |
| | [File stored in wrong folder](#t-f-s) | Files should be stored under ../env/layers|

#### Incorrect filetype {#t-i-f}

#### Improper encoding {#t-i-e}

#### File stored in wrong folder {#t-f-s}

### Stratum masks
| Description | Cause | Workaround or fix |
|-|-|-|
| Stratum mask is not accepted by editor | [Incorrect filetype](#s-i-f) | Encode mask as 8bit RGB, non-interlaced .raw file. |
| | [Incorrect resolution](#s-i-r) | Adjust resolution of stratum mask. Check required resolution by exporting a stratum mask for that map and verifying resolution of exported file. |
| Stratum mask has odd artifacts such as stripes | Stratum mask was incorrectly encoded | Verify correct encoding. |
| Stratum mask is not displaying texture properly | Only greyvalues 128 and up are used. | If masks are made using external programs, rescaling using a levels adjustment is required. | 

#### Incorrect filetype {#s-i-f}
Masks need to be encoded as a RGB, non-interlaced, 8bit .raw file.
>While the heightmap is rendered as a 16bit file, masks are rendered as 8bit. 
{.is-warning}

#### Incorrect resolution {#s-i-r}
By default, stratum mask resolution is related to heightmap resolution, where 513px heightmaps required 512px stratum masks etc. However, if the map was edited within the original FA map editor, only 256px stratum masks will be accepted. To prevent this loss of resolution, try not to use the FA editor. The FA editor is commonly used for actions such as importing and positioning map-wide decals. Jip has created templates for 5km, 10km, and 20km maps containing several placeholding decals that can be replaced and which accept full-resolution stratum masks. These templates may be found here.

### Custom decals
| Description | Cause | Workaround or fix |
|-|-|-|
| Decal is not accepted by editor | Incorrect filetype | Encode decal as DXT3/BC2 .dds file. |
|  | File stored in wrong folder | Files should be stored under ../env/decals |


## Assorted Odd editor behaviour
| Description | Cause | Workaround or fix |
|-|-|-|
| ['Play Map' functionality isn't working](#PM) | Function has never worked | FAF may be started using the executable rather than the FAF client. Keeping the game open and using the <kbd>Restart game</kbd> button after saving any changes in the editor allows for quick testing. |
| [Map does not look the same in game as it does in editor](#MD) | The editor uses a different shader than the game. | No fix available. |
| [Decalls flicker when zooming in or out](#DF) | Large (local) differences in terrain elevation | Move offending decal to the bottom of the decal stack.  

#### 'Play Map' functionality isn't working {PM}
#### Map does not look the same in game as it does in editor {MD}
#### Decall flickering {#DF}

### Symmetry issues
Description:
Cause:
Workaround or fix: 

## Glossary
<dl>
  <dt>Ozonex editor or FAF editor</dt>
  <dd>This is the definition of the first term.</dd>
  <dt>FA editor</dt>
  <dd>This is one definition of the second term. </dd>
</dl>
