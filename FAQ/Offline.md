---
title: Playing FAF Offline
description: 
published: true
date: 2026-09-23T07:30:06.921Z
tags: 
editor: markdown
dateCreated: 2021-11-02T18:22:18.621Z
---

# How to Play FAF Offline
## Windows
All you need to play the FAF offline is to create a shortcut to

`C:\ProgramData\FAForever\bin\ForgedAlliance.exe`

and run it. If the game crashes, you may have to run `C:\\ProgramData\\FAForever\\bin\\ForgedAlliance.exe` as administrator (this comes with a security risk, especially if you obtained FAForever from an untrusted source). If you run the game offline you will not have access to some features such as autodownload of missing maps/mods from the vault or automated saving of replays to the FAF replay vault (although you should still be able to access the replay from the last offline game on your hard drive).

If you want to play a coop mission in single player you need to "host" it once through the FAF client (co-op tab), so that it downloads the relevant files. Once you get to the in-game lobby you can close the game. You need to do this once for each mission you want to play. Every time you want to play singleplayer: Start the game with the /init init_coop.lua command line switch or shortcut. Begin the mission from the **skirmish** screen and change the map to select a different (downloaded) mission. Resume saved progress from the campaign screen.

For an example of command line switches, the following will open FAF offline, disable the intro movies, show the 'moho log' window, and create a log (offlineDev.log) in the same folder:
`C:\ProgramData\FAForever\bin\ForgedAlliance.exe /init init_faf.lua /EnableDiskWatch /showlog /nomovie /log  offlineDev.log`

## Linux
Locate the "run-offline" file in the faf-linux folder, and run this.

You can also edit this to add command line switches, similarly to a windows shortcut. For example, the following code will open FAF offline, disable the intro movies, show the 'moho log' window, and create a log (offlineDev.log) in the same folder:


`#!/usr/bin/env bash`

`basedir=$(dirname "$(readlink -f "${BASH_SOURCE[0]}")")`
`"$basedir/launchwrapper" ~/.faforever/bin/ForgedAlliance.exe /init "${@:-init_faf.lua}" /EnableDiskWatch /showlog /nomovie /log offlineDev.log`

If playing via steam, an example of the offline replay folder location is as follows:
`/home/[username]/.steam/steam/steamapps/compatdata/9420/pfx/drive_c/users/steamuser/Documents/My Games/Gas Powered Games/Supreme Commander Forged Alliance/replays/[profile name]`