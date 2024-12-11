---
title: Tutorial
description: 
published: true
date: 2024-12-11T16:06:54.795Z
tags: 
editor: markdown
dateCreated: 2022-06-15T22:00:20.236Z
---

# FAF Tutorials
- [Git Repository](https://github.com/FAForever/faf-tutorials)

Tutorials will be mission-like. Currently BO tutorials are under development.
They will have their own tab in the client. Some UI design is needed.


## Game Mechanics
Tutorials introducing players to the FA.

## Challenges

Basically they are tests of your eco balance skills for new players:

1. Time Trial for most t1 tanks on limited number of mex and reclaim. (The Test lets you understand t1 power and build power)
2. Time Trial for fastest to reach 30 interceptors and 25 tanks. (Expands on the first test to teach balance between spam and air production)
3. Time Trial to produce 30 T1 interceptors and 15 t2 Gunships in 10 minutes) (Show the cost of t2 air and how t2 power is important)
4. Time Trial to get Full t3 Mex setup at your base in 20 minutes on a map like    Pyramid(Provides insight into what the minimum is to get t3 eco)

The real question is how much new players would be interested. It is less intimidating than playing vs trainers etc since some people seem to prefer to improve a bit before consulting trainers. The next would be getting high level players to try them on a defined map so that you can produce challenging times. 

## Build Orders

Tutorials showing map specific build orders to the players. Build order will be 5-10 minutes, just to know what to build at the beginning since everything else will rely on what the opponent is doing anyway.
Keep the builds simple! The goal is to give a clear guideline to new players. Standard could be 3 factories with acu and then walk. Special builds like the loki treegroup-reclaim build can be done in an advanced version.[Example](https://youtu.be/ridzpHQJy1Y)

Content:
- Map introduction
	- Camera moving around the map together with VOs explaining everything players need to know about the map.
- Example BO done by AI
	- Player should be able to select buildings/engineers to see command qeue
	- More VOs during the BO to explain what to build and why
- Player trying the BO

### Basic
This set of tutorials will be an introduction to the 1v1 (for now) games. It’s expected that the players already know the very basics of the game.
Maps should be newbie-friendly.
Preferably this maps should be for newbie ladder, so when a new player would search ladder, he would be getting only these maps that we have tutorials for. Should be around 10 maps.

#### Map List
To-do:
- Canis River
- Twin Rivers
- White Fire

In Process:
- Regor
- EotS
- Finns Revenge

Done:
- Theta
- Summer Duel
- 4 Leaf Clover
- Loki
 
## Client Requirements
Some nice UI with all available tutorials, split into categories. Currently there are only basic Build Order tutorials but the plan is to have all types of those.

There will be need for some text with basic information, what the tutorials are about. What they do and what not.
Description of the map and map preview would be nice as well.

Some of the tutorials might be just a text in the client since not everything requires launching the game. Right know I don’t know what’s the best approach for these so feel free to suggest that. If wiki is the way to go or w/e.

## Launching the tutorial
Tutorials can be launched directly using command line arguments.
What’s needed:
`/init init_tutorials.lua /map MapName`
No clan, number of games or rating is required. BUT saving the game.log in case something goes wrong.
The map name is the folder name of the map in the featured mod.
Server Requirements
- [Git repository](https://github.com/FAForever/faf-tutorials)
Tutorials mod will be similar to coop, packed in single file `tutorials.tut` with that there’s also a custom init file for them `init_tutorials.lua` All map tutorials are directly inside the mod. Since there won’t be replays, there’s no need to version all maps, but just the mod.

Since the game does not care where the map files are as long as they are properly linked in `scenario.lua` the mod doesn’t contain vanilla map files (.scmap). Question is if you can make it to download specific map from the vault when player tries to launch a tutorial on that map. This would reduce the side of the mod a lot as the scmap file is the 90% data of the map.
`Sure, the above is already being done for coop in the Python client, as long as the maps are in the map vault. -mazornoob`

Additional files for voices and videos will have to be downloaded as well. The mod will have 2 sound files for common VOs and videos or each of the VO (packed in file `FAF_TUT_Common_VO.nx2`, or any expansion that is needed). And then the same for each specific map (example `FAF_TUT_Theta_BO_VO.nx2`).
I think the best would be to always pack all voices and videos for one map together and download it if player tries to launch it. The client should be able to unpack the videos from that (right duke?)
Afaik it is possible to make the updater pick only some files and folders from the git repository and pack them. Currently the voices and videos are not in the repo but I can add them later if needed.

So to sum it up: when player tries to launch one tutorials it will download the custom init file, the packed mod `tutorials.tut`, packed common voices and videos for the tutorials and packed voices and videos specific for that map. (and the required map from the vault)

## Updating the mod
Init file should not require changes once it’s placed. But checking it for changes can’t hurt.

Version of the mod will be specified in `mod_info.lua`, updating the mod will update all the maps as well.

Updating VOs.

## How to contribute for non-LUA-People
### Map introductions
- Write down everything that should be said during the cinematics when the map is presented to the players.
	- Keep it in the blocks. One block of text should be one video shown on the screen. So not too long (1-5 sentences let’s say)
	- best is to write it directly in notepad++ or sublime using LUA-format
	- you can basically use this format: Code Example and change the text/blocks
	- watch out for the Syntax
	- don't forget to add a replay of the build you are explaining
- Include camera positions
	- Launch a game in sandbox mode. Alt-V will enable free camera movement, Space for tilting the camera.
	- F9 will open the game log. (you can’t be in fullscreen)
		- You can click on Clear to get rid of everything that is in the log currently
	- Open console as well (“~” (tilde sign) - key under Esc probably)
	- If you type in command DumpCamera into the console it will print the information needed about position and orientation into the log, you can copy paste it from there. 
	- [Example](https://puu.sh/umBBZ/329e0f237b.png)
  
## Localization
All tutorials are planned to be translated into all languages that FA currently supports.
You can keep an eye of these files and translate all strings in them. That means everything after = between “ “ symbols.
https://github.com/speed2CZ/faf-tutorials/tree/master/mods/tutorials/hook/loc

