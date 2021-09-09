---
title: Modding
description: 
published: true
date: 2021-09-09T15:48:11.042Z
tags: 
editor: markdown
dateCreated: 2021-08-31T09:44:35.455Z
---

## Introduction

Supreme Commander is extensible by [mods](Game-Modifications-(Mods)), which can alter the whole gameplay (like PhantomX for example), change the balance of units, display information to the user or make the user automatically do things like renaming units or send messages to his allies when he starts upgrading. This is a page for you to get a basic idea of modding FA.

See also [Tips for Modding Efficiently](Tips-for-Modding-Efficiently).

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
- Here you can find a bunch of Functions in this [LUCADOC](/LUADOC)
- Here are some more Lua Global Functions [Lua.Globals](/LUAGLOBALS)

### Differences to default LUA

There are some things different to default LUA:
- The # sign is used to comment in FA, the #mytable operation to get its length is not possible, you can use table.getn(mytable) instead
- it's not necessary but still possible to use "for i, v in ipairs(mytable) do", "for i, v in mytable do" works aswell

### Sim and UI

![](Sim-ui.png "fig:Sim-ui.png") Basically, this game is divided in two interacting components, Sim and UI. Both are moddable, here is some info:
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

Q: I can't find files in the /lua path which should be there! Where are they?
A: Likely in the mohodata or schook folders (.scd files), they are mounted to the /lua path aswell

## Debugging

This section is to help you debug your mods and scripts. If you're creating a mod, and run into some errors, hopefully this will help you find a workaround.

### Handling LazyVars

This is quite a common issue with FA. Usually, LazyVars are related to the User Interface of FA. This sub-section will help you find out how to debug LazyVars and what's causing issues with your User Interface code.

The first thing you need to do is find out what's causing your error. LazyVars don't provide any helpful error exceptions by default, but this can be changed.

Navigate to: C:\\Program Files (x86)\\Steam\\steamapps\\common\\Supreme Commander Forged Alliance\\gamedata and open mohodata.scd with either 7zip or WinRAR.

Once you have opened the SCD file, find a file called 'lazyvar.lua' and open it with any text editor (Recommended: Notepad++ or Sublime Text 3) Be sure to make a back-up of this file before you make any changes as this may cause you to desync in public games when playing FAF.

With the file open, locate the variable "ExtendedErrorMessages = false" and change it to "ExtendedErrorMessages = true".

