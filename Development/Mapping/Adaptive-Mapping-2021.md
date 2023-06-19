---
title: Adaptive Mapping Guide Updated 2021
description: an upto date guide on how to make adaptive maps
published: true
date: 2023-06-19T09:56:29.669Z
tags: mapping, adaptive, guide
editor: markdown
dateCreated: 2022-08-12T22:17:59.915Z
---

This guide will take you through the steps to turn a standard skirmish map in to an adaptive map, or how to set one up from the start, the method is the same for both apart from the first step, where renaming won't be necessary because you will name it correctly to begin with, your map name must start with Adaptive , For ease of identifying in the vault and to honour the author of the script, failure to do this will lead to your map being hidden by the vault mods.


**Change your map name**
-

In my example my map is called Test Map, this will need to be changed to Adaptive Test Map here,

![alt text](https://i.imgur.com/dmq3JFX.png)
First make a normal save this can be used as a back up, Then you will need to save your map using save as, Then right click in the files box and create a new folder and name it;
Adaptive test map
Then select the folder you have just created and click select folder

![alt text](https://i.imgur.com/TmbuEj5.png)

when the editor saves, it will add the correct file path so it will look like this -- Adaptive_Test_Map.v0001 --


**Creating the lua files needed**
-

Now switch to the markers tab and then to the adaptive tab,

![alt text](https://i.imgur.com/VuyBcrS.png)

And click create table file, A pop up will appear asking to replace the script.lua click yes to this, if you check your map folder you should have all these files

![Image](https://i.imgur.com/8hsPEQO.png)


**Setting up your options**
-

Assigning mex and hydro to player spawn

By doing this when a player in not in that slot their resources wont spawn on the map,
First make sure your army spawn id's are set up correctly (odds vs evens),

![alt text](https://i.imgur.com/XxPx3YO.png)

Then select the adaptive tab and select all the resource markers you want to add to that player, Then click the corresponding Army and repeat for all players,

![alt text](https://i.imgur.com/nXr6Jop.png)

Lines will appear showing you have done it correctly, If this is the only thing you want your adaptive map to do you can stop here, Read on if you want to explore the other options available.


**Assigning extra core mex**
-

In this example I want to be able to choose between 4 or 6 core mex, so I will add 2 extra mex markers per player and select them, then assign them to a player and tag them as core mexes,

![alt text](https://i.imgur.com/GXXbuGM.png)

The untagged ones will always spawn with the player, But the tagged ones will need to be selected from the options in the game lobby, to make them appear in the options when you host a game you need to edit the options.lua, I prefer to use notepad++ (but regular notepad works to), find this section of code and move it above the comment line that states
-- it should be above this line to use them --
```
{
    default = 1,
    label = "<LOC adaptive_core_mex_label> Core Mexes",
    help = "<LOC adaptive_core_mex_2_help> Spawn 4 or 5 core mexes.",
    key = 'core_mexes',
    pref = 'core_mexes',
    values = {
      -- there are no additional translations for this option
        { text = "4", help = "<LOC adaptive_core_mex_key_4> Spawn 4 core mexes.", key = 1, },
        { text = "5", help = "<LOC adaptive_core_mex_key_5> Spawn 5 core mexes.", key = 2, },
    },
},
```

In my example I would now need to change a couple of numbers and remove some text for it to show in the options with the right number of mex, Green box's change from 5 to 6, And yellow boxes need to be deleted or the game will default to the text that it's referencing there,

![alt text](https://i.imgur.com/LoXY4DG.png)

These should be changed to match your map if necessary, And can be changed on any of the options

![alt text](https://i.imgur.com/E4OM4CY.png)
Label and help,

![alt text](https://i.imgur.com/JDEUWBf.png)
Text and help in the values,

This process is the same for all options that are either on or off (Extra hydros, Extra mexes, Extra base mexes) although you don't have to have them linked to player, if you don't want them to be dependent on a player

To change which option is the default option you will need to change the number after
-- Default = X -- to match the key number -- key = X -- then you need to open script.lua and find this line (Line 23)
```
local core_mexes = ScenarioInfo.Options.core_mexes or 1
```

and change the number to match the default number you chose in the options.lua,
It is the same process for setting all defaults so remember this process.


**Assigning expansion mexes**
-

In this example we will add expansion mexes so you will be able to choose between 4 options;
option key=1 : removes a+b+c
option key=2 : spawn a, removes b+c
option key=3 : spawn a+b, removes c
option key=4 : spawn a+b+c

Add the mexes you want to be your expansion mexes,then open the adaptive tab and tag them like this,

![alt text](https://i.imgur.com/gLP0DOg.png)

Red is 1, Green is 2, Yellow is 3, And tag them all to a player if you want them player dependent, Repeat for all players and mex you want assigned, Now back to the options.lua and find this, and move it above the line

![7e3f6488-e838-4a24-b9e6-2ab4fe65369c-image.png](/assets/uploads/files/1619868961672-7e3f6488-e838-4a24-b9e6-2ab4fe65369c-image.png)

In this instance all the text, help and labels are correct for what I am doing but if I needed to change anything it would be the same as above, this process will work for all options that have 4 choices (Middle mexes, Side mexes and so on)


**Optional civilian defences**
-

In this example we will create some defences between our players that you can choose if there are no defences, T1, T2, T3 or wreckage of any of the tech levels, for this one we'll start by moving the options above the line in options.lua look for this

```lua
{
	default = 1,
  lablel = "<LOC adaptive_civ_def_label> Civilian Defense",
  help = "<LOC adaptive_civ_def_label> Spawn civilian defenses at the middel plateau.",
  key = 'optional_civilian_defenses',
  pref = 'optional_civilian_defenses',
  values = {
  	{ text = "<LOC adaptive_disabled> disabled", help="<LOC adaptive_civ_def_key_0_help> No civilian defenses.", key = 1, },
    { text = "<LOC adaptive_def_key_1> T1 Wrecks (PD+AA)" help="<LOC adaptive_civ_def_key_1_help> Spawn civilian T1 PD & AA Wrecks. Includes T1 Radar, T1 Power Generators & Energy Storage.", key = 2, },
    { text = "<LOC adaptive_def_key_2> T2 Wrecks (PD+TMD)" help="<LOC adaptive_civ_def_key_2_help> Spawn civilian T2 PD & TMD Wrecks in addition to T1.", key = 3, },
    { text = "<LOC adaptive_def_key_3> T3 Wrecks (PD+AA)" help="<LOC adaptive_civ_def_key_3_help> Spawn civilian T3 PD & AA Wrecks in addtion to T1 & T2.", key = 4, },
    { text = "<LOC adaptive_def_key_4> T1 operational (PD+AA)", help="<LOC adaptive_civ_def_key_4_help> Spawn operational civilian T1 PD & AA. Includes T1 Radar, T1 Power Generators & Energy Storage.", key = 5, },
    { text = "<LOC adaptive_def_key_5> T2 operational (PD+TMD)", help="<LOC adaptive_civ_def_key_5_help> Spawn operational civilian T2 PD & TMD in addition to T1.", key = 6, },
    { text = "<LOC adaptive_def_key_6> T3 operational (PD+AA)", help="<LOC adaptive_civ_def_key_6_help> Spawn operational civilian T3 PD & AA in addtion to T1 & T2.", key = 7, },
  },
},

```

Now go back to editor and switch to the unit tab and groups tab, Then create 3 groups in ARMY_17 named;
Optional_Civilian_Defenses_2
Optional_Civilian_Defenses_3
Optional_Civilian_Defenses_4

![alt text](https://i.imgur.com/qgnzb91.png)

Then with Optional_Civilian_Defenses_2 group selected switch to the units tab then click on find unit which will open the unit browser then pick your T1 defences and place them, Then select the next group Optional_Civilian_Defenses_3, And repeat the last step but this time with T2 defences, And then repeat with next group for T3, You will also need to place a radar and power for some defences to work, You can place mobile units down but they will be Dumb though they won't move at all, And only attack if you get in range, The process is similar if you just want civilian bases, But you need to use the option labelled
-- Civilian Base -- and you only need one group named;
Optional_Civilian_Base_2
Make sure you change the text and help lines in the options.lua to match your map


**Crazy rush**
-

This option will add a crazy rush mex to your players spawn (for the uninitiated crazy rush is where you place a mex down and the 4 spots around it turn into new mexes), This one is easy, Open adaptive tab and select one of the start mex assigned to a player and tag it as Crazyrush One Mexes that's it, The option for this should already be above the line in the options.lua


**Expanding map**
-

This will allow you to define a start area, And then have it expand after either, A set time has elapsed or 80%/90% of mex have been built or if a player spawns in the expanded area, In this example we will add 2 players and place them in the expansion area, First we need to set up our areas, Switch to the map and areas tab and and create a new area, Name it AREA_4

![alt text](https://i.imgur.com/NuDWJYn.png)

Choose the size you want your start area to be here (boxes match the arrows)

![alt text](https://i.imgur.com/xikWhph.png)

In my example i will be adding players you can skip this part if its not relevant*, To add players place a blank marker and rename it to the next numerical army then switch to the armies tab and add armies, Then i will move the markers into the expansion area and add their start mex and tag them in the adaptive tab as before,

*Now we need to open options.lua and move the expansion options above the line and edit the help line so its relevant

![alt text](https://i.imgur.com/taoWutt.png)

If you want to change the default you need to change it here in the script.lua for this option

![alt text](https://i.imgur.com/BImP3tE.png)

Next we need to open script.lua and find this and remove the -- from the highlighted line

![alt text](https://i.imgur.com/BNNI2KL.png)

Then scroll down to the expansion part and change these from AREA_1 to AREA_4

![alt text](https://i.imgur.com/JLYIE2f.png)

so that the options for 80% or 90% mex built are only looking at the start area not the whole expanded map area, The next part is for players added in the expansion you are done if this doesn't apply to your map, Now find this part and delete the red squares and change the blue square to the army numbers that are in the expansion and you are done.

![alt text](https://i.imgur.com/CdaXPNm.png)


**Seraphim jamming crystal**
-

this will add a jamming crystal to your map which will create false radar signals, To do this open the groups tab and create a new group in ARMY_17 and name it;
Jamming

![alt text](https://i.imgur.com/Gjyn0T2.png)

then switch to the units tab and place a seraphim jamming crystal,

![alt text](https://i.imgur.com/oVDxOK3.png)

Then open options.lua and move the jamming part above the line and adjust the default if you want to (don't forget to change the default in script.lua to match)

Here's a link to Cookienoobs video tutorial https://