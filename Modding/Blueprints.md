---
title: Blueprints
description: A blueprint is a file within Supreme Commander that describes a unit
published: true
date: 2023-03-29T19:34:57.186Z
tags: modding
editor: markdown
dateCreated: 2022-06-02T16:40:29.156Z
---

# Blueprint
A blueprint is a file within Supreme Commander that describes a unit. These are .bp files inside gamedata.scd. Within that file the blueprints are found in a subdirectory of gamedata\units\. For instance, `gamedata\units\UAA0101\UAA0101_unit.bp` is the blueprint for the Aeon T1 Air Scout.

# Blueprint format
The following is documentation of the contents of a blueprint file. It is valid Lua code. The entire file is a call to UnitBlueprint with a large table. Below is an incomplete list of the fields and their purposes.

## Adjacency
The Adjacency section details [adjacency bonuses](/Learning/Adjacency-Bonus). There are 6 possible types. Each type contains a list of structure sizes and modifiers.

- **EnergyBuildBonus** - Energy consumption reduction, bestowed by energy production facilities.
- **EnergyMaintenanceBonus** - Energy consumption (for maintenance, i.e. shields, intel, etc.?) reduction, bestowed by energy production facilities.
- **EnergyProductionBonus** - Energy production increase, bestowed by energy storage facilities.
- **EnergyWeaponBonus** - Energy consumption (for weapons, esp artilleries) reduction, bestowed by energy production facilities.
- **MassBuildBonus** - Mass consumption reduction, bestowed by mass production facilities.
- **MassProductionBonus** - Mass production increase, bestowed by mass storage facilities.

Each of this attribute types needs modifiers per structure size. For example the settings of a tech 1 mass extractor would be:
```lua
Adjacency = {
	MassBuildBonus = {
		{
			Category = 'STRUCTURE SIZE4',
			Modifier = '-0.1',
		},
		{
			Category = 'STRUCTURE SIZE8',
			Modifier = '-0.05',
		},
		{
			Category = 'STRUCTURE SIZE12',
			Modifier = '-0.033333',
		},
		{
			Category = 'STRUCTURE SIZE16',
			Modifier = '-0.025',
		},
		{
			Category = 'STRUCTURE SIZE20',
			Modifier = '-0.02',
		},
	},
},
```

## AI
AI information for the unit.

```lua
AI = {
	AttackAngle = 'n', --  Under what angle the unit attacks its target after getting an attack order
	AutoSurfaceToAttack = 'true/false', -- Automatically surface to attack ground targets.
	BeaconName = 'string', -- This is the beacon that this unit will create under some circumstances.
	GuardFormationName = 'string', -- The formation name used for guarding this unit. Known formations: 'GuardFormation'
	GuardRadius = 'n', -- How far a unit on patrol will look off it's patrol path to go attack.
	GuardReturnRadius = 'n', -- Maximum range from the guarded unit before initiating return.
	GuardScanRadius = 'n', -- Guard range for the unit.
	InitialAutoMode = 'true/false', -- Initial auto mode behaviour for the unit.
	NeedUnpack = 'true/false', -- Unit should unpack before firing weapon.
	RefuelingMultiplier = 'n', -- This muliplier is applied when a staging platform is refueling an air unit.
	RefuelingRepairAmount = 'n', -- This amount of repair per second offered to refueling air units.
	TargetBones = 'string', -- Some target bones setup for other units to aim at instead of the default center pos.
},

```

## Air

Air control information for the unit.

```lua
Air = {
	AutoLandTime = 'n', -- Timer to automatically initiate landing on ground if idle.
	BankFactor = 'n', -- How much aircraft banks in turns; negative to lean out.
	BankForward = 'true/false', -- True if aircraft banks forward/back as well as sideways.
	BombDropThreshold = 'n', -- Distance from the target unit will start firing bombs.
	BreakOffDistance = 'n', -- Distance to break off before turning around for another attack run.
	BreakOffTrigger = 'n', -- Distance to target to trigger the breaking off attack.
	CanFly = 'true/false', -- Is the unit capable of flight?
	CirclingDirChange = 'true/false', -- Whether unit should ever change flight direction while circling.
	CirclingDirChangeFrequencySec = 'n', -- How often will it change direction when it's attack motion is back and forth, like a gunship.
	CirclingElevationChangeRatio = 'n', -- Elevation change ratio of unit when circling.
	CirclingFlightChangeFrequency = 'n', -- Frequency of flight pattern change for unit.
	CirclingRadiusChangeMaxRatio = 'n', -- Max circling radius ratio for unit.
	CirclingRadiusChangeMinRatio = 'n', -- Min circling radius ratio for unit.
	CirclingRadiusVsAirMult = 'n', -- Multiplier to the circling radius when targeting another air unit.
	CirclingTurnMult = 'n', -- Adjust turning ability when in circling mode.
	CombatTurnSpeed = 'n', -- Maximum combat turn speed of the unit for special maneuvers.
	EngageDistance = 'n', -- Distance to being engaging enemy target in attack task.
	FlyInWater = 'true/false', -- Can this unit fly under water?
	HoverOverAttack = 'true/false', -- Whether unit should hover over the target directly to attack. (Used for cases like the CZAR)
	KLift = 'n', -- Controller proportional parameter for vertical motion.
	KLiftDamping = 'n', -- Controller damping parameter for vertical motion
	KMove = 'n', -- Controller proportional parameter for horizontal motion.
	KMoveDamping = 'n', -- Controller damping parameter for horizontal motion.
	KRoll = 'n', -- Controller proportional parameter for roll changes.
	KRollDamping = 'n', -- Controller damping parameter for roll changes.
	KTurn = 'n', -- Controller proportional parameter for heading changes.
	KTurnDamping = 'n', -- Controller damping parameter for heading changes.
	LiftFactor = 'n', -- How much altitude the unit can gain/loose per second.
	MaxAirspeed = 'n', -- Maximum airspeed.
	MaxEngineThrust = 'n', -- Max thrust for the engine. Directly influences speed and acceleration.
	MaxEngineTorque = 'n', -- (?)(Found in various aircraft blueprints)
	MinAirspeed = 'n', -- Minimum combat airspeed.
	NeedToComputeBombDrop = 'true/false', -- Doesn't drop bombs until path is computed?
	PredictAheadForBombDrop = 'n', -- ??Time in seconds or distance to target??
	RandomBreakOffDistanceMult = 'n', -- Random multiplier applied to break off distance for winged aircrafts.
	RandomMaxChangeCombatStateTime = 'n', -- Random max time to switch combat state in seconds for winged aircrafts.
	RandomMinChangeCombatStateTime = 'n', -- Random min time to switch combat state in seconds for winged aircrafts.
	StartTurnDistance = 'n', -- Distance from target at which to start turning to align with it.
	TightTurnMultiplier = 'n', -- Additional turning multiplier ability during a tight turn maneuver.
	TransportHoverHeight = 'n', -- This transport will stay at this height when picking up and dropping off units.
	TurnSpeed = 'n', -- Regular turn speed of the unit.
	Winged = 'true/false', -- Does the unit use wings for forward flight?
},
```

## Audio
The Audio section describes the sounds that are associated with the unit. There are a large number of triggers for those sounds, listed below. Each trigger is given the result of a call to the Sound function. The Sound function takes three arguments. The first is the name of the bank that contains the sound. The second is the specific sound within that bank. The third is a setting that describes the level of detail at which the sound is played. This ensures that small ambient sounds from individual units aren't heard when the user has zoomed out too far to hear them.