Save the file and a nice message should pop up: [1](https://i.gyazo.com/dca0f1768fc5ec5808b58b45809f92b0.png)

Click yes and close the archive.

Now, when you open up your game again, you will find that your console (F9) will provide error exceptions related to "LazyVars".

## Further Reading
modding [Shaders](Shaders "wikilink")
modding [Emitters](Modding_Emitters "wikilink")


## The Basics (By [Balthazar](https://github.com/The-Balthazar/SupCom-Mod-Tutorials/wiki))
### Getting started and mod_info
The first thing any new mod needs is its own mod folder and **mod_info.lua** file. **.lua** files are just plaintext so you can create and edit them with any plaintext editor including Notepad. I would, however, recommend getting an editor with syntax highlighting if you don't have one already; It will make things easier in the long run. I personally recommend [Atom](https://atom.io).

#### mod_info.lua
The bare minimum that a mod info file needs is as follows:
```lua
name = "Basic Mod"
uid = "0e6ac7fe-5c74-4e4c-802a-b452a8f10bc8"
version = 1
description = "This mod does nothing except appear on the mods list."
author = "Balthazar"
```
Update the values as described below and save it as **mod_info.lua** in your mods own folder in your games mods folder, which you can find in your documents. If you are doing this in Notepad, change the 'Save as type' to **All Files (*.*)** so you can save as **.lua** instead of **.txt**.

This will get you an item that appears on the mod manager and can be loaded. At this point it doesn't do anything else, but you need to start somewhere.

#### Primary values
Most of the values are fairly self explanatory, but for completeness I will outline them all:

- **name:** A string representing the name of the mod. Good conventions, and also FAF vault rules, say to not include any versioning in the name string.
- **uid:** A unique string identifier. Actual specifics are unimportant, since the game only uses it for string comparisons, however don't copy paste **uid**'s from other mods, and change the **uid** whenever you publish a new version of your mod. This change can be as trivial as having the version number at the end of the it. You can generate them fresh [here](https://www.uuidgenerator.net).
- **version:** The version of the mod. The game doesn't care if this is a string or number or whatever, however the FAF vault requires it to be an integer, and requires newer uploaded versions to be greater. Sorry if you're a fan of semantic versioning.
- **description:** A string expected to outline the basic effects of the mod. This is primarily visible in the mod manager, but also usually visible in any other index of mods. The vanilla lobby has a fairly restrictive character limit before it starts to spill over outside of its UI element, of two short-ish lines.
- **author:** The game doesn't actually reference this by default, although many other things do. Attribution is important. Should probably be a string.

That's slightly more than the bare minimum you need to get something appearing on the games mod manager.

#### Secondary values
Other functional mod info values that may be useful, but aren't essential are:

- **icon:** A string path to an image to represent the mod. Path wants to start at /mods/. Various standard formats are accepted, including .png. .dds is accepted in game, but generally isn't supported by anything outside the game.
- **enabled:** You can set this to false to remove your mod from the mod manager. No other value matters since it checks not false to make it show. Undefined, nil, true and anything else is all treated the same. The only reason to do this would be if you wanted to make a dummy container mod for the FAF vault, or some other external mod index.
- **exclusive:** When set to true no other mods can be enabled along side it. There are basically no good reasons to do this.
- **ui_only:** When set to true, the game will ignore any aspects of the mod that would make changes to the game simulation.
- **conflicts:** An array of uid strings of other mods that this mod is known to be incompatible with; for preventing them from being loaded together. For example:
```lua
conflicts = {
    "0e6ac7fe-5c74-4e4c-802a-b452a8f10bc8",
}
```
- **requires:** An array of **uid** strings of other mods that this mod requires to run. Will cause the game to enforce that mods with those **uid**'s be enabled before allowing this mod to be activated. It is recommended to combine it with **requiresNames** unless the required mods will always be packaged with this mod. Personally I leave this unpopulated and mention requirements in the descriptions so that if that mod updates, players can use the updated version of that mod without this mod being updated first to reference the new mod. Assuming that actually works.
- **requiresNames:** A table keyed with **uid**'s with mod-name values so that the missing requirement dialogue gives a human readable error instead of a random string. For example:
```lua
requiresNames = {
    ["0e6ac7fe-5c74-4e4c-802a-b452a8f10bc8"] = "Basic Mod",
}
```
- **before:** An array of **uid** strings. Controls mod load order.
- **after:** An array of **uid** strings. Controls mod load order.

### Blueprint Merge
The very simplest form of functional mod is the blueprint merge.

The primary purpose of the blueprint merge is to change selected values inside of unit blueprints. Generally for the purpose of balance changes and other tweaks.

These are done in **.bp** files. The game will actively load any **.bp** from inside your mod regardless of what it's called and where in the mod it is placed. Any directory structure housing them basically exists only for your personal organisational needs.

#### Anatomy of a .bp file and blueprints
As with **.lua** files, **.bp** files are plaintext files. A unit blueprint consists of the function **UnitBlueprint** called with a Lua table; the specification of that blueprint. Lua tables consist of curly brackets **{ }** with entries separated by commas **,**. The last entry can optionally have a comma after it to make rearranging lines easier and less-missing-comma-error prone.

If an entry doesn't contain an equals sign **=** defining the separation between 'key' and 'value' of that entry or cell, then the key is implicitly defined as a number; sequentially continuing from the previous number starting from 1. This differentiation is what separates any old table from an array; an array has sequential uninterrupted numbers for keys, that are often implicit rather than explicitly written, starting from 1 not 0

The values of the cells can be a number, simple maths equation, string, Boolean, another fully nested table, or the **Sound** function called with a table. Any other values will likely cause an error.

The most common reason for a **.bp** to not load is an error with commas, or an error with not properly nested tables. The game log will issue a warning saying that it failed to load the bp in this eventuality.

#### Blueprints and the blueprint ID
A **.bp** file can contain any number of blueprints as long as those blueprints define **BlueprintId**. The blueprint ID should always be lowercase. If the blueprint doesn't define **BlueprintId**, then it will derive the ID from the file name. If the filename contains the suffix **_unit** then the ID will be the part prior to that, converted to lowercase. If filename doesn't contain **_unit** then the entire file path, converted to lowercase, will be used as the ID. This is something to be avoided.

#### The merge
A blueprint merge is defined by setting **Merge = true**. This will cause the game to load the contents of the blueprint as an overwrite for whatever the blueprint ID defines. This means you can change a select few stats without having to include the whole of the original.

#### Creating a merge

##### Finding the target original
First thing you're going to want to do is locate the original blueprint. Be mindful of where you plan to use the mod when doing this. It shouldn't make too much difference since you're only going to be including changed values in your merge, but different environments have different balance, and sometimes some other crucial changes, but it makes it easier to compare changes if you are working from the correct version. For [FAF](https://github.com/FAForever/fa/tree/deploy/fafdevelop/units) and [LOUD](https://github.com/LOUD-Project/Git-LOUD/tree/master/gamedata/units/units) these files can be located in their respective Github pages. For all other versions of the game, these files can be located inside the gamedata folder, within the games directory, inside of **units.scd**. **.scd** is just a renamed **.zip** file, so either treat it as such, or rename a copy to that.

##### Assembling your merge
Look down the original for the values you want to change, and take note of what tables they are in. If you are using Atom or some other vaguely competent editor you should be able to collapse tables with a click when you see they contain nothing you're interested in, or you've dealt with them.

In your merge you will need to mirror the table structure for the values you wish to change. For example, if you wish to change a units max shield health, that will need to be in a Shield table, in the Defense table. If you have multiple keys with the same name within a given table, the later will replace the former, so it's best to avoid that.

One thing to be wary of is things like the **Categories** array; editing these can be problematic from a merge, and if you wish to do so in the 'best practice' way, that is covered in 103 § Closing with categories, so wait until you get there, or just replace the whole array with your changed version.

#### Aeon_Merge.bp
The following is an example taken from BrewLAN:
```bp
UnitBlueprint {
    Merge = true,
    BlueprintId = "xab3301", --T3 Quantum Optics
    Footprint = {
        SizeX = 3,
        SizeZ = 3,
    },
    Physics = {
        SkirtOffsetX = -2.5,
        SkirtOffsetZ = -2.5,
        SkirtSizeX = 8,
        SkirtSizeZ = 8,
    },
}

UnitBlueprint {
    Merge = true,
    BlueprintId = "ual0303", --Harbinger
    Defense = {
        Health = 2125,
        MaxHealth = 2125,
        Shield = {
            ShieldMaxHealth = 1200,
        },
    },
    Economy = {
        BuildCostEnergy = 5400,
        BuildCostMass = 480,
        BuildTime = 2400,
    },
    Physics = {
        MaxAcceleration = 4,
        MaxBrake = 4,
        MaxSpeed = 4,
    },
    Weapon = {
        [1] = {
            Damage = 150,
            MaxRadius = 20,
        },
    },
}
```

### Blueprint.lua hook
A powerful scripted alternative to the blueprint merge, is hooking the file **Blueprints.lua**.

It requires an amount of Lua programming, however with only some very basic scripts, large sweeping changes can be made across all units in the game, including those added by other mods, and the whole thing basically amounts to navigating tables like in 102 — Blueprint merge.

Finding the file you want to hook
Now, script hooks are much more restrictive than blueprint merges; you can't just dump the files in your mod folder and expect them to work: To set up a hook for a given Lua file, first locate the original. This is where your target game environment can really start to matter depending on what you plan to hook. Refer to 102 § finding-the-target-original but substitute units for lua.

For the purposes of this tutorial, locating the original file that we will be hooking will basically only serve as context for some of the actions we will be taking, and to show how it would be done for other files.

Setting up your hook
The file we want to hook is located at lua/system/Blueprints.lua, so in your mod folder, create a blank file at hook/lua/system/Blueprints.lua.

A quick aside; don't actually run the mod at this stage: An empty hook file will cause an error.

When loaded by the game, our hook will have access to everything in the original without having to redefine it, so there's no need to include anything that we aren't going to be changing. The only thing we're interested in is the function ModBlueprints. Now, we could at this point just have the following in our file:

function ModBlueprints(all_blueprints)

end
And write our new stuff in the middle of that. The problem with this is that it will overwrite anything added by any other mod resolved before this one, which is bad. If every mod did this then loading multiple mods would be like playing a game of snap with who's stuff gets ran.

How we solve this is to do:

local OldModBlueprints = ModBlueprints

function ModBlueprints(all_blueprints)
    OldModBlueprints(all_blueprints)
end
As you may well be able to see, what we're doing here is storing the old version of the function, replacing the function, then calling the old stored version. Now, this is mostly fine, however other mods hooking this file would be able to see and potentially accidentally modify our local variable OldModBlueprints, which we want to avoid. The way we do this is to surround the whole thing with a do block:

do
    local OldModBlueprints = ModBlueprints

    function ModBlueprints(all_blueprints)
        OldModBlueprints(all_blueprints)
    end
end
The effect of the do block here is to define the scope of things created within it. The bit inside it would still be 'done' without the do block, but the reference to OldModBlueprints will stop existing once the do block is over, and it will become inaccessible to other things. Which is what we want. The same isn't true of ModBlueprints, because that wasn't defined within the scope of the block; that was already defined; we just changed it.

So what have we got here
Now that we have our basics set up we are ready to start doing things.

In our ModBlueprints function we have the variable all_blueprints. Now, the name of that function doesn't actually matter, since the names of the function inputs are decided by the function, and bear no explicit resemblance to what is actually fed into them. We could rename it to all_bps or something as long as we rename all instances of it within that function, since as with the do block, the function defines a scope and things created within it only exist within it.

What is actually fed into the function is a table. The contents of that table is several other tables. These tables split the blueprints into basic groupings, and inside each of those tables is the actual blueprints. The whole thing basically looks like this:

all_blueprints = {
    Mesh = {
        --All mesh blueprints
    },
    Unit = {
        --All unit blueprints
    },
    Prop = {
        --All prop blueprints
    },
    Projectile = {
        --All projectile blueprints
    },
    TrailEmitter = {
        --All trail emitter blueprints
    },
    Emitter = {
        --All emitter blueprints
    },
    Beam = {
        --All beam blueprints
    },
}
A light example
The blueprints within each of those are defined as tables with the blueprint IDs used as keys. So from here, if we wanted to specifically change the health of the Mech Marine to 69, we could with the following:

do
    local OldModBlueprints = ModBlueprints

    function ModBlueprints(all_blueprints)
        OldModBlueprints(all_blueprints)
        all_blueprints.Unit.uel0106.Defense.Health = 69
        all_blueprints.Unit.uel0106.Defense.MaxHealth = 69
    end
end
As may be apparent, the . operator is what you use when you want to refer to a thing with a known string name inside the table to the left of the .. This has some downsides in that if any of the tables left of a dot don't exist for whatever reason, this would cause an error and make the game get stuck on the loading screen with a warning in the game log.

A serious light example
If we were serious about doing some Mech Marine changes, and didn't want to do this in a blueprint merge so we can have some logic associated with it, we could start with something like this:

do
    local OldModBlueprints = ModBlueprints

    function ModBlueprints(all_blueprints)
        OldModBlueprints(all_blueprints)
        MechMarineChanges(all_blueprints.Unit.uel0106)
    end

    function MechMarineChanges(MMBP)
        if MMBP and MMBP.Defense then
            MMBP.Defense.Health = 69
            MMBP.Defense.MaxHealth = 69
        end
    end
end
Now, what we're doing there is we're taking the blueprint reference for the Mech Marine, and feeding it into a function we called MechMarineChanges which we're defining below ModBlueprints. Now, if we defined MechMarineChanges as a local, it would need to be before ModBlueprints, but it's defined as a global within the scope of the do block we have surrounding our whole document, so we can access it from within ModBlueprints above it.

Within MechMarineChanges we're calling our first input argument MMBP, because we can, and it's descriptive enough and short enough to reference a lot without requiring a lot of space. When we're working with MMBP within this function, it's functionally the same as working with all_blueprints.Unit.uel0106 in ModBlueprints, but easier to handle.

What we're actually doing with MMBP in the function is first checking it exists, which we can't guarantee, then checking the Defense table within it also exists. The and operator in between the two will only do the part after it if the part before exists. Technically this could still error if MMBP is something that isn't a table, which we could check for, but honestly if that's ever true then something gone badly wrong elsewhere, or someone is playing silly buggers with the blueprints.

Repeated use
Since we're setting the health of the Mech Marine with a function that we just feed a blueprint, we could if we so wanted then also feed the function other blueprints. Say we wanted to also the Cybran and Aeon LABs, we could do this:

do
    local OldModBlueprints = ModBlueprints

    function ModBlueprints(all_blueprints)
        OldModBlueprints(all_blueprints)
        MechMarineChanges(all_blueprints.Unit.uel0106)
        MechMarineChanges(all_blueprints.Unit.ual0106)
        MechMarineChanges(all_blueprints.Unit.url0106)
    end

    function MechMarineChanges(MMBP)
        if MMBP and MMBP.Defense then
            MMBP.Defense.Health = 69
            MMBP.Defense.MaxHealth = 69
        end
    end
end
This is all perfectly fine and will work with no issues. From a stylistic point though, the name of the function is now a lie; it's not Mech Marine Changes any more; it's just generically making things have 69 health. MMBP is also technically a lie; it's no longer just the Mech Marine blueprint, it's just the blueprint we happen to be feeding it.

It's also veering headfirst into the realms of being a lot of copy pasted code; this isn't really a problem at this point, and is technically faster to execute than the alternative, but this is code executed once at the start of the game, so it's better to pay the price of setting up a loop, than deal with the inherent human-error prone-ness of unnecessary copy pasted code.

The Lööps
This is what those "fixes" look like:

do
    local OldModBlueprints = ModBlueprints

    function ModBlueprints(all_blueprints)
        OldModBlueprints(all_blueprints)

        local UnitsToChange = {
            'uel0106',
            'ual0106',
            'url0106',
        }

        for i, id in UnitsToChange do
            SetTo69Health(all_blueprints.Unit[id])
        end
    end

    function SetTo69Health(bp)
        if bp and bp.Defense then
            bp.Defense.Health = 69
            bp.Defense.MaxHealth = 69
        end
    end
end
This will have the same effect as the previous, but gets about it in a slightly different way. Now what's going on in these new bits:

First we're defining a new array UnitsToChange which has the IDs of the units we wish to change. As you hopefully remember from 102, tables without = in the cells to define keys are implicitly given number keys starting from 1, which are often called indexes instead of keys.

Second, we're creating a for loop. The i, id bit is what we will be calling the index and unit ID we will be working with from the table in each iteration. The i will be the implicit numbering we just mentioned, and the id will be what we actually want from the table. The in UnitsToChange part is defining the table we will be iterating over.

A word of warning in UnitsToChange technically isn't valid Lua; in later versions you would be expected to declare in ipairs(UnitsToChange) instead. You could do that here, but it isn't necessary.

Anyway, inside that loop we have our renamed function call SetTo69Health, and at the end of what we are feeding into it, instead of .uel0106 we have [id]; the square brackets is equivalent to the ., except we can feed it things without it taking them literally. For example, .id would try to access a table inside Unit called 'id', which probably doesn't exist, and isn't what we want if it does. We could rewrite the whole line to SetTo69Health(all_blueprints['Unit'][id]) if we wanted to, but since we know we want the table called 'Unit' at the time of writing we might as well hard code that instead.

We also renamed MMBP to bp so it matches its new use better.

But wait, there's more
But what if this isn't enough for us? What if we're not happy with just setting the LAB health values to 69? What if we want to set every units health to 69?

Well, we could just loop over the whole of all_blueprints.Unit instead:

do
    local OldModBlueprints = ModBlueprints

    function ModBlueprints(all_blueprints)
        OldModBlueprints(all_blueprints)

        for id, bp in all_blueprints.Unit do
            SetTo69Health(bp)
        end
    end

    function SetTo69Health(bp)
        if bp and bp.Defense then
            bp.Defense.Health = 69
            bp.Defense.MaxHealth = 69
        end
    end
end
To explain the changes, UnitsToChange is no longer needed, so that's gone, all_blueprints.Unit is keyed with the unit IDs and the value are now the actual blueprint we want, so where we once had i and id to represent the implied [1] = 'uel0106' we had in UnitsToChange, we now have id and bp to represent the uel0106 = { ... } we now have while looping through all_blueprints.Unit. And since the bp is what we were navigating to before to feed the SetTo69Health function, we can just feed it that directly.

We could have left it as SetTo69Health(all_blueprints.Unit[id]), but since we already have a direct reference to the blueprint, bp, we might as well use it.

Another aside: In much the same way that in modern Lua we'd want ipairs(UnitsToChange), here we'd want pairs(all_blueprints.Unit). The reason it's pairs and not ipairs is because ipairs is for when the keys are a sequential list of numbers starting at 1, and pairs is just for arbitrary tables. You could use pairs on an array instead of ipairs but it'd be slower and it wouldn't do them in order.

696969
But what if that's not enough 69 for us? What if instead of giving everything 69 health we wanted to set everything to have an amount of health that's the same length of the original, but all 69's instead? Well for that we could do:

do
    local OldModBlueprints = ModBlueprints

    function ModBlueprints(all_blueprints)
        OldModBlueprints(all_blueprints)

        for id, bp in all_blueprints.Unit do
            SetTo69Health(bp)
        end
    end

    function SetTo69Health(bp)
        if bp.Defense and bp.Defense.MaxHealth then
            local mathsWizardry = math.floor(math.pow(10, math.floor(math.log10(bp.Defense.MaxHealth))) * 6.96969696969696969696969696)

            bp.Defense.Health = mathsWizardry
            bp.Defense.MaxHealth = mathsWizardry
        end
    end
end
You'll notice we changed bp and bp.Defense into bp.Defense and bp.Defense.MaxHealth; the reason for that being we already know bp exists because we're working from the actual blueprints list not a list of ones we want to work from, and we added bp.Defense.MaxHealth because we plan to do maths to it, we need to make sure it exists first.

As for the maths wizardry; math.log10 is basically doing the opposite of what math.pow(10 is doing. This is a gross simplification and people who know maths probably just cringed a little. Without the math.floor operation in between the two, i.e.: math.pow(10, math.log10(bp.Defense.MaxHealth)), the result would be equal to bp.Defense.MaxHealth, but with the floor, that part is giving a number that is a 1 and a bunch of 0's. However many 0's would be needed to make it the same length as the original.

Then the outer parts of that are essentially taking the number from the inner part, which is probably 100 1000 or 10000, and multiplying it by 6.96 etc., and discarding the excess decimals. Giving us, in those examples, 696, 6969 or 69696.

It's done in a local both so that we don't have to calculate it twice, but also so that we don't have to write it twice or copy paste it.

Closing with categories
And at that point we've pushed this meme about as far as it can go without adding in some extra logic for giving less game warping numbers. So I'll close with giving some details on how we would effectively add and remove values from blueprint arrays like Categories, as promised in 102:

table.insert(bp.Categories, 'NEWCATEGORY')
table.removeByValue(bp.Categories, 'OLDCATEGORY')
Using everything we've learned in this tutorial so far, you should be able to make effective use of them. Remember to check bp.Categories exists first, and well done for making it this far.