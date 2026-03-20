---
title: Creating UI Mods
description: How to create a mod for the User Interface
published: true
date: 2026-03-20T09:44:01.969Z
tags: modding
editor: markdown
dateCreated: 2026-03-20T09:08:55.909Z
---

# Introduction

If you want to create UI mods from scratch, it can be unclear where the proper entry points into the UI or where data from the Sim is acquired by the UI. There can also be difficulties in debugging. This page introduces the UI framework and how to avoid these issues.

### Prerequisites
You should already know how to structure a mod and hook files from the [general modding introduction](/Development/Modding/Modding).

## Entry points to hook

The general introduction teaches that you can hook files and functions, but what do you hook when you want to create a UI mod? While you can hook functions for existing UI elements, this does not let you create a mod from scratch.

### In what order is the UI executed?
1. Front End: This includes everything outside of a game session, such as the lobby and the main menu. It starts from [uimain.lua](https://github.com/FAForever/fa/blob/develop/lua/ui/uimain.lua) using one of the callbacks at the top of the file. UI mods cannot access this part of the code since they are not set active yet. The front end and game session UIs run different lua states, so to get information between them, there is `SetFrontEndData` and `GetFrontEndData` (used for replay ID, replay filenames, and campaign briefings) and the Prefs file (used by mod manager and FAF client to record active UI mods).
2. Session init: This uses [SessionInit.lua](https://github.com/FAForever/fa/blob/develop/lua/SessionInit.lua) sets up user lua state when starting a new game session, which includes assigning UI mods as active, so after this step UI mods start functioning.
3. Create World UI Provider: The function [`StartGameUI` from `uimain.lua`](https://github.com/FAForever/fa/blob/cf1d6940b62ed8344b95a3d6cdb6be4cc3c31649/lua/ui/uimain.lua#L111) is called, and its main job is to create the "World UI Provider", an object that has the lua callbacks for the loading phases of the game (loading game Sim rules ("in transit" screen), waiting for other players, and finally create the game interface).
4. Create Game Interface: The [`CreateGameInterface` callback in the UI Provider](https://github.com/FAForever/fa/blob/33ef66dc35887bd9fa2051b183927533bc1b3ed4/lua/ui/game/gamemain.lua#L536) runs when the game finishes loading. The main function of interest is [`CreateUI` of `gamemain.lua`](https://github.com/FAForever/fa/blob/33ef66dc35887bd9fa2051b183927533bc1b3ed4/lua/ui/game/gamemain.lua#L153).

### What to hook
In order of importance:
- If you want to create an entirely new UI element, you would want to hook [`CreateUI` of `gamemain.lua`](https://github.com/FAForever/fa/blob/33ef66dc35887bd9fa2051b183927533bc1b3ed4/lua/ui/game/gamemain.lua#L153).
- If you want to modify an existing UI element, you would hook the function you are interested in.
- If you want to modify the game loading phases, you cannot hook `StartGameUI`, because `uimain.lua` is loaded in the front end, but you can hook [`CreateWldUIProvider` of `gamemain.lua`](https://github.com/FAForever/fa/blob/33ef66dc35887bd9fa2051b183927533bc1b3ed4/lua/ui/game/gamemain.lua#L440). Changes here would most likely be preferred as contributions to FAF game repository ([GitHub](https://github.com/FAForever/fa)).
- Old mods hook `UserSync.lua`, which ends up being a hook in the Session Init phase, but you should not need to use this.


## Structuring your mod for ease of debugging

After hooking `CreateUI` (or a function), what do you write in your hook? This depends on the what you want to accomplish, but the fundamental structure can be similar for most mods to make debugging (and testing) easier.

### Better line numbers
Since hooking is file concatenation, if an error occurs in your code, the line numbers in the error message will go past the end of the actual file and you have to decipher where that large line number falls within your own mod. To avoid this, put your code in a separate file and import it.
For example, instead of:
```lua
function ComplexFn(obj, str)
	local ret = oldComplexFn(obj, val)
	if obj.a > 1 or str == "" then
		obj.window:Hide()
	end
  return ret
end
```
do:
```lua
function ComplexFn(obj, str)
	local ret = oldComplexFn(obj, str)
	local myModule = import("/mods/yourmod/modules/file.lua")
  myModule.ModifyComplexFnObj(obj, str)
  return ret
end
```

### Don't break the UI on errors
If your mod has an error and hooks `CreateUI` or a similar initialization-type function, the initialization you hooked won't continue for any other code coming after, be it from other mods or something you wrote. This can sometimes break the UI in such a way that you need to close the game to get the UI to work or errors to stop flooding the log. 
You can avoid this by wrapping your function in a `pcall`:
```lua
function ComplexFn(obj)
	local ret = oldComplexFn(obj)
	local myModule = import("/mods/yourmod/modules/file.lua")
  local ok, msg = pcall(myModule.ModifyComplexFnObj -- no () since we're passing in the function
		, obj, val
	)
	if not ok then WARN(msg) end -- complex mods may need to do more than this when an error occurs
  return ret
end
```
### Minimize code run upon import
Errors that happen during imports are usually not handled by whatever imported it, and they tend to spread errors because they break entire files instead of just one function. So don't do complex operations or call functions other than `import`. Use functions to encapsulate your code, and then call those functions wherever you are importing your mod.
Instead of:
```lua
-- module file
ModuleObj = {}
ModuleObj.a = CreateA() -- complex function that could error as you are working on the mod
ModuleObj.b = CreateB()
```
```lua
-- hooked file
local module = import("/mods/yourmod/modules/file.lua") -- if this import errors it breaks the entire hooked file
function Hooked()
	return module.ModuleObj
end
```
do:
```lua
-- module file
local moduleObj
function GetModuleObj()
	if not moduleObj then
		moduleObj = {}
    moduleObj.a = CreateA()
    moduleObj.b = CreateB()
	end

	return moduleObj
end
```
```lua
-- hooked file
local module = import("/mods/yourmod/modules/file.lua")
function Hooked()
	return module.GetModuleObj()
end
```

### Reloading your mod with /EnableDiskWatch
The disk watcher lets you immediately test changes you make if it is set up correctly. This is done using the `__moduleinfo` table that every imported file (a "module") has, using the member functions `OnReload` and `OnDirty`.
- `OnDirty` is called when the disk watcher detects a change in your module. It is an opportunity for you to clean up anything in the current state of the module
- `OnReload` is called when a dirtied module is imported again. It is called from the dirty module's state and has the new module as a parameter. It is an opportunity to set up the new module and pass data from the old module to the new one.

In conjunction, you can use these to make a UI element that goes back to where you were looking after you make a change, for example the [AutoLobbyInterface](https://github.com/FAForever/fa/blob/309b408c827e7dc60a24b7c78bfa64ac25d114c7/lua/ui/lobby/autolobby/AutolobbyInterface.lua#L222) class.
Basic Example:
```lua
local myObject
function __moduleinfo.OnDirty()
	myObject:Destroy()
	import(__moduleinfo.name)
end
function __moduleinfo.OnReload(newModule)
	local newObject = newModule.CreateObject()
  newObject:RestoreState(myObject.State)
end
```

> These examples re-import the module in the `OnDirty` function, but this should only be done if the module is not a dependency, because when a module is dirtied it dirties all modules that depend on it, and dependent modules usually initialize the module. Modules become dependencies if imported during import or after setting `__moduleinfo.track_imports = true`.
{.is-info}

## Getting data from the Sim

There are two ways to get data from the Sim: Engine functions and the Sync table.

### Engine Functions
Engine functions give relatively simple data about units in your own army.
This includes: "Rollover info" (blueprint id, resource consumption/production, health, shields, fuel, work progress, focused unit, kills stat, ammunition stats, custom name, and army index), command capabilities (what orders can be given), build capabilities, build rate, assisting units, attached units (for transports), pause state, fire state, auto-build mode, auto-surface mode, submerge state, overcharge availability, command queue, unit creator, unit position, unit's completion progress, and unit blueprint.

> Rollover info can be given about units outside your army by calling `GetRolloverInfo()` when mousing over the unit, but info about resources, shields, fuel, work progress, focus, ammo, and kills is removed.
{.is-info}

There are also a few engine functions that give information about the game, including: scenario info, game speed, game tick/time, mouse world pos,

- [User.lua *Documentation of global UI functions*](https://github.com/FAForever/fa/blob/develop/engine/User.lua)
- [UserUnit.lua *Documentation of UI unit functions*](https://github.com/FAForever/fa/blob/develop/engine/User/UserUnit.lua)
{.links-list}

#### Unit Script Bits
You may have noticed `GetScriptBit` and `ToggleScriptBit`. Script bits are used to toggle common abilities like shields, intel, stealth, cloak, production, jamming, and other special ones. Even though they usually follow the normal game rules for how they're used, their implementation in the sim is arbitrary lua, and the sim can toggle them as well. There is a table in the unit blueprint that defines how the toggles should be displayed in the UI when the script bits do not act exactly as expected.

#### UserUnit:GetStat
The `GetStat` function returns simple info about units as defined in the sim, including veterancy level/experience, HP regen, and reclaimed resource amounts.

### Sync Table
The Sync table is the way complex, custom info is sent from the sim to the UI.

This includes: what mass is on the map, game score data, game results (army defeat/victory), built unit enhancements, in-progress building/enhancement notifications, nuke launch notifications, mass fabricator status, objective timer, pings, replayed chat, game restrictions, pauses, diplomacy, campaign transmissions, and more.

The best way to mod the Sync table is to write a function and then add it using `AddOnSyncHashedCallback`.
```lua
local function OnNukeLaunched() end
AddOnSyncHashedCallback(OnNukeLaunched -- the callback
  , "NukeLaunchData" 			-- Category to listen to
  , "MyMod_OnNukeLaunched" -- Identifier to allow us to be replaced
)
```
If you clean up your UI element mid-session, you should remove the callback using `RemoveOnSyncHashedCallback`.
```lua
RemoveOnSyncHashedCallback("NukeLaunchData", "MyMod_OnNukeLaunched")
```
The old way to mod it is to hook `UserSync.lua`'s function `OnSync`.

- [UserSync.lua *UI-side root of almost all default sync usages*](https://github.com/FAForever/fa/blob/develop/lua/UserSync.lua)
{.links-list}

#### UnitData sync table
The global `UnitData` table contains persistent data for units, and is keyed with the entity ID. Although it is very versatile, it is currently only used for Seraphim T1 Scout Selen deselection when cloaked (key: `LowPriority`), name of currently set weapon priority (key: `WepPriority`), Eye of Rhianne ability status (key: `Abilities`; no UI example usage), and status of active buff names (key: `Buffs`; no UI example usage).
Basic example:
```lua
function GetUnitWepPriorityName(userUnit)
	local id = userUnit:GetEntityId()
	return UnitData[id].WepPriority
end
```
-----
> The following sections are brief and could be expanded into their own pages.
{.is-info}

## Getting Elements on Screen
With knowledge of where to hook and how to get data, you now just need to put the data on screen visually.

UI elements are made up of Controls, which are pretty much boxes of various types with a defined height, width, and position. There are various classes that also add text or images.

### Some visual designs:
- Dialogs
- Unit Overlays
- In-game HUD

Choose a UI element you like as an example, but be wary of old code styles.

[Mods made by 4z0t](https://github.com/4z0t/faf-ui-mods) have advanced features such as animations and a centralized mod options system, but they use a custom library.

### Code style:
A lot of FAF's UI is outdated so the code style is not good. One up-to-date UI element is the [autolobby interface](https://github.com/FAForever/fa/blob/develop/lua/ui/lobby/autolobby/AutolobbyInterface.lua), but it is rather simple.
[Mods made by 4z0t](https://github.com/4z0t/faf-ui-mods) are more complex and generally have good code style, but they use a custom library.

- [`uiutil.lua` *Various utility functions to make UI scripts easier and more consistent*](https://github.com/FAForever/fa/blob/develop/lua/ui/uiutil.lua)
- [`layouthelpers.lua` Layouter class: `ReusedLayoutFor` *An extremely helpful design pattern for laying out components, it is intended to make UI code readable, maintainable, robust, and easily diagnosable*](https://github.com/FAForever/fa/blob/e16b829ee2603450988f283e7ee1776026c53061/lua/maui/layouthelpers.lua#L1099)
{.links-list}

### LazyVars
LazyVars are common and used to dynamically calculate UI elements so that they can update when they are moved around or resized. They can also be used to manage state.
They are difficult to debug. Setting `ExtendedErrorMessages` to true in [lazyvar.lua](https://github.com/FAForever/fa/blob/develop/lua/lazyvar.lua) can help slightly. The most common lazyvar error comes from uninitialized position/height/width of a Control.

### Structuring UI layout code
Just like the code style, a lot of FAF's UI is old and difficult to understand or expand. Newer examples include the [autolobby interface](https://github.com/FAForever/fa/blob/develop/lua/ui/lobby/autolobby/AutolobbyInterface.lua).

## UI Skins
There exist hotkeys to cycle skins.

- [skins.lua *Hook to add in your own skin data*](https://github.com/FAForever/fa/blob/develop/lua/skins/skins.lua)
{.links-list}

## Hotkeys
You can add a hotkey (called a key action in the code) for your mod by using the keymapper to permanently save it in the user key actions (a table in the preferences file).
```lua
    local SetUserKeyAction = import("/lua/keymap/keymapper.lua").SetUserKeyAction
    local keyAction = {
        action = "UI_Lua import('/mods/yourmod/modules/file.lua').DoMyHotkey()", -- console command to run
        category = "MyMod",  -- category under which the action will be grouped in the hotkeys menu (F1)
    }
    SetUserKeyAction("ModdedAction1" -- Name of action used for display and searching
			, keyAction)
```
If you want to give your key action a better display name you can use key descriptions. This supports localization.
```lua
    local keyDescriptions = import('/lua/keymap/keydescriptions.lua').keyDescriptions
    keyDescriptions.ModdedAction1 = '<LOC key_ModdedAction1>Perform action from my mod'
```
If you want to assign a key to an action you can use the keymapper's `SetUserKeyMapping` function.
```lua
local keymapper = import("/lua/keymap/keymapper.lua")
local current = keymapper.GetCurrentKeyBinding("ModdedAction1")
keymapper.SetUserKeyMapping("Ctrl-Shift-Alt-M", current, "ModdedAction1")
```


## Localization
If you want to support multiple languages, you can use the `LOC` function to localize text inputs (although most UI util functions elements already localize internally) and hook the `strings_db.lua` file in the folder of the corresponding language.
- [`loc` folder in the game repository*all language folder names and a short translation guidelines document*](https://github.com/faforever/fa/tree/develop/loc)
{.links-list}

## Further Information

- [Mod Test Loop *Old Guide with example mod to experiment with*](/Development/Modding/Mod-test-loop)
{.links-list}