`Activate` - `ActiveLoop` - `AirUnitWaterImpact` - `AmbientMove` - `AmbientMoveLand` - `AmbientMoveWater` - `BarrelLoop` - `BarrelStart` - `BarrelStop` - `BeamLoop` - `BeamStart` - `BeamStop` - `CaptureLoop` - `ChargeStart` - `Close` - `CommanderArrival` - `Construct` - `ConstructLoop` - `ConstructStart` - `ConstructStop` - `DeathExplosion` - `Destroyed` - `DoneBeingBuilt` - `EnhanceEnd` - `EnhanceFail` - `EnhanceLoop` - `EnhanceStart` - `EnterWater` - `Fire` - `FireUnderWater` - `FootFallGeneric` - `FootFallGenericSeabed` - `HoverKilledOnWater` - `Killed` - `Landed` - `Landing` - `Load` - `MoveSharpTurn` - `MuzzleChargeStart` - `NuclearLaunchDetectedAeon` - `NuclearLaunchDetectedCybran` - `NuclearLaunchDetectedUEF` - `NuclearMissileInterceptedAeon` - `NuclearMissileInterceptedCybran` - `NuclearMissileInterceptedUEF` - `Open` - `Pack` - `ReclaimLoop` - `Refueling` - `ShieldOff - ` - `ShieldOn` - `StartCapture` - `StartMove` - `StartMoveAir` - `StartMoveLand` - `StartMoveWater` - `StartReclaim` - `StopMove` - `StopMoveLand` - `StopMoveWater` - `SubmergeStart` - `SurfaceStart` - `TakeOff` - `Thruster` - `TransitionLand` - `TransitionWater` - `UISelection` - `Unload` - `Unpack` 

## AverageDensity

We store average density instead of an absolute mass value (units mass, not economic) so you don't have to change the mass value when the size of the unit changes. The mass is autocalculated via the Size * AverageDensity.
```lua
AverageDensity = 'n', -- Unit average density in tons / m^3 (Default is 0.49).
```
## BlueprintId
BlueprintId is used for modding an existing blueprint. An example for usage is BlueprintId = 'uel0101' which would be the UEF Land Scout.
```lua
BlueprintId = 'string',
```
## Buffs
```lua
Regen -- sets the bonus regen per verterancy level
```
## BuildIconSortPriority
This is set to an integer that describes the unit's position in the list of build icons.

**BuildIconSortPriority** = '**integer**',

## Categories
This is a list of capitalized strings that describe categories to which the unit belongs. Many other parts of the game refer to these categories to affect how units interact. For instance, [adjacency bonuses](/Learning/Adjacency-Bonus) only apply to other units that contain the STRUCTURE category. Below is an exhaustive list of categories.

AEON -
AIR -
AIRSTAGINGPLATFORM -
ANTIAIR -
ANTIMISSILE -
ANTINAVY -
ANTISUB -
ARTILLERY -
BENIGN -
BOMBER -
BUILTBYCOMMANDER -
BUILTBYEXPERIMENTALSUB -
BUILTBYQUANTUMGATE -
BUILTBYTIER1ENGINEER -
BUILTBYTIER1FACTORY -
BUILTBYTIER2COMMANDER -
BUILTBYTIER2ENGINEER -
BUILTBYTIER2FACTORY -
BUILTBYTIER3COMMANDER -
BUILTBYTIER3ENGINEER -
BUILTBYTIER3FACTORY -
CANTRANSPORTCOMMANDER -
CAPTURE -
CARRIER -
COMMAND -
CONSTRUCTION -
CONSTRUCTIONSORTDOWN -
COUNTERINTELLIGENCE -
CYBRAN -
DEFENSE -
DIRECTFIRE -
DRAGBUILD -
ECONOMIC -
ENERGYPRODUCTION -
ENERGYSTORAGE -
ENGINEER -
EXPERIMENTAL -
FACTORY -
GATE -
GROUNDATTACK -
HIGHALTAIR -
HOVER -
HYDROCARBON -
INDIRECTFIRE -
INTELLIGENCE -
LAND -
MASSEXTRACTION -
MASSFABRICATION -
MASSPRODUCTION -
MASSSTORAGE -
MOBILE -
NAVAL -
NEEDMOBILEBUILD -
NUKE -
OMNI -
OVERLAYANTIAIR -
OVERLAYOMNI -
OVERLAYRADAR -
PATROLHELPER -
POD -
PODSTAGINGPLATFORM -
RADAR -
RALLYPOINT -
REBUILDER -
RECLAIM -
RECLAIMABLE -
REPAIR -
SCOUT -
SELECTABLE -
SHIELD -
SILO -
SIZE4 -
SIZE8 -
SIZE9 -
SIZE12 -
SIZE16 -
SIZE20 -
SONAR -
STRATEGIC -
STRUCTURE -
SUBCOMMANDER -
SUBMERSIBLE -
TACTICALMISSILEPLATFORM -
TECH1 -
TECH2 -
TECH3 -
TELEPORTBEACON -
TRANSPORTATION -
TRANSPORTFOCUS -
UEF -
VISIBLETORECON -
WALL -

## CollisionOffsetX
Note: The collision offset ones are to move the collision box away from the center of the unit. It's used to extend the collision box of floating units (like engineers) below the water to allow torpedoes to hit them.
```lua
CollisionOffsetX = 'n', -- Offset collision by this much on the X Axis.
```
## CollisionOffsetY
```lua
CollisionOffsetY = 'n', -- Offset collision by this much on the Y Axis.
```
## CollisionOffsetZ
```lua
CollisionOffsetZ = 'n', -- Offset collision by this much on the Z Axis.
```
## CollisionShape
```lua
CollisionShape = 'string', -- Shape to use for collision db, 'None' for no collision. Allowed shapes: 'None', 'Box'
```
## Defense
Defense information for the unit.
```lua
Defense = {
    ArmorType = 'string', -- The armor type name; known armor types are 'Light', 'Normal', 'Commander', 'Structure'.
    Health = 'n', -- Starting health value for the unit.
    MaxHealth = 'n', -- Max health value for the unit. (It just could get higher through veteran buff or an enhancement)
    RegenRate = 'n', -- Amount of health to regenerate per second.
    Shield = { -- When a unit has a shield here are settings defined; Shield attributes are:
        OwnerShieldMesh = 'string', -- Define the PersonalShield_mesh when PersonalShield = true
        PassOverkillDamage = 'true/false'
        PersonalShield = 'true/false', -- Define a personal shield.
        ShieldEnergyDrainRechargeTime = 'n', -- The amount of time the shield takes to come back online when its disabled due to insufficient energy
        ShieldMaxHealth = 'n', -- The max health of the shield.
        ShieldRechargeTime = 'n', -- The time it takes for the shield to come back online when powered down
        ShieldRegenRate = 'n', -- The amount of health the shield regenerates, per second, when it's not taking damage
        ShieldRegenStartTime = 'n', -- The delay after getting hit by ordinance the shield starts recharging
        ShieldSize = 'n', -- The radius of the shield.
        ShieldVerticalOffset = 'n', -- How many supcom units the shield is moved up (or down if negative) from normal
        StartsOff = 'true/false', -- Appears to do nothing but seems to be meant to make the shield turned off by default
        StartOn = 'true/false', -- (?)
    },
ThreatLevel = 'n', -- Amount of threat this poses to the enemy.
},
```

