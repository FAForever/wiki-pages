---
title: Integrated Mods
description: An outline of mods that were integrated into FAF, and how to use them.
published: true
date: 2023-06-03T18:42:15.129Z
tags: client
editor: markdown
dateCreated: 2021-08-31T09:43:34.672Z
---

These mods are currently integrated into FAF. **They don't require any installation and will probably break if you try to install them**.

## Engy Mod
![engimod.jpg](/engimod.jpg)
Only T1 engies were viable to produce higher tech units or assisting buildings. Multiple factories or more than one higher tech engy were very inefficient. Multiple T2/T3 factories and T2/T3 engies to build and assist are now cost efficient (Thanks to Rienzilla and Zock)

- The normal factory is renamed to T2/T3 factory Headquarters.
- If you have at least one Headquarters, you can now build some new, cheap factories (called support factories)
- If you lose all Headquarters, these support factories can make only t1 units until you make a new HQ.
- Many units had their build power adjusted, check the [Unit Database](/Unit-Database) for more details.
- You can remove support factories in the restriction menu of the FA lobby, it will disable this mechanic.

## Hotbuild

![hotbuild-layout-en.png](/hotbuild-layout-en.png)
Hotbuild is a mod which lets you quickly order buildings and units via hotkeys instead of having to click the build menu. It does this by having multiple structures/units bound to the same key, which you press multiple times to cycle through.

- Hotbuilding keys can be set in-game. Press **F1** to open keybinding window and scroll to **Hotbuilding** section.
- You need to set the keys up manually. Luckily, the keys are in order on the keyboard - w,e,r,t, ect. so it takes almost no time at all.
- The Hotkeys are saved to your **Game.prefs** file, which you can find at:

```
C:\Users\USERNAME\AppData\Local\Gas Powered Games\Supreme Commander Forged Alliance
```

>:\ AppData is a hidden folder, so make sure your settings for seeing it are enabled.

>:\ You can also transfer this file to other people to give them the same settings that you have, including templates.

