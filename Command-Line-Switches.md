---
title: Command Line Switches
description: 
published: true
date: 2021-12-30T02:20:16.401Z
tags: modding
editor: markdown
dateCreated: 2021-08-31T09:42:35.315Z
---

Command line switches let you run Forged Alliance with extra options and settings.

Supreme Commander will accept many command line switches. You can set them up in your windows shortcut. This is a partial list, with some explanations.

## Setting up a skirmish using command line

### Standard switches

You can automaticly launch a skirmish right after launching the game. To do that, you need to specify a map. The other switches are optional.

<table>
<thead>
<tr class="header">
<th><p>Command Line Switch</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>/map <em>map_folder</em></p></td>
<td><p>Set the map</p></td>
</tr>
<tr class="even">
<td><p>/faction <em>faction</em></p></td>
<td><p>Set your faction</p>
<dl>
<dt></dt>
<dd>1 = UEF
</dd>
<dd>2 = Aeon
</dd>
<dd>3 = Cybran
</dd>
</dl></td>
</tr>
<tr class="odd">
<td><p>/victory "<em>victory_condition</em>"</p></td>
<td><p>Set victory conditions</p>
<dl>
<dt></dt>
<dd>demoralization = Assassination
</dd>
<dd>domination = Supremacy
</dd>
<dd>eradication = Annihilation
</dd>
<dd>sandbox = Sandbox
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p>/nofog</p></td>
<td><p>Set fog to None</p></td>
</tr>
<tr class="odd">
<td><p>/blackfog</p></td>
<td><p>Set fog to Unexplored</p></td>
</tr>
<tr class="even">
<td><p>/predeployed</p></td>
<td><p>Set pre-built units to On</p></td>
</tr>
</tbody>
</table>

Example:
`SupremeCommander.exe /map SCMP_019 /faction 3 /nofog /victory "domination"`

### Custom switches

You can create your own switches :

1.  hook *`lua/SinglePlayerLaunch.lua`*
2.  go to line 175
3.  add your switch detection code

Example:

`if HasCommandLineArg("/gamespeed") then`
`options['GameSpeed'] = GetCommandLineArg("/gamespeed", 1)[1]`
`end`

This will allow you to adjust game speed with the following switch :
`/gamespeed "`*`gamespeed`*`"`


Set game speed ("normal", "fast" or "adjustable")

## Other switches

| Command Line Switch         | Description                                                                                                                                                                                                                                      |
|-----------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| /aqtime                     |                                                                                                                                                                                                                                                  |
| /audition                   |                                                                                                                                                                                                                                                  |
| /bugreport                  |                                                                                                                                                                                                                                                  |
| /data                       |                                                                                                                                                                                                                                                  |
| /debug                      | Opens the debugging tool at startup                                                                                                                                                                                                              |
| /D3D10                      |                                                                                                                                                                                                                                                  |
| /EnableDiskWatch            | The game engine will monitor all files on the disk, and if it detects a change, it will attempt to re-load that file immediately, if possible. This allows instant in-game updates of things like unit blueprints.                               |
| /edit                       |                                                                                                                                                                                                                                                  |
| /exitongameover             | Application will exit when the game is over                                                                                                                                                                                                      |
| /file                       |                                                                                                                                                                                                                                                  |
| /framerate                  |                                                                                                                                                                                                                                                  |
| /genpath                    |                                                                                                                                                                                                                                                  |
| /gpgnet                     |                                                                                                                                                                                                                                                  |
| /gpgnetdev                  |                                                                                                                                                                                                                                                  |
| /hook                       |                                                                                                                                                                                                                                                  |
| /hostgame                   |                                                                                                                                                                                                                                                  |
| /init                       |                                                                                                                                                                                                                                                  |
| /interlocked                |                                                                                                                                                                                                                                                  |
| /joingame                   |                                                                                                                                                                                                                                                  |
| /load                       |                                                                                                                                                                                                                                                  |
| /loadrulesandexit           |                                                                                                                                                                                                                                                  |
| /log "*log_file*"           | Logs messages to the given file.                                                                                                                                                                                                                 |
| /mediacenter                |                                                                                                                                                                                                                                                  |
| /networksafe                |                                                                                                                                                                                                                                                  |
| /nobugreport                |                                                                                                                                                                                                                                                  |
| /noinitialunits             |                                                                                                                                                                                                                                                  |
| /nologbox                   |                                                                                                                                                                                                                                                  |
| /nomass                     |                                                                                                                                                                                                                                                  |
| /nomovie                    | Disable all pre-rendered movies                                                                                                                                                                                                                  |
| /nomusic                    | Set music to Off                                                                                                                                                                                                                                 |
| /noprops                    |                                                                                                                                                                                                                                                  |
| /nosound                    | Set sound to Off                                                                                                                                                                                                                                 |
| /novalidate                 | Do not test for minimum system requirements                                                                                                                                                                                                      |
| /p4yes                      |                                                                                                                                                                                                                                                  |
| /perf                       | Performance test (same as /map PerfTest)                                                                                                                                                                                                         |
| /position *X* *Y*           | Set the game window position to *X*x*Y*                                                                                                                                                                                                          |
| /prefs *prefs_file*         | Uses the given file for preferences instead of Game.prefs                                                                                                                                                                                        |
| /profile *profile*          |                                                                                                                                                                                                                                                  |
| /purgecache                 |                                                                                                                                                                                                                                                  |
| /replay "*replay_file*"     | Plays the given replay file. Example: /replay "C:\\My Replays\\Me vs The Bad Guys.SupremeCommanderReplay"                                                                                                                                        |
| /savereplay "*replay_file*" | Save the replay to the given file. Does not work for skirmishes started with /map *map_folder* - you have to hook *lua/SinglePlayerLaunch.lua* and edit sessionInfo.createReplay = true (in function SetupCommandLineSkirmish) for this to work. |
| /scenario                   |                                                                                                                                                                                                                                                  |
| /showlog                    | Shows the log window at startup                                                                                                                                                                                                                  |
| /size *X* *Y*               | Set a *X*x*Y* resolution. Example: /size 1024 768                                                                                                                                                                                                |
| /softwareinstancing         |                                                                                                                                                                                                                                                  |
| /sounds                     |                                                                                                                                                                                                                                                  |
| /spewbp                     |                                                                                                                                                                                                                                                  |
| /spewsound                  |                                                                                                                                                                                                                                                  |
| /sse2                       |                                                                                                                                                                                                                                                  |
| /synclog                    |                                                                                                                                                                                                                                                  |
| /tutorials                  |                                                                                                                                                                                                                                                  |
| /waitfordebugger            |                                                                                                                                                                                                                                                  |
| /windowed *X* *Y*           | Start game in a window, with a *X*x*Y* resolution. ex: /windowed 1024 768                                                                                                                                                                        |
| /xactdebug                  |                                                                                                                                                                                                                                                  |

Other Switches