## Description
This is the description of the unit. For example the description for the UEF tech 1 Tank MA12 Striker is `'<LOC uel0201_desc>Medium Tank'`. `<LOC xxx_desc>` is used for localisation which is defined in the strings_db.lua (in the file loc_XX.scd in the subdirectory \loc\XX\; XX is the shortcut for the localised language). If the localisation part is not set, the description in tags will be used for any language, which would be "Medium Tank" for this example.

**Description** = '**string**',

## Display
Here is anything defined thats needed for visual stuff(?)
```lua
Display = {
    Abilities = { 'string', }, -- Shows the abilities of the unit. Multiple abilities could be added like 'string1', 'string2', etc.
    AINames = { '<string1>', '<string2>', }, -- Names that the AI can use to name the unit, provided the AI is programmed to do this.
    AnimationActivate = 'string', -- The animation that is played when the unit is completed (seen in experimentals, e.g. Megalith - XRL0403)
    AnimationBuild = 'string', -- Animation that is played when the unit is building
    AnimationDeath = { -- Multiple animations could be added
        Animation = 'string', -- animation death file is linked here: '/units/UnitID/UnitID_??.sca'
        AnimationRateMax = 'n', -- the maximum speed this animation is played at
        AnimationRateMin = 'n', -- the minimum speed this animation is played at
        Weight = 'n', -- This number affects how often a death animation is used when there are more than one. This value is relative rather than absolute.
    },
    AnimationOpen = 'string', -- Animation open file is linked here: '/units/UnitID/UnitID_aopen.sca'
    AnimationPermOpen = '?', -- The animation that is played when the unit is done building
    AnimationSurface = '?', -- The animation that is played when the unit surfaces.
    AnimationUpgrade = 'string', -- The animation that is played when the unit is upgraded
    AnimationWalk = 'string', -- Animation walk file is linked here: '/units/UnitID/UnitID_??.sca'
    AnimationWalkRate = 'n', -- Controls the speed of the animation. Adjusting this number can cause or prevent "skating".
    BlinkingLights = '?', -- ?
    BlinkingLightsFx = '?',-- ?
    BuildAttachBone = '?', -- ?
    DamageEffects = '?', -- ?
    ForcedBuildSpin = '?', -- ?
    IdleEffects = {  -- Effects displayed when the unit is idle (e.g. glow beneath hovering units), multiple layers can be used.
        'string' = { -- Name of the layer where effects should be displayed.
            Effects = {
                { -- Multiple effects can be defined for a single layer, each of them must be in a block like that.
                    Bones = { 'string1', 'string2'... }, -- Names of bones to which the effect will be attached.
                    Offset = { 'n1', 'n2', 'n3', }, -- Controls position of the effect relatively to the bone it's attached to. n1, n2 and n3 are respectively x, y and z coordinates (0, 0, 0 by default).
                    Scale = 'n', -- Controls scale of the effect (1 by default).
                    Type = 'string', -- Defines what effect will be used.
                },
            },
        },
    },
    LayerChangeEffects = { -- Effects displayed when the unit changes layers (e.g. when an aircraft lands or takes off).
        'string' = { -- Defines for what transition the effects are created. 'string' is composed of 2 names of layers, first one is the old layer and the second is the new one. E.g.effects are needed for an aircraft landing, so the old layer is Air and the new one is Land, then the 'string' will be AirLand (LandAir would be the opposite - take off). Note: there is NO space between layer names.

            Effects = { -- Exactly as in IdleEffects 
            }, 
        },
    },
    Mesh = { -- ?
        IconFadeInZoom = 'n', -- The zoom level at which the strategic icon begins showing. Higher values increase how zoomed out you must be for the icon to appear.
        LODs = { -- Defines different Levels Of Detail, so that units become less detailed when player zooms out (to improve performance)
            {
                MeshName = 'string', -- lod0 file is linked here: '/units/UnitID/UnitID_LOD0.scm'
                AlbedoName = 'string', -- lod0 albedo file is linked here: '/units/UnitID/UnitID_Albedo.dds'
                NormalsName = 'string', -- lod0 normalsts file is linked here: '/units/UnitID/UnitID_NormalsTS.dds'
                SpecularName = 'string', -- lod0 specteam file is linked here: '/units/UnitID/UnitID_SpecTeam.dds'
                LODCutoff = 'n', -- Defines zoom level when this LOD is no longer used (higher value increases how zoomed out you must be).
                Scrolling = 'true/false', -- ?
                ShaderName = 'string', -- ? known ShaderName's: 'Unit', 'Insect', 'Seraphim'
            },
            {
                MeshName = 'string', -- lod1 file is linked here: '/units/UnitID/UnitID_lod1.scm'
                AlbedoName = 'string', -- lod1 albedo file is linked here: '/units/UnitID/UnitID_lod1_Albedo.dds'
                NormalsName = 'string', -- lod1 normalsts file is linked here: '/units/UnitID/UnitID_lod1_normalsTS.dds'
                SpecularName = 'string', -- lod1 specteam file is linked here: '/units/UnitID/UnitID_lod1_SpecTeam.dds'
                LODCutoff = 'n', -- Defines zoom level when this LOD is no longer used (higher value increases how zoomed out you must be)
                ShaderName = 'string', -- ? known ShaderName's: 'Unit', 'Insect', 'Seraphim'
            },
        },
    },
    MotionChangeEffects = { ? }, -- ?
    MovementEffects = { -- Effects displayed during movement of the unit.
        'string' = { -- Name of the layer for which the effects are displayed.
            Contrails = { -- Contrails shown behind aircraft (in SupCom usually behind tips of wings).
                Bones = { 'string1', 'string2', ... }, -- Names of the bones which will have the contrails attached.
            },
            Effects = { 
                -- As in IdleEffects
            }, 
            Treads = { -- For units with treads or wheels, e.g. tanks, UEF engineers.
                ScrollTreads = 'true/false', -- Should the treads be scrolled when unit is moving?
                TreadMarks = {
                    BoneName = 'string', -- Name of the bone to which the tread marks will be attached.
                    TreadMarks = 'string', -- Name of the tread marks to be used (e.g. light tank might have different than a heavier one).
                    TreadMarksInterval = 'n', -- Defines how often should they be created on the ground.
                    TreadMarksSizeX = 'n', -- <Defines how big/stretched should the tread marks be on the X axis.
                    TreadMarksSizeZ = 'n', -- Defines how big/stretched should the tread marks be on the Z axis.
                    TreadOffset = { 'n1', 'n2', 'n3', }, -- Defines the offset of tread marks to bone defined in BoneName. 'n1', 'n2', 'n3' are respectively x, y and z coordinates.
                },
            },  
        },
    },
    PlaceholderMeshName = 'string', -- ?
    SpawnRandomRotation = 'true/false', -- ?
    Tarmacs = { ? }, -- ?
    UniformScale = 'n', -- This is the scale of the unit size. This will only change the visual size, when changing this the collision hitbox should be adapted under SizeX, SizeY and SizeZ as well.
},
```
## Economy
Economy information for the unit.
```lua
    Economy = {
    AdjacentEnergyProductionMod = 'n', -- ?
    AdjacentMassProductionMod = 'n', -- ?
    AdjacentStructureEnergyMod = 'n', -- ?
    BuildableCategory = { 'string1', 'string2', }, -- This define what units could be produced.
    BuildCostEnergy = 'n', -- Energy cost to build this unit.
    BuildCostMass = 'n', -- Mass cost to build this unit.
    BuildRate = 'n', -- How fast this unit build other units.
    BuildTime = 'n', -- The needed time when producing this unit; This is only a factor of time, not the real time to produce the unit.
    InitialRallyX = 'n', -- Default rally point X for the factory.
    InitialRallyZ = 'n', -- Default rally point Z for the factory.
    MaintenanceConsumptionPerSecondEnergy = 'n', -- Amount that define which amount of energy the unit is consuming per second; Used for Shields.
    MaxBuildDistance = 'n', -- Maximum build range of the unit. The target must be within this range before the builder can perform operation.
    MaxEnergyUse = 'n', -- The maximum Amount of Energy the Unit can produce (see PARAGON xab1401)
    MaxMassUse = 'n', -- The maximum Amount of Mass the Unit can produce (see PARAGON xab1401)
    MinBuildTime = 'n', -- ?
    NaturalProducer = 'true/false', -- Produces resource naturally and does not consume anything.
    NeedToFaceTargetToBuild = 'true/false', -- Builder needs to face target before it can build/repair.
    ProductionPerSecondEnergy = 'n', -- Amount of energy produced per second.
    ProductionPerSecondMass = 'n', -- Amount of mass produced per second.
    RebuildBonusIds = { 'string', }, -- You will get bonus if you rebuild this unit over the wreckage of these wreckages. Multible BonusID's could be added.
    SacrificeMass = 'n', -- Builder will kill self but provide this amount of health to the unit it is helping.
    StorageEnergy = 'n', -- Enery storage capacity provided by this unit; This gets added to the main resource pool and is not stored in the unit itself.
    StorageMass = 'n', -- Mass storage capacity provided by this unit; This gets added to the main resource pool and is not stored in the unit itself.
    TeleportEnergyMod = 'n', -- Multiply by the unit's energy cost to get the energy per tick cost of teleporting.
    TeleportMassMod = 'n', -- Multiply by the unit's mass cost to get the mass per tick cost of teleporting.
    TeleportTimeMod = 'n', -- Multiply by the unit's build time to get the time required to teleport.
},
```
## Enhancements
Data about unit upgrades (ACU upgrades, for example).

