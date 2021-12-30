---
title: Modding
description: 
published: true
date: 2021-12-30T02:26:55.076Z
tags: modding
editor: markdown
dateCreated: 2021-12-25T00:03:29.141Z
---

Supreme Commander is extensible by [mods](/Game-Modifications-(Mods)), which can alter the whole gameplay (like PhantomX for example), change the balance of units, display information to the user or make the user automatically do things like renaming units or send messages to his allies when he starts upgrading. This is a page for you to get a basic idea of modding FA.

See also [Tips for Modding Efficiently](/Modding/Tips-for-Modding-Efficiently).

### What we need

- The Supcom FA installation files
- A texteditor, preferably one with syntax highlighting. Notepad++ or Sublime do fine, a full IDE like IntelliJ with a LUA plugin is fine aswell
- Basic LUA knowledge

### Basic information
- Supcom FA is using LUA
- Mods are usually stored in C:\\Users\\%USERNAME%\\Documents\\MyGames\\Gas Powered Games\\Supreme Commander Forged Alliance\\Mods
- Every mod needs a mod_info.lua file in its folder, containing infos such as Name, Description, UID etc.
- Mods usually have a hook folder (usually /hook, can be configured to have another path in the mod_info) which contains all files that the user is hooking to (overwriting or adding code)
- There is a SIM and a UI mod category. Sim mods affect everybody and usually alter the gameplay, so as example PhantomX and any balancemod is a sim mod. UI mods don't affect other players (directly), as example notify is messaging them about your upgrade,   but it's not altering their game
- The game files (.scd) aswell as the FAF mod files (.nx2, ...) are all just renamed .zip files. You can copy them somewhere to work with, rename their extension and unzip them to see their content.
- You can use the default hotkey F9 to open the live LOG in your game, and use LOG(text), SPEW(text) or WARN(text) in your code to print to it

### Lua Information
- Here you can find a bunch of Functions in this [LUCADOC](/Modding/LUADOC)
- Here are some more Lua Global Functions [Lua.Globals](/Modding/LUAGLOBALS)

### Differences to default LUA

There are some things different to default LUA:
- The # sign is used to comment in FA, the #mytable operation to get its length is not possible, you can use table.getn(mytable) instead
- it's not necessary but still possible to use "for i, v in ipairs(mytable) do", "for i, v in mytable do" works aswell

### Sim and UI
![sim-ui.png](/images/modding/sim-ui.png){.align-right}
Basically, this game is divided in two interacting components, Sim and UI. Both are moddable, here is some info:
- The Sim (simulation) of the game happens for every player and is deterministic, so the same input will always yield the same result, that is why the players in a multiplayer game usually do not desync. Many mods introduce changes that affect all players equally, every balance change does this.
- The UI (user interface) component only has a part of the information that the Sim side is calculating. For example which units the user has, their health and vet points, and what they are ordered to. Orders about your opponent's units are also calculated on your PC, in the Sim, but your UI has no info about it. The UI also displays these infos, resulting for example in the ecopanel or the scoreboard.

Both sides are interacting, to keep the user updated about what's happening to his (and his allies') units, and to inform the Sim about what orders the user issued. This is done via two files:
- SimCallbacks.lua is used by UI operations to inform the Sim about something it should know (commands, pings, ...) 
- UserSync.lua is used by the Sim to inform the UI about something it should know (eco, unit info, pings from teammates, ...)

