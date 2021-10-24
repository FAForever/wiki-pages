---
title: Tips-for-Modding-Efficiently
description: 
published: true
date: 2021-10-24T20:44:49.333Z
tags: 
editor: markdown
dateCreated: 2021-08-31T09:45:32.416Z
---

## Introduction

Following are some ideas about how to get started modding quickly. This is more about how to set up an efficient cycle for rapid development, and less about technically how to do things.

## Development

For an IDE, a decent option is to use Visual Studio (free) with BabeLua installed. You get syntax highlighting looks like this:

![vs.syntax.png](/images/modding/vs.syntax.png){.align-center}
To work out what LUA commands are available
- See the Other Sources section in the [Modding](Modding "wikilink") page. The spreadsheet there contains every global function call in the game. Search through it to find what you want.
- The existing LUA source code from the base game is found in the files lua.scd and moholua.scd, which is in the gamedata folder of your FA installation. Unzip these files and index the folder.Then you can search quickly for a keyword across the whole code base. This is handy when you are trying to work out how to use a function - you can find existing usages of it.
- Try and think of a mod that does something similar, go through its code

## Starting a game

Launch your game with this command line:
`C:\\ProgramData\\FAForever\\bin\\ForgedAlliance.exe /init init_faf.lua /nobugreport /log "c:\\yourdirectory\\game.log" /EnableDiskWatch`
- /log will allow you to view the log easily as it is saved to disk.
- /EnableDiskWatch will ask FA to reload your changes whenever the file is changed - skipping the need to reload your game.
- /init allows you change it to run your code on startup for some low level stuff. For now just keep it at the default init_faf.lua

Run your game in windowed mode
- You can see log error messages in real time
- You can swap between code and game

Run your skirmish with
- Cheats enabled - so you can use cheat menu (ALT F2) to spawn units and swap teams
- Game speed adjustable - so you can speed it up with +/-/\* keys
- Sandbox mode - so you don't have to mess with AI

## Testing your mod

Create a shortcut key to execute the console command AI_INSTABUILD. When it is on you will instantly build anything. It is much quicker to just build things than to spawn them using the cheat menu.

You can copy and paste units with ctrl-shift-c and ctrl-shift-v. Copying actually saves a script to your keyboard. When you paste it the script it executed. So you can save that script (paste into notepad) and retrieve it many days later... allowing you to retest with similar units next time.

The ctrl-shift-v "paste" shortcut will actually invoke any script in keyboard, is not limited to pasting units.

You can restart a skirmish with ctrl-f10.

## Creating a test loop

Create a [mod test loop](mod_test_loop "wikilink") that allows you to test your code instantly.

## Dealing with errors

If you get an error,
- Save time by searching for "Concat". This jumps to a LuaConcat error which you can think of as a compiler error - it happens because the code is broken syntactically.
- Sometimes the game will have a huge infinite error stream. Try restarting (ctrl-F10) and clearing the log, or just pausing. The error will still be in the log file.
- The log window (displayed with F9) seems to wrap once the log gets big. This gets very confusing when you start seeing errors that were from last game iteration. Whenever you restart,

## Hanging the game
- It is possible to hang the game or crash with a fatal exception.
- You can run this in a command line to instantly close FA, even if it is hung: taskkill /IM forgedalliance.exe /F
- A leading cause of hanging the game is when you LOG-repr an object that is from C++. To avoid this create your own, safe log call:
```Lua
function SafeLog(o) for k, v in o do LOG(k .. " = " .. tostring(v)) end
end
```