## Footprint
Unit footprint. How many o-grids it'll take up in the pathfinder. If you don't specify this the game will use a 'best guess' based off its collision box. Although even if you do specify a footprint size, the pathfinder will still do a best match against the footprint definitions in footprints.lua to figure out the pathfinding blueprint. This generally is not something you need to worry about. Apart from the pathfinding, the footprint also specifies the dimensions of the o-grid to occupy (hit ctrl-alt-o to see the ogrid and occuption by footprints).


Keep this in mind wile using SkirtOffsetX = 'n',SkirtOffsetZ = 'n',SkirtSizeX = 'n', SkirtSizeZ = 'n', as these will be affected by the footprint.

Where not specified, these values will be filled in with data from the footprints.lua.
```lua
Footprint = {
    Flags = 'n', -- ?
    MaxSlope = 'n', -- ?
    MinWaterDepth = 'n', -- ?
    OccupancyCaps = 'n', -- ?
    SizeX = 'n', -- ?
    SizeZ = 'n', -- ?
},
```

## General
General information for the unit.
```lua
General = {
    CapCost = 'integer', -- Cost of the unit towards unit cap (default is 1.0)
    Category = 'string', -- ?
    Classification = 'string', -- ?
    CommandCaps = { -- Command capability flags for this unit; CommandCaps has following subcategories:
        RULEUCC_Attack = 'true/false', -- Whether the unit has an attack command.
        RULEUCC_CallTransport = 'true/false', -- Whether the unit can ask to be transported by a transport unit.
        RULEUCC_Capture = 'true/false', -- Whether the unit has a capture command.
        RULEUCC_CloakToggle = 'true/false', -- Whether the unit has a cloak toggle button.
        RULEUCC_Dive = 'true/false', -- Whether the unit has a dive toggle button (like on submarines).
        RULEUCC_Dock = 'true/false', -- Whether the unit has a dock button (like on planes).
        RULEUCC_GenericToggle = 'true/false', -- ?
        RULEUCC_Guard = 'true/false', -- Whether the unit can guard other units.
        RULEUCC_Ferry = 'true/false', -- Whether the unit has the ferry command (transports).
        RULEUCC_IntelToggle = 'true/false', -- Whether the unit has a toggle for intelligence (radar, sonar, cloaking, stealth, etc.).
        RULEUCC_JammingToggle = 'true/false', -- Whether the unit has a toggle for radar jamming.
        RULEUCC_Move = 'true/false', -- Whether the unit has a move command
        RULEUCC_Nuke = 'true/false', -- Whether the unit can be commanded to launch a strategic missile.
        RULEUCC_Overcharge = 'true/false', -- Whether the unit has the Overcharge command (ACU).
        RULEUCC_Patrol = 'true/false', -- Whether the unit has the patrol command.
        RULEUCC_Pause = 'true/false', -- Whether this unit can pause construction of units/structures
        RULEUCC_ProductionToggle= 'true/false', -- Whether this unit can pause some sort of production that also drains resources.
        RULEUCC_Reclaim = 'true/false', -- Whether the unit has the reclaim command.
        RULEUCC_Repair = 'true/false', -- Whether the unit has the repair command.
        RULEUCC_RetaliateToggle = 'true/false', -- Whether the unit can control the retaliation of it's weapons
        RULEUCC_Sacrifice = 'true/false', -- Whether the unit has the sacrifice command.
        RULEUCC_ShieldToggle = 'true/false', -- Whether the unit has an on/off toggle for a shield.
        RULEUCC_SiloBuildNuke = 'true/false', -- Whether the unit can be commanded to build strategic missiles.
        RULEUCC_SiloBuildTactical = 'true/false', -- Whether the unit can be commanded to build tactical missiles.
        RULEUCC_SpecialAction = 'true/false', -- ?
        RULEUCC_SpecialToggle = 'true/false', -- ?
        RULEUCC_StealthToggle = 'true/false', -- Whether the unit has an on/off toggle for the stealth ability.
        RULEUCC_Stop = 'true/false', -- whether the unit can issue a stop command to itself
        RULEUCC_Tactical = 'true/false', -- ?
        RULEUCC_Teleport = 'true/false', -- Whether the unit can be commanded to teleport itself (upgraded ACUs).
        RULEUCC_Transport = 'true/false', -- Whether the unit can be ordered to transport other units (transports).
        RULEUCC_WeaponToggle = 'true/false', -- ?
    },
    FactionName = 'string', -- Faction the unit belongs to. Factions are 'Aeon', 'Cybran' and 'UEF'.
    QuickSelectPriority = 'integer', -- Indicates unit has it's own avatar button in the quick select interface, and it's sorting priority.
    TarmacDecal = '?', -- ?
    TarmacGlowDecal = '?', -- ?
    TechLevel = 'string', -- This define the tech level. 'RULEUTL_Basic' for tech 1, 'RULEUTL_Advanced' for tech 2, 'RULEUTL_Secret' for tech 3 and 'RULEUTL_Experimental' for experimental.
    UnitName = 'string', -- The name of the unit.
    UnitWeight = 'n', -- ?
    UpgradesFrom = 'string', -- What unit, if any, was this unit upgrade from.
    UpgradesTo = 'string', -- What unit, if any, does this unit upgrade to.
},
```

