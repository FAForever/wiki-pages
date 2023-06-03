Gaz's UI, formerly GOOMs UI is a custom user interface developed for FA.
It has additional functionality than the stock UI. The mod has since
been integrated into FAF and requires not installation. Simply enable
the corresponding options in-game under UI options.

## How to install for use with FAF

-   GAZ UI was integrated into FAF together with Hotbuild.
-   You can enable extra GAZ UI options in game menu; go to Options -
    Interface.
-   Added options are starting with line "Enable Cycle Preview for
    Hotbuild"

## Changelog

-   Version 6
    -   Many modules added
    -   Smart Economy Indicators
    -   Strat Build Icons updated

<!-- -->

-   Version 5
    -   Factory Build Queues feature dded
    -   You can now turn off the "seperate icon for idle engineers"
        feature via the options menu.
    -   README.txt updated to give more info

<!-- -->

-   Version 4
    -   Some search & replaces fixed, SCUManager no longer references
        the old mod.

<!-- -->

-   Version 3
    -   Added norem's hotkeys
    -   Idle engineers in selection now uses Idle icon rather than low
        fuel (thanks norem!)
    -   Idle icon will now appear even if you dont have "Larger Strat
        Icons" enabled.
    -   Fixed some bugs.

<!-- -->

-   Version 1
    -   The units in the selection window will now be consistently
        sorted. If you right click to remove some they will no longer
        randomly reorder themselves.
    -   Idle construction units (factories, engineers, (s)ACUs) will now
        be seperated from active ones in the selection window. The idle
        units will be marked with an "out of fuel" icon.
    -   The "larger strategic icons" for the build window have been
        changed

## Documentation

Readme : (btw) Goom's old documentation is in the original thread:
viewtopic.php?t=23447

viewtopic.php?p=414706

## Overview - Options

The various components of GAZ_UI can be toggled on and off via the
ingame menu Options/Interface. Here's a short explanation of each item,
which gives an overview of the features of GAZ_UI.


NOTE: There are some options that must be disabled to be compatible with
AngryZealot's AZUI mod.