-   Video tutorial on how to set up Hotkeys and UI [here.](https://www.youtube.com/watch?v=m5HJa9N_9ww)

## <img src="/gazui.png" width="30"/> Gaz UI

Gaz's UI, formerly GOOMs UI is a custom user interface developed for FA. It has additional functionality than the stock UI.

- Enable extra GAZ UI options in game menu; go to **Options - Interface**.
- Added options are starting with line "**Enable Cycle Preview for Hotbuild**"

Compatibility notes

- AZUI will not work while template names and detailed unit view are enabled.

### Options and Hotkeys

The various components of GAZ_UI can be toggled on and off via the ingame menu Options/Interface. Here's a short explanation of each item, which gives an overview of the features of GAZ_UI.

NOTE: There are some options that must be disabled to be compatible with AngryZealot's AZUI mod.


### GAZ UI Features

<table style="undefined;table-layout: fixed; width: 1453px">
<colgroup>
<col style="width: 180px">
<col style="width: 387px">
<col style="width: 886px">
</colgroup>
<thead>
  <tr>
    <th>Feature<br></th>
    <th>Description</th>
    <th>Comments</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td>Bigger Strategic Build Icons</td>
    <td>Replaces the strategic icons in the build menu with larger images.</td>
    <td>Has 3 settings; Off, Simple (larger icons only) and Full (larger icons with Tech dots).</td>
  </tr>
  <tr>
    <td>Template Rotation</td>
    <td>When placing a structure build template, you can press the middle mouse button to rotate the template.</td>
    <td></td>
  </tr>
  <tr>
    <td>SCU Manager</td>
    <td>Allows use of the SCU Manager.</td>
    <td></td>
  </tr>
  <tr>
    <td>Draggable Build Queue</td>
    <td>You can drag and drop items in a factory's build queue</td>
    <td></td>
  </tr>
  <tr>
    <td>Middle Click Avatars</td>
    <td>You can middle-click the avatar icons on the right side of the screen to select all units in that category.</td>
    <td></td>
  </tr>
  <tr>
    <td>All Race Templates</td>
    <td>When creating structure build templates, templates with common structures like Power Generators will be applied to all factions</td>
    <td>This means you don't need to create the same template for every faction.</td>
  </tr>
  <tr>
    <td>Single Unit Selected Info</td>
    <td>When you have only a single unit selected, that unit's mouse-over information will be displayed.</td>
    <td></td>
  </tr>
  <tr>
    <td>Single Unit Selected Rings</td>
    <td>When you have only a single unit selected, that unit's range rings will be turned on. (effectively, this option activates "Turn range  rings on selected units" if you have a single unit selected.)</td>
    <td></td>
  </tr>
  <tr>
    <td>Zoom Pop Distance</td>
    <td>This option sets the distance the Zoom Pop hotkey will zoom to.</td>
    <td></td>
  </tr>
  <tr>
    <td>Seperate Idle Builders</td>
    <td>When selecting engineers, factories and other builder units, idle units will be collected into a separate icon in the selection window.</td>
    <td></td>
  </tr>
  <tr>
    <td>Factory Build Queue Templates</td>
    <td>Replaces the strategic icons in the build menu with larger images.</td>
    <td>When a factory is selected, selecting the Templates tab will change the "Infinite Build" button into a "Save Template" button.   Alternatively, you can use the "Create Build Template (factory)"  hotkey. All functionality in the Factory Build Template tab is the same as Structure Build Templates. (you can rename, assign a hotkey for build  mode, etc.)   Added by norem</td>
  </tr>
  <tr>
    <td>Display Reclaim Window</td>
    <td>The unitview window will display hp regeneration rate, shield hp, shield regeneration rate and build rate of selected units.</td>
    <td>When enabled will also display up to 8 digits of energy/mass  production as opposed to the standard of 6 digits, ie "999999" when your  true energy production is "12574899"   Disabled by default   Added by ghaleon</td>
  </tr>
  <tr>
    <td>Display more Unit Stats</td>
    <td>Replaces the strategic icons in the build menu with larger images.</td>
    <td>Will now display hp regen rate changes due to upgrades and veterancy. Commander-type units now also get shield hp displayed. If a commander-type unit has gained a level up, hp regen rates in brackets denote the total regen rate gained by veterancy, the other value displays the regen rate gained by upgrades. This is based upon Eni's Total Veterancy UI mod and also works in conjunction with it. This feature is incompatible with Azui.  Enabled by default. Added by ghaleon</td>
  </tr>
  <tr>
    <td></td>
    <td>All template icons will have a small text below them, displaying the template name.</td>
    <td>This feature is incompatible with Azui Enabled by default Added by ghaleon</td>
  </tr>
  <tr>
    <td>Template Name Cutoff</td>
    <td>By using the slider, you can choose how many characters are omitted from the start of the Visible Template Names.</td>
    <td>You can use this to put some hidden characters in the name to allow templates to be sorted in the order that you want.   Needs to restart for the effects to be visible. Added by ghaleon</td>
  </tr>
  <tr>
    <td>Always Render Custom Names</td>
    <td>Self explanatory</td>
    <td>Enabled by default Added by ghaleon</td>
  </tr>
  <tr>
    <td>Force Render Enemy Lifebars</td>
    <td>Self explanatory</td>
    <td>Disabled by default Added by ghaleon</td>
  </tr>
  <tr>
    <td>Auto Rename Replays</td>
    <td>Auto renames the current Replay once you exit the Score screen. will work for localized versions of fa, too.</td>
    <td>Follows following naming scheme; "year"."month"."day"-"hour"."minute" "mapname"   Map name will be shortened to 15 characters   Other naming schemes may be supported in future revisions.   Enabled by default   Added by ghaleon</td>
  </tr>
  <tr>
    <td>Improved Unit deselection</td>
    <td>Reduce the number of selected units by shift(-1) or ctrl(-5) or ctrl+shift(-10) right-click in group selection.</td>
    <td>Enabled by default Added by ghaleon</td>
  </tr>
  <tr>
    <td>Smart Economy Indicators</td>
    <td>Enables advanced ecomony indicators</td>
    <td>When mass stores are above 80% and rising, the income indicator begins flashing bright white, if expenses are higher than income and usage efficiency is above 80%, the mass income indicator remains green, it's yellow till 50%, and red below that.   When energy stores below 20%, the energy indicator begins flashing bright white, before that, if below 50% and sinking, it turns red from yellow, and is green above 100%.   When zero expense, displays infinite instead of 100%   Percentile "efficiency" display goes to more than 100%. it was bad and wrong it was ever capped because it's an important metric.   Percentile values (not absolute values) are filtered, meaning they change smoothly over time. This is especially good when reclaiming stuff and wondering about your overall efficiency.   The old-style economy warnings (glowing underlay) now coincide with the new flashing effect.   You can switch between percentage and absolute +/- by clicking on the number in your mass/energy panel</td>
  </tr>
</tbody>
</table>


## More Unit Info

This mod has been improved and now it is integrated with FAF game. It shows more information about units when a user hovers over unit icons in factories. This game option is on by default, but can be turned off in the “interface” section of game options.

![more_unit_info.png](/more_unit_info.png)

## <img src="/sorian_icon.jpg" width="40"/> Sorian AI

This is an advanced AI which poses much more of a challenge, and in general simply plays better. To use the mod, simply [host a game](/Host-and-join-games) and add AI players, selecting one of the Sorian AI options.

## Split Attack

*Thanks to Blackops team and johnie102*

Split attack allows you to easily attack multiple targets. Bound to Shift-G by default.

- Select some of your units. Make them attack a bunch of enemy units.

![split_attack1.jpg](/split_attack1.jpg)

- Press Shift-G.
- Each of your unit is now attacking a separate group of enemy units.

![split_attack2.jpg](/split_attack2.jpg)

**Uses**
Spread attack move works with move orders as well as other types of orders - experiment to find different uses! The command is very versatile and can give you various advantages:

- Spread attack with move commands is an effective way to prevent units from moving as a group.
- You can get units to move faster to their destination especially around rough terrain.
- Directing utnis through tight spaces or chokepoints is much easier with this feature.
- This features allows for huge micro advantages in T1 land battles.

## Hotkey Labels
*Thanks to Washy for making this mod* ![hotkeylabels.png](/hotkeylabels.png){.align-right}
Displays bound keys on icons in the build menu and command menu

- helps a lot with memorizing (custom) keybindings
- has differend colors for key combinations

## <img src="/notify.png" width="40"/> Notify

Notify allies about ACU upgrades in team chat, along with allowing for ACU/SACU upgrades to be queued up alongside regular orders. Mod by Crotalus, CodingSquirrel

## Selection Sort
Improved unit sorting in the selection panel.