## Intel
Intel information for the unit.
```lua
Intel = {
    Cloak = 'true/false', -- Single unit cloaking.
    CloakFieldRadius = 'n', -- How far our cloaking goes.
    FreeIntel = 'true/false', -- The intel is free. Without this the unit will try drain energy for it's intelligence (radar, sonar, etc) and turn off if you run out.
    JamRadius = {Max = 'n', Min = 'n',}, -- How far we create fake blips.
    JammerBlips = 'n', -- How many blips does a jammer produce
    OmniRadius = 'n', -- How far our omni coverage goes.
    RadarRadius = 'n', -- How far our radar coverage goes.
    RadarStealth = 'true/false', -- Single unit radar stealth.
    RadarStealthFieldRadius = 'n', -- How far our radar stealth goes.
    ReactivateTime = 'n', -- When you run out of power, how long until this unit turns back on.
    ShowIntelOnSelect = 'true/false', -- Show intel radius of unit if selected.
    SonarRadius = 'n', -- How far radar coverage goes.
    SonarStealth = 'true/false', -- Single unit sonar stealth.
    SonarStealthFieldRadius = 'n', -- How far our sonar stealth goes.
    SpoofRadius = {Max = 'n', Min = 'n',}, -- How far off displace blip.
    VisionRadius = 'n', -- How far we can see above water (and land?).
    WaterVisionRadius = 'n', -- How far we can see underwater.
},
```
Note: **RadarStealthField** is no valid blueprint attribute. It is found in URL0306_unit.bp and is only a mistake.

## Interface
Under interface the help text for an unit is defined. The usage is Interface = { HelpText = '<LOC uel0201_help>Medium Tank', }, while this would be the help text for the UEF tech 1 tank. The localisation part is working exactly the same as described under the category Description.
```lua
Interface = {
    HelpText = 'string',
},
```
## LifeBarHeight
```lua
LifeBarHeight = 'n', -- Height of lifebar in OGrids.
```
## LifeBarOffset
```lua
LifeBarOffset = 'n', -- Vertical offset from unit for lifebar.
```
## LifeBarRender
```lua
LifeBarRender = 'true/false', -- Should render lifebar or not.
```
## LifeBarSize
```lua
LifeBarSize = 'n', -- Size of lifebar in OGrids.
```
## Merge
Merge is used for moding an existing blueprint. With Merge = 'true' the BlueprintId must be set.
```lua
Merge = 'true/false',
```

## Physics
Here are the physic behaviors and similar defined.
```lua
Physics = {
    AttackElevation = 'n', -- Preferred attack height when attacking ground targets. (used by dive bombers)>
    BackUpDistance = 'n', -- Distance that the unit will just back up if it is easier to do so.
    BankingSlope = 'n', -- How much the unit banks in corners (negative to lean outwards).
    BuildOnLayerCaps = { -- Unit may be built on these layers (only applies to structures); Subcategories are:
        LAYER_Air = '?', -- If true, unit will leave factory flying.
        LAYER_Land = '?', -- If true, unit will be built standing or hovering on land.
        LAYER_Orbit = '?', -- if true, unit will be build in orbit (Like the Novax Sattelite pops out of its launching box in Orbit)
        LAYER_Seabed = '?', -- If true, unit will leave factory partly underwater (standing on the floor of the water body).
        LAYER_Sub = '?', -- If true, unit will leave factory completely submerged underwater (floating or standing on the floor of the water body).
        LAYER_Water = '?', -- If true, unit will leave factory partly above the water floating.
    },
    BuildRestriction = 'string', -- Special build restrictions (mass deposit, thermal vent, etc).
    CatchUpAcc = '10', -- Acceleration to allow unit to catch up to the target when it starts to drift.
    DragCoefficient = '?', -- (?)
    Elevation = 'n', -- Prefferred height above (-below) land or water surface.
    FlattenSkirt = 'true/false', -- If true, terrain under building's skirt will be flattened.
    FuelRechargeRate = 'n', -- Unit fuels up at this rate per second.
    FuelUseTime = 'n', -- Unit has fuel for this number of seconds.
    LayerChangeOffsetHeight = 'n', -- An offset to the layer change height used during the transition between seabed/water and land.
    LayerTransitionDuration = 'n', -- Transition time in seconds when going from water/land and land/water.
    MaxAcceleration = 'n', -- Maximum acceleration for the unit.
    MaxBrake = 'n', -- Maximum braking acceleration for the unit.
    MaxGroundVariation = 'n', -- Maximum elevation difference across skirt for build site.
    MaxSpeed = 'n', -- Maximum speed for the unit.
    MaxSpeedReverse = 'n', -- Maximum speed for the unit in reverse.
    MaxSteerForce = 'n', -- Maximum steer force magnitude that can be applied to acceleration.
    MeshExtentsX = '?', -- (?)
    MeshExtentsY = '?', -- (?)
    MeshExtentsZ = '?', -- (?)
    MinSpeedPercent = '?', -- (?)
    MotionType = 'string', -- Method of locomotion.
    OccupyRects = 'string', -- Set up the occupy rectangles of the unit that will override the footprint.
    RaisedPlatforms = 'string', -- Raised platform definition for ground units to move on.
    RollDamping = 'n', -- How much damping there is against rolling motion (1 = no motion at all).
    RollStability = 'n', -- How stable the unit is against rolling (0 to 1).
    RollOffPoints = '?', -- (?)
    RotateBodyWhileMoving = 'true/false', -- Ability to rotate body to aim weapon slaved to body while in still in motion.
    RotateOnSpot = 'true/false', -- This unit can tries to rotate on the spot.
    SkirtOffsetX = 'n', -- Offset of left edge of skirt from left edge of footprint. (Should be -- = 0)
    SkirtOffsetZ = 'n', -- Offset of top edge of skirt from left edge of footprint. (Should be -- = 0)
    SkirtSizeX = 'n', -- Unit construction pad Size X for building.
    SkirtSizeZ = 'n', -- Unit construction pad Size Z for building.
    StandUpright = 'true/false', -- Stands upright regardless of terrain,
    TurnFacingRate = 'n', -- Turn facing damping for the unit, usually used for hover units only.
    TurnRadius = 'n', -- Turn radius for the unit, in wolrd units.
    TurnRate = 'n', -- Turn radius for the unit, in degrees per second.
    WobbleFactor = 'n', -- How much wobbling for the unit while hovering.
    WobbleSpeed = 'n', -- How fast is the wobble, The faster the less stable looking.
},
```

## SelectionCenterOffsetX
```lua
SelectionCenterOffsetX = 'n', -- X center offset of selection box
```
## SelectionCenterOffsetY
```lua
SelectionCenterOffsetY = 'n', -- Y center offset of selection box
```
## SelectionCenterOffsetZ
```lua
SelectionCenterOffsetZ = 'n', -- Z center offset of selection box
```
## SelectionSizeX
SelectionSizeX and SelectionSizeZ define the frame around the selected unit.
```lua
SelectionSizeX = 'n', -- X Size of selectien box.
```
## SelectionSizeY
SelectionSizeY adjusts the height of the selection box.
```lua
SelectionSizeY = 'n', -- Y Size of selectien box.
```
## SelectionSizeZ
SelectionSizeX and SelectionSizeZ define the frame around the selected unit.
```lua
SelectionSizeZ = 'n', -- Z Size of selectien box.
```
## SelectionThickness
Use this to modify the thickness of the rendered selection indicator for the unit.
```lua
SelectionThickness = 'n',
```
## SelectionYOffset
```lua
SelectionYOffset = 'n', -- How far to reduce top of collision box for selection (default 0.5)
```
## SizeX
SizeX, SizeY and SizeZ define the collision box for the unit. The collision box is used to detect hits on the unit. If you change the model size the collision box should be adapted.
```lua
SizeX = 'n',
```
## SizeY
SizeX, SizeY and SizeZ define the collision box for the unit. The collision box is used to detect hits on the unit. If you change the model size the collision box should be adapted.
```lua
SizeY = 'n',
```
## SizeZ
SizeX, SizeY and SizeZ define the collision box for the unit. The collision box is used to detect hits on the unit. If you change the model size the collision box should be adapted.
```lua
SizeZ = 'n',
```

