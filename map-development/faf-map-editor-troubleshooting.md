---
title: FAF Map Editor Troubleshooting Guide
description: 
published: true
date: 2023-05-08T22:23:32.943Z
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
| Custom texture is not accepted by editor | Incorrect filetype | |
| | Improper encoding | Textures need to be encoded as DXT3 (BC2) type .dds files, and include mipmaps. |
| | Files stored in wrong folder | Files should be stored under ../env/layers|
<br />

### Stratum masks
| Description | Cause | Workaround or fix |
|-|-|-|
| Stratum mask is not accepted by editor | Incorrect filetype | Encode mask as 8bit RGB, non-interlaced .raw file.[[1]]() |
| | Incorrect resolution | Adjust resolution of stratum mask. Check required resolution by exporting a stratum mask for that map and verifying resolution of exported file.[[2]]() |
| Stratum mask has odd artifacts such as stripes | Stratum mask was incorrectly encoded | Verify correct encoding. |
| Stratum mask is not displaying texture properly | Only greyvalues 128 and up are used. | If masks are made using external programs, rescaling using a levels adjustment is required. | 

[1] While the heightmap is rendered as a 16bit file, masks are rendered as 8bit.
[2] By default, stratum mask resolution is related to heightmap resolution, where 513px heightmaps required 512px stratum masks etc. However, if the map was edited within the original FA map editor, only 256px stratum masks will be accepted. To prevent this loss of resolution, try not to use the FA editor. The FA editor is commonly used for actions such as importing and positioning map-wide decals. Jip has created templates for 5km, 10km, and 20km maps containing several placeholding decals that can be replaced and which accept full-resolution stratum masks. These templates may be found here.

### Custom decals
| Description | Cause | Workaround or fix |
|-|-|-|
| Decal is not accepted by editor | Incorrect filetype | Encode decal as DXT3/BC2 .dds file. |
| Decal is visible in editor | Incorrect filetype | Encode decal as DXT3/BC2 .dds file. |


## Assorted Odd editor behaviour
### 'Play Map' functionality isn't working
Description:
Cause:
Workaround or fix: 
Function has never worked. No workaround or fix available.
### Map does not look the same in game as it does in editor
Description:
Cause:
Workaround or fix: 
The editor uses a different shader than the game. No fix available.
A limited workaround is available by starting the FAF-version of the game without using the launcher, and using the 'restart game' button to quickly refresh the map in game. 
### Decall flickering
Description:
Cause:
Workaround or fix: 
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
