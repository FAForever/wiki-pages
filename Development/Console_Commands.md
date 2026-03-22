---
title: Console Commands
description: 
published: true
date: 2026-03-22T23:04:45.680Z
tags: 
editor: markdown
dateCreated: 2024-03-20T08:55:22.059Z
---

# Console Commands

To understand this page, you need to understand the syntax describing commands:

| Symbol |	Meaning |
| --- | --- |
| <value_name> | A required value that you provide |
| [value_name] | Everything inside is optional |
| [value_name...] | This value is repeatable |
| value_name | value_name	The left or right side are valid |



| Syntax | Description |
| --- | --- |
| AddBeam | Add a test beam into the world |
| `AddImpulse <x> <y> <z>` | Adds impulse to a flying air unit, affected by unit mass. |
| AddLightParticle | Add a light to the world under the cursor |
| AddSplat | Add a splat to the world underneath the cursor |
| AI_DebugArmyIndex | Set up a army index for debugging purposes |
| AI_DebugCollision | Toggle on/off collision detection |
| AI_DebugIgnorePlayableRect | Toggle on/off ignore playable rect |
| ai_FreeBuild | Unit build costs are 0 |
| ai_InitialEnergyCurrency | Initial currency of energy economy. |
| ai_InitialEnergyCurrencyMax | Initial currency of energy economy. |
| ai_InitialMassCurrency | Initial currency of mass economy. |
| ai_InitialMassCurrencyMax | Initial currency of mass economy. |
| ai_InstaBuild | Units build instantly. |
| AI_RenderBombDropZone | Toggle on/off rendering of bomb drop zone |
| AI_RenderDebugAttackVectors | Toggle on/off rendering of debug base attack vectors |
| AI_RenderDebugPlayableRect | Toggle on/off rendering of debug playable rect |
| AI_RunOpponentAI | Turns on or off Opponent AI |
| ai_SteeringAirTolerance | Tolerance used to detect whether an aircraft has reached its destination. |
| AirLookAheadMult | Alter the air units look ahead distance |
| ANI_DumpSkeleton | Dump the skeleton for the selected entity |
| BeginLoggingStats | Begin logging stats |
| BlingBling | Cash money yo |
| cam_DefaultLOD | default value for camera level-of-detail scaling factor |
| cam_DefaultMiniLOD | Default LOD for mini-map |
| cam_EntityBoxExpand | How much to expand the entity box when targetting entity |
| cam_FarFOV | FOV to use for perspective camera at farthest zoom, in degrees |
| cam_FarPitch | Pitch of camera at farthest zoom, in degrees |
| cam_Free | Allow the camera to remain rotated |
| cam_HighLOD |  |
| cam_LowLOD |  |
| cam_MediumLOD |  |
| cam_MinSpinPitch | The min pitch resulting from a spin |
| cam_NearFOV | FOV to use for perspective camera at nearest zoom, in degrees |
| cam_NearPitch | Pitch of camera at nearest zoom, in degrees |
| cam_NearZoom | Closest mouse can zoom in to terrain |
| cam_PanSpeed | How fast the camera pans. |
| cam_SetLOD | Set the lod scale factor for a camera |
| cam_ShakeMult | How much camera shake to allow. |
| cam_SpinSpeed | How fast mouse spins camera, in degrees across screen size |
| cam_TrackProjectileTimeout | Delay after tracking a projectile. |
| cam_ZoomAmount | How far to zoom in response to the mouse wheel. |
| cam_ZoomSpeedLarge | How fast the camera actually moves in response to a large zoom. |
| cam_ZoomSpeedSmall | How fast the camera actually moves in response to a small zoom. |
| ClearStats | Clear stats starting with given parent |
| CON_Echo | Echo out input to function. |
| CON_ExecuteLastCommand | Repeat the last command. |
| CON_ListCommands | List all console commands and variables. |
| con_TestVar | Test variable - not used. |
| con_TestVarBool | Test variable - not used. |
| con_TestVarFloat | Test variable - not used. |
| con_TestVarStr | Test variable - not used. |
| con_TestVarUByte | Test variable - not used. |
| CopySelectedUnitsToClipboard | Copy all the selected units to the clipboard. |
| CreateProp | Spawn a prop underneath the mouse cursor |
| CreateUnit | spawn a unit by id at the mouse cursor or specified location, case sensitive |
| d3d_AntiAliasingSamples |  |
| d3d_ForceDirect3DDebugEnabled | Disable shader optimization and allow D3D debugging. |
| d3d_ForceSoftwareVP | Force D3d to do vertex processing in software. |
| d3d_NoPureDevice | Use a non-pure D3D hardware device. |
| d3d_UseRefRast | Force D3d to do rasterization in software. |
| d3d_WindowsCursor |  |
| DamageUnit | Damage the selected unit (negative values heal) |
| dbg | Enable/Disable debug overlay |
| dbg_Metronome | Tick a metronome every tick. |
| dbg_MonitorAddressSpace | If true, monitor address space usage. |
| Debug_Assert | Fail an assertion (for debugging purposes) |
| Debug_Crash | Cause a crash (for debugging purposes) |
| Debug_Error | Log an error string (for debugging purposes) |
| debug_movie | debug movie output |
| Debug_Throw | Throw a std::exception. |
| Debug_Warn | Log a warning string (for debugging purposes) |
| DebugAIStatesOff | debug function to show some AI states |
| DebugAIStatesOn | debug function to show some AI states |
| DebugClearBuildTemplates | debug clear and disable the build templates. |
| DebugDumpArmyStats | Dump current stats for army index. |
| DebugGenerateBuildTemplateFromSelection | debug generate and enable build templates from the current selection. |
| DebugMoveCamera | Debug function for moving the camera in sim script. |
| DebugSetConsumptionActive | debug function to turn selected units consumption of resources into active state |
| DebugSetConsumptionInActive | debug function to turn selected units consumption of resources into inactive state |
| DebugSetPlayableRect | Set the playable rect of the map (minX, minZ, maxX, maxZ). |
| DebugSetProductionActive | debug function to turn selected units production of resources into active state |
| DebugSetProductionInActive | debug function to turn selected units production of resources into inactive state |
| DestroyAll | Destroy all units.  If any optional army indices are supplied, destroy those army's units. |
| DestroySelectedUnits | destroy selected units. |
| DoSimCommand | do a sim command. |
| dump_Frame | Dump a single video frame. A directory can be specified, otherwise it will prompt for one. |
| dump_Frames | Toggle dumping of video frames. |
| dump_outputFrameNumber | Starting frame to dump on |
| dump_Rate | Frame rate to use for movie dumps |
| DumpActiveLoops | List all active entity loops |
| DumpCamera | Dump out camera position data for the editor |
| DumpPreloadedTextures | Dump debug texture info |
| DumpUnits | Print out units in play |
| ed_EnableHook |  |
| efx_AttachEmitter | Attach an emitter to selected unit, must specify bone name and blueprint |
| EFX_CreateEmitterWindow | Create emitter control window |
| efx_NewEmitter | Create an emitter, must specify blueprint |
| efx_ParticleWaterSurface | Sort order at which particles start rendering under water |
| efx_WaterOffset | Amount that particles which are clamped to the waters surfaces are offset from it. |
| efx_WaveCutoff | Shoreline LOD cutoff |
| EndLoggingStats | End logging stats |
| ExecutePasteBuffer | Execute paste buffer in clipboard. |
| exit | Exit the application. |
| FindUnit | Find a unit by a (case insensitive) string contained in its description. |
| fog_DistanceFog | Distance fog enabled? |
| fog_OffsetMultiplier | amount to fudge offset by to make fog go away as we zoom out |
| GetVersion | Get game version |
| graphics_Fidelity | current graphics fidelity setting |
| graphics_FidelitySupported | maximum graphics fidelity supported |
| imap_debug | Toggle influence map debug info. |
| imap_debug_grid | Toggle influence map debug grid info. |
| imap_debug_grid_army | Set influence map debug grid for which army threat type. |
| imap_debug_grid_type | Set influence map debug grid threat type. |
| imap_debug_path_graph | Toggle map hints path graph. |
| IN_BindKey | Specify a key combo and a console command, binds console command to key |
| IN_DumpKeyBindings | Shows all the key bindings |
| IN_DumpKeyNames | Shows all the key names |
| IN_SetKeyName | Set a key name to map to a key code |
| IssueCommand | Issue the buildSilo/dive/stop command to the selected units. |
| KillAll | Kill all units |
| KillSelectedUnits | kill selected units. |
| lob_IgnoreNames | Comma seperated list of names of people to ignore.  For debugging purposes. |
| Log | Log a string (for debugging purposes) |
| LotsOfProps | spawn 100 props all over the map 2nd Arg = name of prop |
| LUA | Run a bit of lua code. |
| LUADOC | Dump out documentation for Lua functions |
| mesh_Rebatch | Override mesh batch settings |
| NeedRefuelThresholdRatio | Start looking for refueling platform when fuel ratio drops below this point |
| NeedRepairThresholdRatio | Start looking for refueling platform when health ratio drops below this point |
| net_AckDelay | Number of milliseconds to delay before sending ACKs |
| net_CompressionMethod | Compression method, 0=none, 1=deflate.  Only takes effect when connections are first established. |
| net_DebugCrash | If true, crash. |
| net_DebugLevel | Amount of network debug spew |
| net_Lag | Lag, in milliseconds. |
| net_LogPackets | Log all incomming/outgoing packets. |
| net_MaxBacklog | Maximum number of bytes to backlog to any one client. |
| net_MaxResendDelay | Maximum number of milliseconds to delay before resending a packet. |
| net_MaxSendRate | Maximum number of bytes to send per second to any one client. |
| net_MinResendDelay | Minimum number of milliseconds to delay before resending a packet. |
| net_ResendDelayBias | The resend delay is ping*new_ResendPingMultiplier+net_ResendDelayBias. |
| net_ResendPingMultiplier | The resend delay is ping*new_ResendPingMultiplier+net_ResendDelayBias. |
| net_SendDelay | Number of milliseconds to delay before sending Data |
| NoDamage | Disables all damage to units when set. |
| p4_Edit | Check out file(s) from perfoce |
| p4_IsOpenedForEdit | Is the specified file opened for edit? |
| path_ArmyBudget | Budget for each army to do pathfinding each tick |
| path_BackgroundBudget | Maximum number of steps to run pathfinder in background |
| path_BackgroundUpdate | Update pathfinding tables in background |
| path_GeneratePreview | Do a pathfind for the UI preview |
| path_MaxInstantWorkUnits | Budget for instant pathfinds by the AI |
| path_TimeoutPreview | Maximum number of ticks to allow pathfinder preview to take |
| path_UnreachableTimeoutSearchSteps | Maximum number of ticks to allow a single pathfind to take for an unreachable path |
| PathDebug | Debug the path finder |
| PopupCreateUnitMenu | Popup the create unit menu. |
| PrintStats | Test the stat system |
| ProcessInfoPair | set the assist mode flag for the selected units. |
| Purge | Purge all entities of a specified type .  If any optional army indices are supplied, destroy those army's entities. |
| quit | Quit the session. |
| RandomElevationOffset | Alter random non-combat elevation offset so plane don't all stick on the same plane |
| range_Fill |  |
| range_InnerThicknessCoeff |  |
| range_OuterThicknessCoeff |  |
| range_RenderBuild |  |
| range_RenderHighlighted |  |
| range_RenderSelected |  |
| recon_debug | Show debug recon info for specified army index |
| ReconFlush | Flush all recon databases (destroys all blips) |
| ren_BandwidthDisplayKernel | Width of bandwidth filter (in seconds). |
| ren_BandwidthDisplaySeconds | Number of seconds of bandwidth data to display. |
| ren_Beams | Render the beam fx. |
| ren_BgLowerBound |  |
| ren_bicubicnormals | Sample normal map basis using bicubic filter |
| ren_Bloom | Render Blooms? |
| ren_BloomBlurCount | Bloom Blur Count |
| ren_BloomBlurKernelScale | Amount to scale blurred amount by. |
| ren_BloomGlowCopyScale | Scale when copying glowing stuff to glow buffer before blur |
| ren_BorderSize | Size of edge border |
| ren_ClipDecalLevel | Level at which we clip decals for super quick reject |
| ren_ClipDecals | Clip Decals vertex count |
| ren_Clutter | Render clutter |
| ren_ClutterRadius |  |
| ren_DecalAlbedoLodCutoff | Fudge factor for decal cutoff on zoom out for albedos |
| ren_DecalFadeFraction | fraction (0..1) of their range that decals start to fade |
| ren_DecalFidelity |  |
| ren_DecalFlatTol | flatness tolerance |
| ren_DecalNormalLodCutoff | Fudge factor for decal cutoff on zoom out for normals |
| ren_DecalOverDraw | Render overdraw display for decals |
| ren_Decals | Render Terrain Decals. |
| ren_ErrorCache | use error threshold cache? |
| ren_fog | Do we render fog of war, rendering only no effect on database. |
| ren_FogIntensity | intensity of gray fog |
| ren_FogOfWar | Draw terrain with fog-of-war. |
| ren_ForceUpdateMinimapTerrain | Update the terrain tesselation/decals if it's a minimap |
| ren_FrameTimeSeconds | Number of seconds to display. |
| ren_Fx | Render FX? |
| ren_GenerateMesh | Generate a new mesh or use the old one? |
| ren_glowingDecals | Render glowing decals |
| ren_HideSecondary | Hide secondary views |
| ren_IgnoreDecalLOD | Force decals to render regardless of LOD |
| ren_MapBorderAdd | Add a mesh to the map border list |
| ren_MapBorderClear | Clear all map border meshes |
| ren_MeshDissolve | Fade mesh alpha from 1.0 to 0.0 |
| ren_MeshDissolveCutoff |  |
| ren_MeshSkinned | toggle rendering of meshes which have and use skeletons |
| ren_MeshStatic | toggle rendering of meshes which do not have or ignore skeletons |
| ren_MipSkipLevels |  |
| ren_NewFogUpdate | Use new fog update code |
| ren_NewPipeline |  |
| ren_NormalDecals | Render Normal Decals |
| ren_Oblivion |  |
| ren_OnlyFirstView | Render only the first view in the list |
| ren_PlayableBoundary |  |
| ren_Ranges |  |
| ren_Reflection | Render reflection? |
| ren_Refraction | Render refraction? |
| ren_RegenShore | Regenerate shoreline (editor only) |
| ren_RenderNothing | Render nothing? |
| ren_Select | Render select meshes? |
| ren_SelectBoxes | Toggle selection box rendering |
| ren_SelectBracketMinPixelSize | Minimum selection bracket thickness in pixels. |
| ren_SelectBracketSize | Default selection bracket thickness |
| ren_SelectColor | What color do we want the selection box? |
| ren_SelectionHeightFudge | How far off the ground selection boxes are fudged |
| ren_SelectionSizeFudge | How much selection box extents are fudged (multiplier) |
| ren_ShadowBias | Constant shadow bias |
| ren_ShadowBlur | Toggle shadow blurring |
| ren_ShadowCoeff |  |
| ren_ShadowLOD | At what LODMetric do we stop rendering shadows |
| ren_Shadows | Render Shadows? |
| ren_ShadowSize | Sizeof shadow texture |
| ren_ShoreErrorCoeff |  |
| ren_Shoreline | Render shoreline |
| ren_ShorelineCutoff | Shoreline LOD cutoff |
| ren_ShowBandwidthUsage | Show the amount of network bandwidth we are using. |
| ren_ShowBoneNames | Show bone names |
| ren_ShowDirtyTerrain | Show or hide the dirty terrain bits. |
| ren_ShowFrameTimes | Graphically show the frame times. |
| ren_ShowNetworkStats | Show various network stats. |
| ren_ShowNormals | Variable to track show/hide normals rendering. |
| ren_ShowSkeletons | Show mesh skeletons |
| ren_ShowWireframe | Variable to track show/hide wireframe rendering. |
| ren_Skirt | Use new fog update code |
| ren_SkyDome | Render sky |
| ren_Splats | Render Terrain splats. |
| ren_SyncTerrainLOD | Distance at which to start display terrain sync changes |
| ren_TeamColorLookupCount | Number of 'channels' in team color lookup texture. |
| ren_Terrain | Show or hide the terrain. |
| ren_Trees | Show or hide the trees. |
| ren_TTerrainGlow | Render the terrain using TTerrainGlow |
| ren_Ui | Render UI? |
| ren_UnitSelectionScale | How much unit selection box extents are scaled (multiplier) |
| ren_UnitSilhouette |  |
| ren_ViewError |  |
| ren_Water | Show or hide the water. |
| ren_WorldBorder | Render UI world border frame? |
| RenameUnit | Give selected unit a custom name, or with no parameters print name |
| res_AfterPrefetchDelay | Number of milliseconds to nap after prefetching something.  So the prefetcher thread doesn't bog us down too much. |
| res_EnablePrefetching | If true, enable prefetching. |
| res_PrefetcherActivityDelay | Number of seconds to delay prefetching after there is foreground disk activity. |
| res_SpewLoadSpam | If true, spew spam with each resource load. |
| rule_BlueprintReloadDelay | seconds to delay before reloading a blueprint once we notice that it has changed. |
| rule_Paranoid | Paranoid mode for RULE system, print all error messages. |
| SallyShears | Reveal entire map. |
| SC_AntiAliasingSamples |  |
| SC_CameraScaleLOD |  |
| SC_CreateEntityDialog | Create object editing box for the primary selected unit |
| sc_FrameTimeClamp | Minimum time between frames, in milliseconds |
| SC_LuaDebugger | Open Lua debugger window |
| SC_PrimaryAdapter |  |
| SC_SecondaryAdapter |  |
| sc_SkipIntro | Skip intro movies |
| SC_StartMemoryLog | Start up memory logging to filename |
| SC_StopMemoryLog | Stop memory logging |
| SC_ToggleCursorClip | Set the cursor clip to either the pre-launch clip or the current clip |
| SC_VerticalSync |  |
| `ScenarioMethod <name>` | Runs a lua function inside the Sim's `ScenarioInfo.Env` table. |
| SetArmyColor | SetArmyColor(army,r,g,b) |
| SetFocusArmy | Pass in army index or -1 |
| shadow_Fidelity | current shadow fidelity setting |
| shadow_FidelitySupported | maximum shadow fidelity supported |
| ShowArmyStats | Show engine statistics |
| ShowRaisedPlatforms | Turns on or off rendering of raised platform for tweaking and setting up purposes |
| ShowStats | Show engine statistics |
| sim_ChecksumPeriod | How many beats between checksums. |
| sim_DebugCheats | Log a backtrace when we detect a cheat. |
| sim_DebugCrash | Crash the sim. |
| sim_DebugDelay | Milliseconds to delay each sim tick to simulate a slow sim. |
| sim_Gravity | Show or change the current gravity.  Units are ogrids/(second^2) |
| sim_Interlocked | If true, force the sim and UI threads to run interlocked. |
| sim_IssueThreadDebugLevel | How much debug spam to spew from the issue thread. |
| sim_KeepAllLogFiles | If true, keep all long files instead of just the ones for beats that appear out-of-sync. |
| sim_LogSize | How many ticks to log before flushing files. |
| sim_ReportCheats | Report cheating when cheats are enabled. |
| sim_ShowDamage | Show debug damage info |
| sim_TestFunc | Test function - not used. |
| sim_TestVar | Test variable - not used. |
| sim_TestVarBool | Test variable - not used. |
| sim_TestVarFloat | Test variable - not used. |
| sim_TestVarStr | Test variable - not used. |
| sim_TestVarUByte | Test variable - not used. |
| SimAssert | Fail an assertion (for debugging purposes) |
| SimCrash | Cause a crash (for debugging purposes) |
| SimError | Log an error string (for debugging purposes) |
| SimLog | Log a string (for debugging purposes) |
| SimLua | Run some lua code in the sim's Lua. |
| SimWarn | Log a warning string (for debugging purposes) |
| SkipUIChecks | Don't perform any command validation in UI |
| snd_CheckDistance | Do distance checks for sound culling. |
| snd_CheckLOS | Do LOS checks for sound culling. |
| snd_ExtraDoWorkCalls | Enable mid-frame DoWork calls. |
| snd_SpewSound | Spew debug sound info |
| StartCommandMode | Set the UI context for some commands. |
| TeleportSelectedUnits | teleport selected units. |
| timestamp | Dump out EXE timestamp |
| TrackStats | Begin/End tracking stats of selected units. |
| tree_AccelFactor | How quickly falling trees accelerate |
| tree_DampFactor | Damping on swaying trees (0 to 1) |
| tree_SpringFactor | How quickly swaying trees spring back |
| tree_UprootFactor | How far to raise falling trees up out of the ground |
| ui_AlwaysRenderStrategicIcons | When true, strategic icons always render, even when zoomed in |
| UI_ApplySelectionSet | Takes a selection set name and applies the selection |
| ui_ArrowKeysScrollView | Toggle if the arrow keys scroll the main view |
| ui_BuildPlaceTarmacAlpha | Tarmac alpha for buildings that are about to be placed |
| ui_CommandClickScale | Scale applied to the click distance size of command waypoints |
| ui_CommandGraphMaxNodeUnits | Limits the size of the waypoints |
| UI_CreateHead1Map | Destroys anything on head 1 and shows a full screen map in its place |
| ui_CurveSegments | How many segments to subdivide curves into |
| ui_CurveSmoothness | How big to make curves when drawing command previews |
| ui_CustomNameColor | Color of the custom name display |
| ui_CustomNameFontSize | Point size of the custom name display |
| ui_CutsomNameFont | Font family name of the custom name display |
| ui_DebugAltClick | Enable ALT+Click debug command to switch armies |
| ui_DisableCursorFixing | Allows you to toggle the cursor fixing functionality that is used for the mouse-controlled camera spinning/scrolling |
| ui_DragSelect2D | Use a 2D (screen-space) drag-selection box |
| ui_DrawPathPreview | Turns on/off the arrow line |
| UI_DumpControls | Dumps information about all controls to current log target. |
| UI_DumpControlsUnderCursor | Dumps all controls under the cursor to the debug log |
| UI_ExpandCurrentSelection | Expand selection to all units in view that is found in our current selection group |
| ui_ExtractSnapTolerance | Sets the extraction unit 'snap-to' tolerance (in meters) for building.  Increase this to make it easier to auto-snap to extraction sites. |
| ui_FootprintMinThickness | Mimimum render size for the footprint outline. |
| ui_ForceLifbarsOnEnemy | force lifebars on for enemy units |
| UI_forceWeaponsToYellow | Force all minimap weapon fire to yellow |
| ui_FuelBarColor | The color of the secondary Fuel bar |
| ui_fuelbarHeight | size of the fuel bar as a fraction of the bar height |
| ui_FuelEmptyBlinkRate | Blink timer scale for empty fuel |
| ui_FuelWarningColor | The color of the feul warning flash |
| ui_KeyboardPanAccelerateMultiplier | How much faster the camera pans when accelerated |
| ui_KeyboardPanSpeed | How fast arrow keys pans camera |
| ui_KeyboardRotateAccelerateMultiplier | How much faster the camera rotates when accelerated |
| ui_KeyboardRotateSpeed | How fast ins/del rotate camera |
| ui_LifeBarBadColor | The color of the lifebar when there is poor health |
| ui_LifeBarBadCutoff | The percent of health where the life bar changes from bad to medium |
| ui_LifeBarGoodColor | The color of the lifebar when there is good health |
| ui_LifeBarGoodCutoff | The percent of health where the life bar changes from medium to good |
| ui_lifebarHeight | height of health/fuel bar in ogrids |
| ui_LifebarLOD | LOD Cutoff for health bars |
| ui_LifeBarMedColor | The color of the lifebar when there is medium health |
| ui_LifebarOffset | Y Offset in ogrids of all lifebars |
| ui_LifebarWidth | width of health/fuel bar in ogrids |
| UI_Lua | Run lua code in the appropriate UI lua state. |
| UI_MakeSelectionSet | Takes a name, and makes a named selection set from the current selection |
| ui_MaxExtractSnapPixels | Allows us to put a pixel cap on the snap tolerance (in case we are zoomed in close. |
| ui_MaxTextLOD | LOD level that timer text dissapears |
| ui_MaxWaypointSize | Set the maximum pixel size of a waypoint |
| ui_MinExtractSnapPixels | Allows us to put a pixel cap on the snap tolerance (in case we are zoomed out relatively far. |
| ui_MinWaypointSize | Set the minimum pixel size of a waypoint |
| ui_NisRenderIcons | nis toggle for strat icons, also removes pause and diabled icons |
| ui_PathPreview | Turns on/off the pathfinding preview line |
| ui_PathSmoothness | How big to make curves when drawing path preview |
| ui_ProgressBarColor | The color of the secondary Construction Progress bar |
| UI_Quit | Drives quit behavior of the game depending on the state of the UI |
| ui_RenderCustomNames | toggle custom name display |
| ui_RenderIcons | toggle strategic icons on/off |
| ui_RenderSelectionSetNames | toggle selection set names on/off |
| ui_RenderUnitBars | render unit life/fuel bars? |
| UI_RenProectileTrailWidth | The half width, in pixels, of the projectile trail |
| UI_RenProjectileArcsSampleInterval | How often the position is updated for the projectile trail |
| UI_RenProjectileGlow | Toggle projectile icon glow |
| UI_RenProjectileGlowMax | Maximum glow alpha on projecile icon |
| UI_RenProjectileGlowMin | Minimum glow alpha on projectile icon |
| UI_RenProjectileGlowPeriod | The period in which the projectile icon glow will pulse from min to max to min |
| UI_RenProjectileIcons | toggle projectile icons on/off |
| UI_RenProjectileTrailColor | ARGB value of the projectile trail |
| UI_RenResources | toggle resource icons on/off |
| UI_ResetView | Reset a named camera to the default view |
| UI_ResourceLODCutoff | When to draw icons instead of resource deposit textures |
| UI_RotateLayout | Cycles through all available layouts |
| UI_RotateSkin | Cycles through all available skins |
| ui_ScreenEdgeScrollView | Toggle if the mouse on the sides of the main window will scroll the view (fullscreen only) |
| UI_SelectAnything | Debug to allow UI to select anything |
| UI_SelectByCategory | Select a set of units by category |
| ui_SelectionSetNamesColor | Color of the selection set names |
| ui_SelectTolerance | Sets the unit click tolerance (in pixels) for selection.  Increase this to make units have a larger selection box. |
| UI_SetSkin | Sets a new skin |
| ui_ShieldBarColor | The color of the secondary Shield bar |
| UI_ShowControlUnderMouse | Highlights the control currently under the mouse |
| UI_ShowRenameDialog | Display the rename unit dialog during a game |
| ui_StrategicIconBlinkDuration | How long to blink icon when unit is damage |
| ui_StrategicIconBlinkRate | Blink timer scale for strategic icons on damage |
| UI_StrategicProjectileLOD | At what LODMetric do we draw projectile pixels on strategic view |
| UI_ToggleGamePanels | Hide/show the UI panels in game, and expands the world view to fill the screen when panels are hidden. |
| UI_TrackUnit | track selected units. |
| ui_WaypointLineScale | Scale applied to the calculated waypoint line size |
| ui_WindowedAlwaysShowsCursor | Always show cursor in windowed mode, regardless of show/hide |
| WeaponTerrainBlockageTest | Toggle on/off wepaon collision tests against terrain blockages |
| WIN_ShowLogDialog | Explicit show/hide log dialog box |
| WIN_ToggleLogDialog | Show/hide log dialog box |
| WLD_AdvanceBeat | Advance the sim one beat. |
| wld_ClientDebugDump | Dump out debug info about the network connections |
| WLD_DecreaseSimRate | Decrease the game speed. |
| WLD_GameSpeed | Set a new game speed |
| WLD_IncreaseSimRate | Increase the game speed. |
| WLD_ResetSimRate | Increase the game speed. |
| WLD_RestartBeat | Restart rendering the current beat. |
| wld_RunWithTheWind | If true, run beats as fast as we can. |
| WLD_SingleStep | Single-step the sim one tick. |
| wld_SkewRateAdjustBase | How much to adjust the sim rate based on one beat of skew. |
| wld_SkewRateAdjustMax | Max amount to adjust the sim rate due to skew. |
| wnd_DefaultCreateHeight | Minimum initial window height |
| wnd_DefaultCreateWidth | Minimum initial window width |
| wnd_MinCmdLineHeight | Minimum command line height |
| wnd_MinCmdLineWidth | Minimum command line width |
| wnd_MinDragHeight | Minimum drag-resize height |
| wnd_MinDragWidth | Minimum drag-resize width |
| WxInputBox | Text the WWxInputBox dialog. |
| ZeroExtraStorage | Set energy and mass extra storage to 0 |