## StrategicIconName
Name of the strategic icon to use for this unit (seen when zoomed out).

```lua
StrategicIconName = 'string',
```

The structure of an icon is `icon_xxxY_zzz`

`xxx` stands for the unit type which are:

`bomber` - Bomber (Air Unit) <br>
`bot` - Bot/Mech (Land Unit) <br>
`commander` - ACU/SCU (Land Unit) <br>
`experimental` - Experimental Unit <br>
`factory` - Factory (Land Unit) <br>
`fighter` - Fighter/Interceptor (Air Unit) <br>
`gunship` - Gunship/Air Transport (Air Unit) <br>
`land` - Vehicle/Tank (Land Unit) <br>
`ship` - Ships (Sea Unit) <br>
`structure` - Structure (Land Unit) <br>
`sub` - Submarine (Sea Unit)

`Y` stands for the `tech level (1 - 3)`. If no tech level is given a strategic icon without the units tech level is shown.

`zzz` stands for the function of the unit which are:

`air` - Air Factory / Aircraft Staging<br>
`antiair` - Anti-Air Weapons<br>
`antimissile` - Missile Defense<br>
`antinavy` - Torpedo Weapons<br>
`artillery` - Artillery Weapons<br>
`counterintel` - Stealth/Cloaking/Radar Jamming<br>
`directfire` - Direct Fire Weapons<br>
`energy` - Energy producing/storaging<br>
`engineer` - Engineering Suit<br>
`generic` - Undefined unit type<br>
`intel` - Radar/Sonar<br>
`land` - Land Factory<br>
`mass` - Mass producing/storaging<br>
`missile` - Missile Weapons<br>
`naval` - Naval Factory<br>
`shield` - Shielding<br>
`transport` - Transporting<br>
`wall` - Wall

A complete list of avaible icons included in the game:

- icon_bomber_antinavy
- icon_bomber_directfire
- icon_bomber_generic
- icon_bomber1_antinavy
- icon_bomber1_directfire
- icon_bomber1_generic
- icon_bomber2_antinavy
- icon_bomber2_directfire
- icon_bomber2_generic
- icon_bomber3_antinavy
- icon_bomber3_directfire
- icon_bomber3_generic
- icon_bot_directfire
- icon_bot_generic
- icon_bot1_directfire
- icon_bot1_generic
- icon_bot2_directfire
- icon_bot2_generic
- icon_bot3_directfire
- icon_bot3_generic
- icon_commander_generic
- icon_experimental_generic
- icon_factory_air
- icon_factory_generic
- icon_factory_land
- icon_factory_naval
- icon_factory1_air
- icon_factory1_generic
- icon_factory1_land
- icon_factory1_naval
- icon_factory2_air
- icon_factory2_generic
- icon_factory2_land
- icon_factory2_naval
- icon_factory3_air
- icon_factory3_generic
- icon_factory3_land
- icon_factory3_naval
- icon_fighter_antiair
- icon_fighter_directfire
- icon_fighter_generic
- icon_fighter_intel
- icon_fighter1_antiair
- icon_fighter1_directfire
- icon_fighter1_generic
- icon_fighter1_intel
- icon_fighter2_antiair
- icon_fighter2_directfire
- icon_fighter2_generic
- icon_fighter2_intel
- icon_fighter3_antiair
- icon_fighter3_directfire
- icon_fighter3_generic
- icon_fighter3_intel
- icon_gunship_directfire
- icon_gunship_generic
- icon_gunship_transport
- icon_gunship1_directfire
- icon_gunship1_generic
- icon_gunship1_transport
- icon_gunship2_directfire
- icon_gunship2_generic
- icon_gunship2_transport
- icon_gunship3_directfire
- icon_gunship3_generic
- icon_gunship3_transport
- icon_land_antiair
- icon_land_artillery
- icon_land_counterintel
- icon_land_directfire
- icon_land_engineer
- icon_land_generic
- icon_land_intel
- icon_land_missile
- icon_land_shield
- icon_land1_antiair
- icon_land1_artillery
- icon_land1_counterintel
- icon_land1_directfire
- icon_land1_engineer
- icon_land1_generic
- icon_land1_intel
- icon_land1_missile
- icon_land1_shield
- icon_land2_antiair
- icon_land2_artillery
- icon_land2_counterintel
- icon_land2_directfire
- icon_land2_engineer
- icon_land2_generic
- icon_land2_intel
- icon_land2_missile
- icon_land2_shield
- icon_land3_antiair
- icon_land3_artillery
- icon_land3_counterintel
- icon_land3_directfire
- icon_land3_engineer
- icon_land3_generic
- icon_land3_intel
- icon_land3_missile
- icon_land3_shield
- icon_ship_air
- icon_ship_antiair
- icon_ship_antinavy
- icon_ship_directfire
- icon_ship_generic
- icon_ship_intel
- icon_ship1_air
- icon_ship1_antiair
- icon_ship1_antinavy
- icon_ship1_directfire
- icon_ship1_generic
- icon_ship1_intel
- icon_ship2_air
- icon_ship2_antiair
- icon_ship2_antinavy
- icon_ship2_directfire
- icon_ship2_generic
- icon_ship2_intel
- icon_ship3_air
- icon_ship3_antiair
- icon_ship3_antinavy
- icon_ship3_directfire
- icon_ship3_generic
- icon_ship3_intel
- icon_structure_air
- icon_structure_antiair
- icon_structure_antimissile
- icon_structure_antinavy
- icon_structure_artillery
- icon_structure_counterintel
- icon_structure_directfire
- icon_structure_energy
- icon_structure_generic
- icon_structure_intel
- icon_structure_land
- icon_structure_mass
- icon_structure_missile
- icon_structure_naval
- icon_structure_shield
- icon_structure_transport
- icon_structure_wall
- icon_structure1_air
- icon_structure1_antiair
- icon_structure1_antimissile
- icon_structure1_antinavy
- icon_structure1_artillery
- icon_structure1_counterintel
- icon_structure1_directfire
- icon_structure1_energy
- icon_structure1_generic
- icon_structure1_intel
- icon_structure1_land
- icon_structure1_mass
- icon_structure1_missile
- icon_structure1_naval
- icon_structure1_shield
- icon_structure1_transport
- icon_structure2_air
- icon_structure2_antiair
- icon_structure2_antimissile
- icon_structure2_antinavy
- icon_structure2_artillery
- icon_structure2_counterintel
- icon_structure2_directfire
- icon_structure2_energy
- icon_structure2_generic
- icon_structure2_intel
- icon_structure2_land
- icon_structure2_mass
- icon_structure2_missile
- icon_structure2_naval
- icon_structure2_shield
- icon_structure2_transport
- icon_structure3_air
- icon_structure3_antiair
- icon_structure3_antimissile
- icon_structure3_antinavy
- icon_structure3_artillery
- icon_structure3_counterintel
- icon_structure3_directfire
- icon_structure3_energy
- icon_structure3_generic
- icon_structure3_intel
- icon_structure3_land
- icon_structure3_mass
- icon_structure3_missile
- icon_structure3_naval
- icon_structure3_shield
- icon_structure3_transport
- icon_sub_antinavy
- icon_sub_directfire
- icon_sub_generic
- icon_sub_missile
- icon_sub1_antinavy
- icon_sub1_directfire
- icon_sub1_generic
- icon_sub1_missile
- icon_sub2_antinavy
- icon_sub2_directfire
- icon_sub2_generic
- icon_sub2_missile
- icon_sub3_antinavy
- icon_sub3_directfire
- icon_sub3_generic
- icon_sub3_missile

