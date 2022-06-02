---
title: Blueprints
description: A blueprint is a file within Supreme Commander that describes a unit
published: true
date: 2022-06-02T16:40:29.156Z
tags: 
editor: markdown
dateCreated: 2022-06-02T16:40:29.156Z
---

# Blueprint
A blueprint is a file within Supreme Commander that describes a unit. These are .bp files inside gamedata.scd. Within that file the blueprints are found in a subdirectory of gamedata\units\. For instance, `gamedata\units\UAA0101\UAA0101_unit.bp` is the blueprint for the Aeon T1 Air Scout.

## Blueprint format
The following is documentation of the contents of a blueprint file. It is valid Lua code. The entire file is a call to UnitBlueprint with a large table. Below is an incomplete list of the fields and their purposes.

### Adjacency
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

### AI
AI information for the unit.

```lua
AI = {
	AttackAngle = 'n', --Under what angle the unit attacks its target after getting an attack order
	AutoSurfaceToAttack = 'true/false', --Automatically surface to attack ground targets.
	BeaconName = 'string', --This is the beacon that this unit will create under some circumstances.
	GuardFormationName = 'string', --The formation name used for guarding this unit. Known formations: 'GuardFormation'
	GuardRadius = 'n', --How far a unit on patrol will look off it's patrol path to go attack.
	GuardReturnRadius = 'n', --Maximum range from the guarded unit before initiating return.
	GuardScanRadius = 'n', --Guard range for the unit.
	InitialAutoMode = 'true/false', --Initial auto mode behaviour for the unit.
	NeedUnpack = 'true/false', --Unit should unpack before firing weapon.
	RefuelingMultiplier = 'n', --This muliplier is applied when a staging platform is refueling an air unit.
	RefuelingRepairAmount = 'n', --This amount of repair per second offered to refueling air units.
	TargetBones = 'string', --Some target bones setup for other units to aim at instead of the default center pos.
},

```

### Air

Air control information for the unit.

```lua
Air = {
	AutoLandTime = 'n', --Timer to automatically initiate landing on ground if idle.
	BankFactor = 'n', --How much aircraft banks in turns; negative to lean out.
	BankForward = 'true/false', --True if aircraft banks forward/back as well as sideways.
	BombDropThreshold = 'n', --Distance from the target unit will start firing bombs.
	BreakOffDistance = 'n', --Distance to break off before turning around for another attack run.
	BreakOffTrigger = 'n', --Distance to target to trigger the breaking off attack.
	CanFly = 'true/false', --Is the unit capable of flight?
	CirclingDirChange = 'true/false', --Whether unit should ever change flight direction while circling.
	CirclingDirChangeFrequencySec = 'n', --How often will it change direction when it's attack motion is back and forth, like a gunship.
	CirclingElevationChangeRatio = 'n', --Elevation change ratio of unit when circling.
	CirclingFlightChangeFrequency = 'n', --Frequency of flight pattern change for unit.
	CirclingRadiusChangeMaxRatio = 'n', --Max circling radius ratio for unit.
	CirclingRadiusChangeMinRatio = 'n', --Min circling radius ratio for unit.
	CirclingRadiusVsAirMult = 'n', --Multiplier to the circling radius when targeting another air unit.
	CirclingTurnMult = 'n', --Adjust turning ability when in circling mode.
	CombatTurnSpeed = 'n', --Maximum combat turn speed of the unit for special maneuvers.
	EngageDistance = 'n', --Distance to being engaging enemy target in attack task.
	FlyInWater = 'true/false', --Can this unit fly under water?
	HoverOverAttack = 'true/false', --Whether unit should hover over the target directly to attack. (Used for cases like the CZAR)
	KLift = 'n', --Controller proportional parameter for vertical motion.
	KLiftDamping = 'n', --Controller damping parameter for vertical motion
	KMove = 'n', --Controller proportional parameter for horizontal motion.
	KMoveDamping = 'n', --Controller damping parameter for horizontal motion.
	KRoll = 'n', --Controller proportional parameter for roll changes.
	KRollDamping = 'n', --Controller damping parameter for roll changes.
	KTurn = 'n', --Controller proportional parameter for heading changes.
	KTurnDamping = 'n', --Controller damping parameter for heading changes.
	LiftFactor = 'n', --How much altitude the unit can gain/loose per second.
	MaxAirspeed = 'n', --Maximum airspeed.
	MaxEngineThrust = 'n', <Max thrust for the engine. Directly influences speed and acceleration.
	MaxEngineTorque = 'n', <(?)(Found in various aircraft blueprints)
	MinAirspeed = 'n', <Minimum combat airspeed.
	NeedToComputeBombDrop = 'true/false', <Doesn't drop bombs until path is computed?
	PredictAheadForBombDrop = 'n', <??Time in seconds or distance to target??
	RandomBreakOffDistanceMult = 'n', <Random multiplier applied to break off distance for winged aircrafts.
	RandomMaxChangeCombatStateTime = 'n', <Random max time to switch combat state in seconds for winged aircrafts.
	RandomMinChangeCombatStateTime = 'n', <Random min time to switch combat state in seconds for winged aircrafts.
	StartTurnDistance = 'n', <Distance from target at which to start turning to align with it.
	TightTurnMultiplier = 'n', <Additional turning multiplier ability during a tight turn maneuver.
	TransportHoverHeight = 'n', <This transport will stay at this height when picking up and dropping off units.
	TurnSpeed = 'n', <Regular turn speed of the unit.
	Winged = 'true/false', <Does the unit use wings for forward flight?
},
```
