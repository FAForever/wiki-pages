---
title: Command Line Switches
description: Command line switches let you run Forged Alliance with extra options and settings.
published: true
date: 2026-09-15T10:51:34.209Z
tags: modding, development
editor: markdown
dateCreated: 2021-08-31T09:42:35.315Z
---

Supreme Commander will accept many command line switches. You can set them up in your windows shortcut. This is a partial list, with some explanations.

## Setting up a skirmish using command line

### Standard switches

You can automaticly launch a skirmish right after launching the game. To do that, you need to specify a map. The other switches are optional.

| **Command Line Switch** 	| **Description** 	|
|---	|---	|
| /map map_folder 	| Set the map 	|
| /faction faction 	| Set your faction<br>- 1 = UEF<br>- 2 = Aeon<br>- 3 = Cybran<br>- 4 = Seraphim    	|
| /victory "victory_condition" 	| Set victory conditions<br>- demoralization = Assassination<br>- domination = Supremacy<br>- eradication = Annihilation<br>- sandbox = Sandbox  	|
| /nofog 	| Set fog to None 	|
| /blackfog 	| Set fog to Unexplored 	|
| /predeployed 	| Set pre-built units to On 	|

Example:
`SupremeCommander.exe /map SCMP_019 /faction 3 /nofog /victory "domination"`

### Custom switches

You can create your own switches :

1.  hook *`lua/SinglePlayerLaunch.lua`*
2.  go to line 175
3.  add your switch detection code

Example:
```lua
if HasCommandLineArg("/gamespeed") then
	options['GameSpeed'] = GetCommandLineArg("/gamespeed", 1)[1]
end
```
This will allow you to adjust game speed with the following switch :
`/gamespeed "`*`gamespeed`*`"`


Set game speed ("normal", "fast" or "adjustable")

## Other switches

| Command Line Switch | Description |
|-----------------------------|-------------------------------------------------------|
| `/aqtime`                     | Non-functional due to engine patch. |
| `/audition`                   | For XACT auditioning server                                                                                                                                                                                                                     |
| `/bugreport`                  | Enables bugsplat for the top level exception filter, overriden by `/nobugreport`. |
| `/data`                       |                                                                                                                                                                                                                                                  |
| `/debug`                      | Opens Lua debugger window at startup. |
| `/D3D10`                      | Use D3D10 rendering |
| `/EnableDiskWatch`            | The game engine will monitor all files on the disk, and if it detects a change, it will attempt to re-load that file immediately, if possible. This allows instant in-game updates of things like unit blueprints.                               |
| `/edit`                       | Opens the Moho Log at startup. Unknown difference from `/showlog`, which is typically used instead. |
| `/exitongameover`             | Application will exit when the game is over                                                                                                                                                                                                      |
| `/file`                       | Unkown |
| `/framerate <fps>`                  | Sets max framerate at startup. |
| `/gameoptions [<option_key>:<value>...]` | Allows setting individual game options like so: `/gameoptions CheatsEnabled:true GameSpeed:adjustable` |
| `/genpath`                  | Enables path generation debug logging. |
| `/gpgnet <address>`              | Connects to gpgnet |
| `/gpgnetdev`                  | Uses a gpgnet client in the directory `C:/work/rts/main/code/src/Multiplayer/MultiplayerClient/bin/Debug/MultiplayerClient.exe` |
| `/hook`                     |    Unkown |
| `/hostgame <protocol> <port> <player_name> <game_name> <map_file>`| Launches the game using `StartHostLobbyUI` in `/lua/ui/uimain.lua` |
| `/init <initFile>`          |  Defines init file that mounts game content and, in FAF, adjusts process priority. |
| `/interlocked`                | Force the sim and UI threads to run interlocked at startup. Equivalent to game console command `sim_Interlocked` |
| `/joingame <protocol> <address> <player_name>` | Launches the game using `StartJoinLobbyUI` in `/lua/ui/uimain.lua` |
| `/load <save_file>`                      | Launches the game into a saved game. |
| `/loadrulesandexit`           | Loads the game rules defined in `RuleInit.lua` at startup and then exits |
| `/log <log_file>`           | Logs messages to the given file.                                                                                                                                                                                                                 |
| `/mediacenter`                | Launches windows media center at startup. |
| `/networksafe`                | Unknown |
| `/nobugreport`                | Disables bugsplat for the top level exception filter, overrides `/bugreport`. |
| `/noinitialunits`             | Makes the lua function `ShouldCreateInitialArmyUnits` return `false` |
| `/nologbox`                   | Unknown.                                                                                                                                                                                                                                                 |
| `/nomass`                     | Disables checking mass deposit occupancies for structures.  |
| `/nomovie`                    | Disable all pre-rendered movies                                                                                                                                                                                                                  |
| `/nomusic`                    | Sets "music" category volume to 0 at startup |
| `/noprops`                    | Disables initial prop generation from map data |
| `/nosound`                    | Disables sound engine entirely |
| `/novalidate`                 | Do not test for minimum system requirements |
| `/p4yes`                      | Unknown functionality, but related to auto-accepting prompts from Perforce version control. |
| `/perf`                       | Performance test (same as /map PerfTest) |
| `/position <X> <Y>`           | Set the game window position to (*X*, *Y*) |
| `/prefs <prefs_file>`         | Uses the given file for preferences instead of `%localappdata%/Gas Powered Games/Supreme Commander Forged Alliance/Game.prefs` |
| `/profile <name>`          | Uses the profile in the prefs file with the given name, setting `NetName` if the profile exists, or otherwise creating a new profile using `/lua/user/prefs.lua` `CreateProfile` |
| `/purgecache`                 | Clears out the shader cache in `%localappdata%/Gas Powered Games/Supreme Commander Forged Alliance/cache` at startup. |
| `/replay <replay_file>`     | Plays the given replay file. Example: `/replay "C:\\My Replays\\Me vs The Bad Guys.SupremeCommanderReplay"` or `/replay "C:/ProgramData/FAForever/cache/temp.scfareplay"`|
| `/savereplay <replay_file>` | Save the replay to the given file. Does not work for skirmishes started with /map *map_folder* - you have to hook *lua/SinglePlayerLaunch.lua* and edit sessionInfo.createReplay = true (in function SetupCommandLineSkirmish) for this to work. |
| `/scenario <map_scenario_file>`                   | Equivalent to `/map` |
| `/showlog`                   | Shows the log window at startup                                                                                                                                                                                                                  |
| `/size <X> <Y>`               | Sets the main window's size |
| `/softwareinstancing`         | Force software instancing for mesh batches. Also accessible in-game with `mesh_Rebatch` console command. |
| `/sounds`                    | Unknown |
| `/spewbp`                     | Logs initialization process for blueprints. |
| `/spewsound`                  | Enable debug logging of sound information. Also accessible in-game with `snd_SpewSound` |
| `/sse2`                       | If available, use SSE2 parallel SIMD instructions |
| `/synclog <folder_path>`    | Folder to save sim logs about each synced beat. Logs are saved to a new folder per session. Stores only the last 70 beats unless `sim_keepAllLogFiles` is enabled in the in-game console. |
| `/tutorials`                  | Unknown |
| `/waitfordebugger`            | Pauses startup until the user clicks ok so that they can attach a debugger |
| `/windowed <X> <Y>`           | Start game in a window, with an *X*x*Y* resolution |
| `/xactdebug`                  | Starts xact debug process at startup |

Other Switches