## StrategicIconSortPriority

This is set to an integer that describes the unit's position in the list of selected units when different unit types are selected. 0 renders on top, 255 on bottom.

```lua
StrategicIconSortPriority = 'n',
```

## Transport

Transport related information for the unit.

```lua
Transport = {
    AirClass = 'true/false', -- These define that the unit can only land on air staging platforms.
    CanFireFromTransport = 'true/false', -- Define if the unit can fire out of a transport.
    Class2AttachSize = 'integer', -- Number of class 1 attach points this affects.
    Class3AttachSize = 'integer', -- Number of class 1 attach points this affects.
    Class4AttachSize = 'integer', -- Number of class 1 attach points this affects.
    ClassGenericUpTo = 'integer', -- Generic slots up to the specified class.
    ClassSAttachSize = 'integer', -- Number of class 1 attach points this affects.
    RepairRate = 'n', -- Repairs units attached to me at this % of max health per second.
    StorageSlots = 'integer', -- How many internal storage slots avaible for the transport on top of attach points.
    TransportClass = 'integer', -- Type of attach points required on transports.
},
```
## UseOOBTestZoom
Use OOB hit test for this unit when camera is below this zoom level. Usually we use screen space to do unit selection, but occasionally we want to use the unit's oriented bounding box (OBB) instead. So we have UseOOBTestZoom.
```lua
UseOOBTestZoom = 'n',
```

## Veteran
Veteran define how many kills for each veteran level are required.
```lua
Veteran = {
    Level1 = 'integer', -- Define how much kills are required for reaching veteran level 1
    Level2 = 'integer', -- Define how much kills are required for reaching veteran level 2
    Level3 = 'integer', -- Define how much kills are required for reaching veteran level 3
    Level4 = 'integer', -- Define how much kills are required for reaching veteran level 4
    Level5 = 'integer', -- Define how much kills are required for reaching veteran level 5
},
```
## Weapon