<table>
<caption>GAZ UI Features</caption>
<thead>
<tr class="header">
<th><p>Feature</p></th>
<th><p>Description</p></th>
<th><p>Comments</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Bigger Strategic Build Icons</p></td>
<td><p>Replaces the strategic icons in the build menu with larger images.</p></td>
<td><p>Has 3 settings; Off, Simple (larger icons only) and Full (larger icons with Tech dots).</p></td>
</tr>
<tr class="even">
<td><p>Template Rotation</p></td>
<td><p>When placing a structure build template, you can press middle mouse button to rotate the template.</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>SCU Manager</p></td>
<td><p>Allows use of the SCU Manager.</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Draggable Build Queue</p></td>
<td><p>You can drag and drop items in a factory's build queue.</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Middle Click Avatars</p></td>
<td><p>You can middle-click the avatar icons on the right side of the screen to select all units in that category.</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>All Race Templates</p></td>
<td><p>When creating structure build templates, templates with common structures like Power Generators will be applied to all factions.</p></td>
<td><p>This means you dont need to create the same template for every faction.</p></td>
</tr>
<tr class="odd">
<td><p>Single Unit Selected Info</p></td>
<td><p>When you have only a single unit selected, that unit's mouse-over information will be displayed.</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Single Unit Selected Rings</p></td>
<td><p>When you have only a single unit selected, that unit's range rings will be turned on. (effectively, this options activates "Turn range rings on selected units" if you have a single unit selected.)</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Zoom Pop Distance</p></td>
<td><p>This option sets the distance the Zoom Pop hotkey will zoom to.</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Seperate Idle Builders</p></td>
<td><p>When selecting engineers, factories and other builder units, idle units will be collected into a seperate icon in the selection window.</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Factory Build Queue Templates</p></td>
<td><p>Allows creation of Factory Build Queue templates.</p></td>
<td><ul>
<li>When a factory is selected, selecting the Templates tab will change the "Infinite Build" button into a "Save Template" button.</li>
<li>Alternatively you can use the "Create Build Template (factory)" hotkey. All functionality in the Factory Build Template tab is the same as Structure Build Templates. (you can rename, assign hotkey forbuild mode, etc.)</li>
<li>Added by norem</li>
</ul></td>
</tr>
<tr class="even">
<td><p>Display Reclaim Window</p></td>
<td><p>Will display a small window close to the Economy Bar which details the total mass and energy you have reclaimed.</p></td>
<td><ul>
<li>When enabled will also display up to 8 digits of energy/mass production as opposed to standard of 6 digits, ie "999999" when your true energy production is "12574899"</li>
<li>Disabled by default</li>
<li>Added by ghaleon</li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Display more Unit Stats</p></td>
<td><p>The unitview window will display hp regeneration rate, shield hp, shield regeneration rate and build rate of selected units.</p></td>
<td><ul>
<li>Will now display hp regen rate changes due to upgrades and veterancy.</li>
<li>Commander-type units now also get shield hp displayed.</li>
<li>If a commander-type unit has gained a level up, hp regen rates in brackets denote total regen rate gained by veterancy, the other value displays regen rate gained by upgrades.</li>
<li>This is based upon Eni's Total Veterancy UI mod and also works in conjuction with it.</li>
<li>This feature is incompatible with Azui</li>
<li>Enabled by default</li>
<li>Added by ghaleon</li>
</ul></td>
</tr>
<tr class="even">
<td><p>Visible Template Names</p></td>
<td><p>All template icons will have a small text below them, displaying the template name.</p></td>
<td><ul>
<li>This feature is incompatible with Azui</li>
<li>Enabled by default</li>
<li>Added by ghaleon</li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Template Name Cutoff</p></td>
<td><p>By using the slider, you can choose how many characters are omitted from the start of the Visible Template Names.</p></td>
<td><ul>
<li>You can use this to put some hidden characters in the name to allow templates to be sorted in the order that you want.</li>
<li>Needs restart for effects to be visible.</li>
<li>Added by ghaleon</li>
</ul></td>
</tr>
<tr class="even">
<td><p>Always Render Custom Names</p></td>
<td><p>Self explanatory</p></td>
<td><ul>
<li>Enabled by default</li>
<li>Added by ghaleon</li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Force Render Enemy Lifebars</p></td>
<td><p>Self explanatory</p></td>
<td><ul>
<li>Disabled by default</li>
<li>Added by ghaleon</li>
</ul></td>
</tr>
<tr class="even">
<td><p>Auto Rename Replays</p></td>
<td><p>Auto renames the current Replay once you exit to the Score screen. will work for localized versions of fa, too.</p></td>
<td><ul>
<li>Follows following naming scheme; "year"."month"."day"-"hour"."minute" "mapname"</li>
<li>Map name will be shortened to 15 characters</li>
<li>Other naming schemes may be supported in future revisions.</li>
<li>Enabled by default</li>
<li>Added by ghaleon</li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Improved Unit deselection</p></td>
<td><p>Reduce the number of selected units by shift(-1) or ctrl(-5) or ctrl+shift(-10) right-click in group selection.</p></td>
<td><p>Enabled by default</p>
<ul>
<li>Added by ghaleon</li>
</ul></td>
</tr>
<tr class="even">
<td><p>Smart Economy Indicators</p></td>
<td><p>Enables advanced ecomony indicators</p></td>
<td><ul>
<li>When mass stores above 80% and rising, income indicator begins flashing bright white, if expenses are higher than income and usage efficiency is above 80%, mass income indicator remains green, it's yellow till 50%, and red below that.</li>
<li>When energy stores below 20%, energy indicator begins flashing bright white, before that, if below 50% and sinking, it turns red from yellow, and is green above 100%.</li>
<li>When zero expense, displays infinite instead of 100%</li>
<li>Percentile "efficiency" display goes to more than 100%. it was bad and wrong it was ever capped, because it's an important metric.</li>
<li>Percentile values (not absolute values) are filtered, meaning they change smoothly over time. This is expecially good when reclaiming stuff and wondering about your overall efficiency.</li>
<li>The old style economy warnings (glowing underlay) now coincide with the new flashing effect.</li>
</ul>
<dl>
<dt></dt>
<dd>You can switch between percentage and absolute +/- by clicking on the number in your mass/energy panel.
</dd>
</dl></td>
</tr>
</tbody>
</table>