## Basic examples
### A simple mod_info.lua
Explanation
```lua
`name: mod name`
`uid: an ID every mod needs, you can generate a random one for example here: `[`https://www.uuidtools.com/`](https://www.uuidtools.com/)
`version: use a versioning pattern of your choice, the current FAF mod vault will only display a single integer though`
`copyright: mention how you want copying to be treated`
`description: mod description`
`author: your name`
`url: if you have one, for example a forum thread that you could be making to show us your mod`
`selectable: true|false : whether the mod should be selectable in the ingame lobby`
`enabled = true|false`
`exclusive = true|false:`
`ui_only = true|false: whether all players need to mod for the game to run. SIM mods are needed by everyone, UI mods not`
`requires = {}: table of requirements for your mod (for example "common mod tools"), enter the UIDs here`
`conflicts = {}: table of conflicts, this way the lobby will warn the player that they don't work together`
`before = {}: mods that will have to be hooked in before your mod is hooked`
`after = {}: mods that have to be hooked in after your mod`
```
Filled example
```lua
`name = "Tutorial Mod Info"`
`uid = "431a0114-92a0-11e5-8994-feff819cdc9f"`
`version = 1`
`copyright = "nah, just copy it"`
`description = "A new description"`
`author = "Myxir"`
`url = ""`
`selectable = true`
`enabled = true`
`exclusive = false`
`ui_only = true`
`requires = {}`
`conflicts = {}`
`before = {}`
`after = {}`
```
### Understanding Hooking
Our way into modding the game is hooking. Hooking in FA is basically file concatenation, that means that the file we're hooking to will be extended by our file.

Paths:
```lua
`\lua\ui\game\selection.lua is a UI side file handling what happens when we (de)select units`
`C:\Users\%USERNAME%\Documents\My Games\Gas Powered Games\Supreme Commander Forged Alliance\Mods\examplemod\hook\lua\ui\game\selection.lua is the full path to my own file, how i hook it`
`"/mods/examplemod/" is the path the mod can find its own files later`
```
Ok so now i want to hook that file, i have created an empty selection.lua in the path as mentioned above. As said, hooking is file concatenation, so my empty file will be added at the bottom of the original selection.lua. Now i can overwrite a function, let's take PlaySelectionSound, which is playing the sounds of a selection when you select something.
```lua
`-- original selection.lua file`
`function PlaySelectionSound(newSelection)`
`   -- the newSelection parameter is the table of units`
`   -- original code not displayed`
`end`
```
Let's say i want it to do nothing, so i can just destructively hook (overwrite) it completely in my own selection.lua:
```lua
`-- my own selection.lua file in /mods/examplemod/hook/lua/ui/game`
`function PlaySelectionSound(newSelection)`
`end`
```
As this is simple file concatenation, my own function has the exact same name of the original function, but is mentioned later and is thus overwriting it. In result, nothing happens, no sound is played.

If i want to add something, instead of overwrite, i can construtively hook the function by saving a reference and calling the "old" function via that
```lua
`-- my own selection.lua file in /mods/examplemod/hook/lua/ui/game`
`local oldPlaySelectionSound = PlaySelectionSound`
`function PlaySelectionSound(newSelection)`
`   oldPlaySelectionSound(newSelection)`
`   -- here i can execute my own code`
`end`
```
## FAQ

>Q: I can't find files in the /lua path which should be there! Where are they?
>A: Likely in the mohodata or schook folders (.scd files), they are mounted to the /lua path aswell

## Debugging

This section is to help you debug your mods and scripts. If you're creating a mod, and run into some errors, hopefully this will help you find a workaround.

### Handling LazyVars

This is quite a common issue with FA. Usually, LazyVars are related to the User Interface of FA. This sub-section will help you find out how to debug LazyVars and what's causing issues with your User Interface code.

The first thing you need to do is find out what's causing your error. LazyVars don't provide any helpful error exceptions by default, but this can be changed.

Navigate to: C:\\Program Files (x86)\Steam\steamapps\common\Supreme Commander Forged Alliance\gamedata and open mohodata.scd with either 7zip or WinRAR.

Once you have opened the SCD file, find a file called 'lazyvar.lua' and open it with any text editor (Recommended: Notepad++ or Sublime Text 3) Be sure to make a back-up of this file before you make any changes as this may cause you to desync in public games when playing FAF.

With the file open, locate the variable "ExtendedErrorMessages = false" and change it to "ExtendedErrorMessages = true".

Save the file and a nice message should pop up:
![dca0f1768fc5ec5808b58b45809f92b0.png](/images/modding/dca0f1768fc5ec5808b58b45809f92b0.png)
Click yes and close the archive.

Now, when you open up your game again, you will find that your console (F9) will provide error exceptions related to "LazyVars".

## Further Reading
modding [Shaders](/Modding/Shaders)
modding [Emitters](/Modding/Modding_Emitters)