Weapon define which weapons are attached to a unit and how they are configured. Nearly everything that is needed to make a weapon workable is set under this category (blueprint's category).

Note: The following is just basic information. For more details see [Blueprint/Weapon](/Blueprints/Weapon)

```lua
Weapon = {
    Audio = '?', -- Informations about the audio files used by the weapon
    AutoInitiateAttackCommand = '?', -- If the unit has no issued commands and has a weapon that has AutoInitiateAttackCommand set, then if it finds a suitable target it will issue an attack command to go after the target.
    BallisticArc = 'string', -- Ballistic arcs that should be used on the projectile. RULEUBA_None, RULEUBA_LowArc or RULEUBA_HighArc
    BeamCollisionDelay = 'n', -- Every X +.1 seconds, this beam will collide and do damage - use 0 so that beams will cause their damage every .1 second
    BeamLifetime = 'n', -- The amount of time the beam exists
    Buffs = '?', -- Information about the bonuses added to the unit's weapon when it reaches a specific veteran level.
    CameraShakeDuration = 'n', -- time to maintain the camera shake
    CameraShakeMax = 'n', -- Max size of the camera shake
    CameraShakeMin = 'n', -- Minimum size of the camera shake
    CameraShakeRadius = 'n', -- How far from the unit should the camera shake
    CollideFriendly = 'true/false' -- Should the unit collide against friendly meshes
    ContinuousBeam = 'true/false' -- Beam fires without stopping - overrides RateOfFire
    Damage = 'n', -- Damage value
    DamageFriendly = 'true/false', -- Should we damage friendly units
    DamageRadius = 'n', -- Blast Radius
    DamageType = 'string', -- The type of damage the unit will do. 'Normal' will affect all units
    DisplayName = 'string', -- Just for debugging. "dbg weapons" on the console shows the weapon names. Also some errors that we detect in script code will print the name of the weapon to help track down the issue.
    DoTPulses = 'n', -- The number of times the damage will be dealt
    DoTTime = 'n', -- Length of Time the Damage over Time (DoT) will last in seconds.
    DummyWeapon = '?', -- This instructs the engine not to create a C++ weapon object that is usually linked with the script object. This is for purely script driven weapons (like death weapons). 
    EnergyDrainPerSecond = 'n', -- How much energy this weapon will drain per second
    EnergyRequired = 'n', -- How much energy is required to fire this weapon
    FireTargetLayerCapsTable = {} = '?', -- FireTargetLayerCapsTable allows you to pick which layers you can target in relation to the layer that you are currently at
    FiringRandomness = 'n', -- How much random inaccuracy should we be from the target
    FiringTolerance = 'n', -- How much misalignment can the barrel be before starting to fire. Used when you are trying to target ammo that does not require lots of accuracy due to the size of their damage radius or because the ammo does automatic targetting
    HeadingArcCenter = '?', -- Controls what the weapon is allowed to target in reference to the heading of the unit
    HeadingArcRange = '?', -- Controls what the weapon is allowed to target in reference to the arc center, this is degrees on either side
    HideMuzzle = 'true/false', -- Indicates that the muzzle bones will be hidden when fired and turned back on before muzzle recharge and during idle. Useful for weapons that show the projectile in the art then fire it off. (Mobile missile launchers) **this must be put inside the Rack {} but outside the muzzlebones {}
    Label = 'string', -- Label is linking the blueprints (unitid_unit.bp) weapon information with the script (unitid_script.lua) weapon information. For example: blueprint: Weapon { Label = 'FrontTurret01', } script: Weapons = { FrontTurret01 = Class(TDFGaussCannonWeapon) {} }. If the Label doeas not match the weapon will not be workable.
    MaxRadius = 'n', -- How far does the target need to be before we start firing
MetaImpactAmount = '?', -- Deprecated attribute (Changing these will do nothing to the weapon)
MetaImpactRadius = '?', -- Deprecated attribute (Changing these will do nothing to the weapon)
MuzzleBones = '?', -- { List of muzzle bones }
MuzzleChargeDelay = 'n', -- The time that the muzzle will wait between playing the FxMuzzleFlash table and the creation of the projectile. Note: This will delay the firing of the projectile. So if you set the rate of fire to fire quickly, this will throttle it
MuzzleSalvoDelay = 'n', -- Time in between muzzles firing. Setting to 0 = all muzzle fire together
MuzzleSalvoSize = 'n', -- Number of times the muzzle will fire during a rack firing
MuzzleVelocity = 'n', -- Speed in which the projectile comes out of the muzzle. This speed is used in the ballistics calculations. If you weapon doesn't fire at its max radius, this may be too low
MuzzleVelocityReduceDistance = 'n', -- MuzzleVelocityReduceDistance was put there so weapons that have a high muzzle velocity because they have a huge range, like an artillery piece, wouldn't point right at something that's close, it'll slow down it's shot and still have a nice arc to it
NeedPrep = 'true/false', -- If NeedProp is true then whenever the unit aquires a new target and is ready to attack it it will first run the OnGotTarget script on the weapon.
ProjectileId = 'string', -- Blueprint of the projectile to fire
ProjectileLifetime = 'n', -- How long the projectile lives
ProjectilesPerOnFire = 'n', -- Deprecated attribute (Changing these will do nothing to the weapon)
RackBones = '?', -- Bone Used for Rack Recoil
RackFireTogether = 'true/false', -- Do all racks fire simultaneously?
RackRecoilDistance = 'n', -- Distance racks will recoil, Z axis, local coords
RackReloadTimeout = 'n', -- Seconds before the weapon will reload when it didn't go through all its racks
RackSalvoChargeTime = 'n', -- Time before the racks start firing
RackSalvoFiresAfterCharge = 'true/false', -- Does the racks immediately fire when charge is done or wait until next OnFire event?
RackSalvoReloadTime = 'n', -- Time the racks will reload before starting its next charge/salve cycle
RackSalvoSize = 'n', -- Number of times the racks will fire before its reload period
RackSlavedToTurret = 'true/false', -- All rack bones are slaved to the turret pitch bone?
RateOfFire = 'n', -- Rack firings per second. You can use decimals for fire rates that are longer than a second
TargetCheckInterval = 'n', -- Interval of time between looking for a target
TargetPriorities = '?', -- Table of category strings that define the targetting order of this weapon.
TargetRestrictDisallow = '?', -- The categories that we will not allow to target
TargetRestrictOnlyAllow = '?', -- Exclusive categories that we will allow to target
TelescopeBone = 'string', -- Bone used for telescoping barrel recoil **this must be put inside the Rack {} but outside the muzzlebones {}
TelescopeRecoilDistance = 'n', -- Distance the telescoping part of the barrel will recoil
TrackingRadius = 'n', -- The radius that the weapon start tracking the target. This does not mean that the weapon will fire. The weapon will only fire when a target enters the maxradius. This is a multi of the weapons MaxRadius.
TurretBoneDualMuzzle = 'string', -- The second muzzle bone for a turret, used for arms on bots as weapons
TurretBoneDualPitch = 'string', -- The second pitch bone for a turret, used for arms on bots as weapons
TurretBoneMuzzle = 'string', -- The bone used as the muzzle bone for turrets. This is used for aiming as where the projectile would come out
TurretBonePitch = 'string', -- Bone name that will determine the pitch rotation (rotation along the X axis)
TurretBoneYaw = 'string', -- Bone name that will determine the yaw rotation (rotation along the Y axis)
TurretDualManipulators = 'true/false', -- Do we need two manipulators? Used for bots with arms
Turreted = 'true/false', -- Does this have a turret?
TurretPitch = 'n', -- The center angle for determining pitch, based off the rest pose of the art
TurretPitchRange = 'n', -- The angle +/- off the pitch that is a valid angle to turn to
TurretPitchSpeed = 'n', -- The speed at which the turret can pitch
TurretYaw = 'n', -- The center angle for determining yaw, based off the rest pose of the art
TurretYawRange = 'n', -- The angle +/- off the yaw that is a valid angle to turn to
TurretYawSpeed = 'n', -- The speed at which the turret can yaw
WeaponCategory = 'string', -- Deprecated attribute (Changing these will do nothing to the weapon)
WeaponRepackTimeout = 'n', -- Amount of time after the unit has lost its target that it will wait before repacking the weapon
WeaponUnpackAnimation = 'string', -- Animation name of the unpack animation
WeaponUnpackAnimationRate = 'n', -- How fast the unpack animation runs
WeaponUnpackLocksMotion = 'true/false', -- Halts all unit motion while this weapon is active and locks out all other weapons not flagged as NotExclusive = true. This is useful when a unit must the stationary to fire such as a moble artillery unit or when a unit is required to be stationary during an unpack / repack sequence.
WeaponUnpackTimeout = 'n', -- Time the unit will take to unpack the weapon
WeaponUnpacks = 'true/false', -- Weapon must unpack before ready to fire

Note: New Commands

AimsStraightOnDisable = 'true/false', -- This weapon will aim straight ahead when disabled.
AlwaysRecheckTarget = 'true/false', -- Always recheck for better target regardless of whether you already have one or not.
AttackGroundTries = 'n', -- This determines the number of shots at a ground target before moving on to the next target.
CountedProjectile = 'true/false', -- This projectile needs to be built and stored before the weapon can fire.
EffectiveRadius = 'n', -- The effective range that this weapon really is.
IgnoresAlly = 'true/false', -- This determines whether the weapon affect ally units or not.
LeadTarget = 'true/false', -- True if weapon should lead its target when aiming.
ManualFire = 'true/false', -- Never fires automaticly.
MaxHeightDiff = '?', -- The maximum height diff range for the weapon. Keep in mind weapons are now cylinder in nature.
MaxProjectileStorage = 'n', -- This weapon can only hold this many counted projectiles.
MinRadius = 'n', -- The minimum range we must be to fire at our target.
MuzzleVelocityRandom = 'n', -- Random variation for muzzle velocity (gaussian).
NukeWeapon = 'true/false', -- Nuke weapon flag.
OverchargeWeapon = 'true/false', -- Overcharge weapon flag.
RequiresEnergy = 'n', -- Weapon requires this much avaible energy to fire.
RequiresMass = 'n', -- Weapon requires this much avaible mass to fire.
SlavedToBody = 'true/false', -- Flag to specify if the weapon is slaved to the unit body, thus requiring unit to face target to fire.
TargetType = 'string', -- The type of entity this unit can target. (RULEWTT_Unit)
UIMaxRangeVisualId = '?', -- Allow the UI to know what kind of maximum range indicator to draw for this weapon.
UIMinRangeVisualId = '?', -- Allow the UI to know what kind of minimum range indicator to draw for this weapon.
NoPause = 'true/false', -- (?)
FiringRandomnessWhileMoving = 'n', -- the firing randomness that this weapon has while the pparent unit is moving
},
```

## Wreckage
Here are wreckage informations defined.
```lua
Wreckage = {
    Blueprint = 'string', -- ?
    EnergyMult = 'n', -- the amount of energy you get when reclaiming expressed as a multiplier of the energy cost when it was alive>
    HealthMult = 'n', -- the amount of health this wreck has so it can take damage from weapons that do area damage>
    MassMult = 'n', -- the amount of mass you get when reclaiming expressed as a multiplier of the mass cost when it was alive>
    ReclaimTimeMultiplier = 'n', -- the time it takes to reclaim this wreck expressed as a multiplier of the build time>
    WreckageLayers = { -- Subcategories are:
        Air = 'true/false', -- ?
        Land = 'true/false', -- ?
        Seabed = 'true/false', -- ?
        Sub = 'true/false', -- ?
        Water = 'true/false', -- ?
    },
},
```
## Notes
`'n'` stands for a number, positive or negative. Quote marks before and after the number are not needed.<br>
`'integer'` stands for a integer. Quote marks before and after the integer are not needed.<br>
`'true/false'` is a true or false argument. Quote marks before and after the argument are not needed.<br>
`'string'` is a word or a combination of words. Quote marks before and after a string are required.<br>
You can use -- to add comments in the blueprints. This could be useful when changing things temporarily.