GAZ UI Features

## Overview - Hotkeys

By pressing F1, you can access the hotkey window. GAZ_UI allows you to
bind your own hotkeys!

-   Although its possible to bind a function to multiple keys, only one
    key will be displayed in the F1 window.
-   The Hotkeys are saved to your Game.prefs file, which you can find
    at: \\Documents and Settings\\\[YOUR USER NAME\]\\Local
    Settings\\Application Data\\Gas Powered Games\\Supreme Commander
    Forged Alliance
-   It's sometimes easier to directly edit that file to manage
    yourhotkeys. **Be sure to back up your file to another location
    before moidfying it!** This is for semi-advanced users only!

GAZ_UI also adds some additional hotkeys, which you may find useful: The
table is quite large, beware of the expanded version!

<table>
<caption>GAZ UI Hotkeys</caption>
<thead>
<tr class="header">
<th><p>The "internal name" which is used by Game.prefs</p></th>
<th><p>The name listed in the F1 Menu</p></th>
<th><p>An explanation of the key.</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>toggle_repeat_build</p></td>
<td><p>Toggle factory repeat build</p></td>
<td><p>Toggles the "Infinite Build" button on factories.</p></td>
</tr>
<tr class="even">
<td><p>zoom_pop</p></td>
<td><p>One-key zoom-pop</p></td>
<td><p>The hotkey for the zoompop feature.</p></td>
</tr>
<tr class="odd">
<td><p>toggle_all</p></td>
<td><p>Toggle all unit abilities</p></td>
<td><p>Toggles all toggleable functions on the selected units. This is a handy key since most units only have 1 toggleable function anyways. (eg. shield generators, mass fabricators, etc.) Alternatively there are individual hotkeys in this table.</p></td>
</tr>
<tr class="even">
<td><p>toggle_shield</p></td>
<td><p>Toggle unit shield</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>toggle_weapon</p></td>
<td><p>Toggle unit weapon</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>toggle_jamming</p></td>
<td><p>Toggle unit jamming</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>toggle_intel</p></td>
<td><p>Toggle unit intel</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>toggle_production</p></td>
<td><p>Toggle unit production</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>toggle_stealth</p></td>
<td><p>Toggle unit stealth</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>toggle_generic</p></td>
<td><p>Toggle unit generic</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>toggle_special</p></td>
<td><p>Toggle unit special</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>toggle_cloak</p></td>
<td><p>Toggle unit cloak</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>toggle_cloakjammingstealth</p></td>
<td><p>Toggle all counter-intelligence abilities</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>toggle_intelshield</p></td>
<td><p>Toggle intel and shield</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>teleport</p></td>
<td><p>Teleport</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>military_overlay</p></td>
<td><p>Show all weapon ranges</p></td>
<td><p>Toggles a SupCom-style "military overlay", where weapon ranges of all units are displayed.</p></td>
</tr>
<tr class="odd">
<td><p>intel_overlay</p></td>
<td><p>Show all intel ranges</p></td>
<td><p>Toggles a SupCom-style "intel overlay", where intel ranges of all units are displayed.</p></td>
</tr>
<tr class="even">
<td><p>select_all_idle_eng_onscreen</p></td>
<td><p>Select idle engineers on screen</p></td>
<td><p>Selects all idle engineers of all tech levels that are onscreen.</p></td>
</tr>
<tr class="odd">
<td><p>scu_upgrade_marker</p></td>
<td><p>Place SCU auto-upgrade marker</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>select_all_similar_units</p></td>
<td><p>Select all similarly upgraded units</p></td>
<td><p>These are for the SCU Manager. I think it selects all SCUs that are similarly upgraded.</p></td>
</tr>
<tr class="odd">
<td><p>select_next_land_factory</p></td>
<td><p>Select next land factory</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>select_next_air_factory</p></td>
<td><p>Select next air factory</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>select_next_naval_factory</p></td>
<td><p>Select next naval factory</p></td>
<td><p>Pressing these keys multiple times will go through your factories one by one.</p></td>
</tr>
<tr class="even">
<td><p>toggle_selectedinfo</p></td>
<td><p>Toggle single unit selected info</p></td>
<td><p>Toggles the "single unit selected info" feature. May be useful to get rid of the window temporarily to clear up your view.</p></td>
</tr>
<tr class="odd">
<td><p>toggle_selectedrings</p></td>
<td><p>Toggle single unit selected rings</p></td>
<td><p>Toggles the "single unit selected rings" feature.</p></td>
</tr>
<tr class="even">
<td><p>select_inview_idle_mex</p></td>
<td><p>Select onscreen idle mass extractors.</p></td>
<td><p>Select all idle mass extractors in view.</p></td>
</tr>
<tr class="odd">
<td><p>select_all_mex</p></td>
<td><p>Select all mass extractors.</p></td>
<td><p>Selects all your mass extractors everywhere.</p></td>
</tr>
<tr class="even">
<td><p>select_nearest_idle_lt_mex</p></td>
<td><p>Select nearest onscreen lowest tech idle mass extractor.</p></td>
<td><p>Select a mass extractor that is In view, Nearest to the cursor, Lowest tech level of all mexes in view, Idle.</p></td>
</tr>
<tr class="odd">
<td><p>acu_select_cg</p></td>
<td><p>Select ACU (control group)</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>acu_append_cg</p></td>
<td><p>Append ACU to selection (control group)</p></td>
<td><p>Selects the ACU in different sort of way. I'm not sure what it does exactly, I'll find out in the next version of this document.</p></td>
</tr>
<tr class="odd">
<td><p>select_nearest_idle_eng_not_acu</p></td>
<td><p>Select nearest idle engineer (not ACU)</p></td>
<td><p>Selects the nearest idle engineer. Different from the other key because it will not select the ACU ever.</p></td>
</tr>
<tr class="even">
<td><p>add_nearest_idle_engineers_seq</p></td>
<td><p>Select/Add nearest idle engineers</p></td>
<td><p>Pressing this key multiple times will add nearby idle engineers to your selection one by one.</p></td>
</tr>
<tr class="odd">
<td><p>cycle_idle_factories</p></td>
<td><p>Cycle through idle factories</p></td>
<td><p>Pressing this key multiple times will select idle factories one by one.</p></td>
</tr>
<tr class="even">
<td><p>cycle_unit_types_in_sel</p></td>
<td><p>Cycle through unit types in selection (Land, Sea, Air)</p></td>
<td><p>Filter your current selection to a single class of unit (air, land, sea). It will remember your selection so you can press this key multiple times to cycle through the types.</p></td>
</tr>
<tr class="odd">
<td><p>create_template_factory</p></td>
<td><p>Create build template (Factory)</p></td>
<td><p>If a factory with a build queue is selected, it will create a factory queue template from it.<br />
</p></td>
</tr>
<tr class="even">
<td><p>toggle_tab_display</p></td>
<td><p>Toggle options tab</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>toggle_mdf_panel</p></td>
<td><p>Toggle MFD panel</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>show_enemy_life</p></td>
<td><p>Show enemy life bars</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>show_network_stats</p></td>
<td><p>Show network stats window</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>select_all_air_exp</p></td>
<td><p>Select all Air Experimentals</p></td>
<td><p>added by ghaleon</p></td>
</tr>
<tr class="odd">
<td><p>select_all_air_factories</p></td>
<td><p>Select all Air Factories</p></td>
<td><p>added by ghaleon</p></td>
</tr>
<tr class="even">
<td><p>select_all_antinavy_subs</p></td>
<td><p>Select all anti-Navy Submarines</p></td>
<td><p>added by ghaleon</p></td>
</tr>
<tr class="odd">
<td><p>select_all_battleships</p></td>
<td><p>Select all Battleships</p></td>
<td><p>added by ghaleon</p></td>
</tr>
<tr class="even">
<td><p>select_all_land_directfire</p></td>
<td><p>Select all Land Direct-Fire units</p></td>
<td><p>added by ghaleon</p></td>
</tr>
<tr class="odd">
<td><p>select_all_land_exp</p></td>
<td><p>Select all Land Experimentals</p></td>
<td><p>added by ghaleon</p></td>
</tr>
<tr class="even">
<td><p>select_all_land_factories</p></td>
<td><p>Select all Land Factories</p></td>
<td><p>added by ghaleon</p></td>
</tr>
<tr class="odd">
<td><p>select_all_land_indirectfire</p></td>
<td><p>Select all Land Indirect-Fire units</p></td>
<td><p>added by ghaleon</p></td>
</tr>
<tr class="even">
<td><p>select_all_naval_factories</p></td>
<td><p>Select all Naval Factories</p></td>
<td><p>added by ghaleon</p></td>
</tr>
<tr class="odd">
<td><p>select_all_stationdrones</p></td>
<td><p>Select all Drones</p></td>
<td><p>added by ghaleon</p></td>
</tr>
<tr class="even">
<td><p>select_all_t1_engineers</p></td>
<td><p>Select all T1 Engineers</p></td>
<td><p>added by ghaleon</p></td>
</tr>
<tr class="odd">
<td><p>select_all_t2_podstations</p></td>
<td><p>Select all T2 Engineering Podstations</p></td>
<td><p>added by ghaleon</p></td>
</tr>
<tr class="even">
<td><p>select_all_tml</p></td>
<td><p>Select all TML</p></td>
<td><p>added by ghaleon</p></td>
</tr>
<tr class="odd">
<td><p>select_anti_air_fighters</p></td>
<td><p>Select all Air Fighters</p></td>
<td><p>added by ghaleon</p></td>
</tr>
<tr class="even">
<td><p>select_gunships</p></td>
<td><p>Select all Gunships</p></td>
<td><p>added by ghaleon</p></td>
</tr>
<tr class="odd">
<td><p>Render_SelectionSet_Names</p></td>
<td><p>Toggles display of group names</p></td>
<td><p>added by ghaleon</p></td>
</tr>
<tr class="even">
<td><p>Render_Custom_Names</p></td>
<td><p>Toggles display of custom names</p></td>
<td><p>added by ghaleon</p></td>
</tr>
<tr class="odd">
<td><p>Render_Unit_Bars</p></td>
<td><p>Toggle display of names and bars of any kind</p></td>
<td><p>added by ghaleon</p></td>
</tr>
<tr class="even">
<td><p>Render_Icons</p></td>
<td><p>Toggle display of Strategic Icons</p></td>
<td><p>added by ghaleon</p></td>
</tr>
<tr class="odd">
<td><p>Always_Render_Strategic_Icons</p></td>
<td><p>Toggle strategic icon cutoff</p></td>
<td><p>added by ghaleon</p></td>
</tr>
<tr class="even">
<td><p>Kill_Selected_Units</p></td>
<td><p>Immediately kill selected units</p></td>
<td><p>added by ghaleon</p></td>
</tr>
<tr class="odd">
<td><p>Kill_All</p></td>
<td><p>Immediately kill all of your units</p></td>
<td><p>added by ghaleon</p></td>
</tr>
<tr class="even">
<td><p>Show_Bandwidth_Usage</p></td>
<td><p>Show bandwith usage window</p></td>
<td><p>added by ghaleon</p></td>
</tr>
</tbody>
</table>

GAZ UI Hotkeys

## Compatibility notes

AZUI will not work while template names and detailed unit view are
enabled.

## Special Thanks

-   Goom for the very excellent original GUI mod.
-   norem for Factory Build Queues and also some of thehotkeys.
-   ghaleon for his many additional modules listed above,and also for
    doing all the work integrating them into v6 :)
-   Thygrrr for the smart economy indicators, and nicer Strat Build
    Icons.
