---
title: LUADOC 1.5.3599
description: 
published: true
date: 2021-09-09T15:06:00.988Z
tags: 
editor: markdown
dateCreated: 2021-09-09T15:04:15.075Z
---

# LUADOC 1.5.3599
## Sim
## Sim{.tabset}
### `Sim.<global>`
- AddBuildRestriction
INFO: AddBuildRestriction(army,category) - Add a category to the restricted list
- ArmyGetHandicap
INFO: army
- ArmyInitializePrebuiltUnits
INFO: army
- ArmyIsCivilian
INFO: ArmyIsCivilian(army)
- ArmyIsOutOfGame
INFO: ArmyIsOutOfGame(army) -- return true iff the indicated army has been defeated.
- AttachBeamEntityToEntity
INFO: AttachBeamEntityToEntity(self, bone, other, bone, army, blueprint)
- AttachBeamToEntity
INFO: AttachBeamToEntity(emitter, entity, tobone, army )
- AudioSetLanguage
INFO: AudioSetLanguage(name)
- ChangeUnitArmy
INFO: ChangeUnitArmy(unit,armyIndex) Change a unit's army
- CheatsEnabled
INFO: Return true iff cheats are enabled
Logs the cheat attempt no matter what.
- CoordinateAttacks
INFO: CoordinateAttacks
- CreateAimController
INFO: CreateAimController(weapon, label, turretBone, [barrelBone], [muzzleBone])
- CreateAnimator
INFO: CreateAnimator(unit) -- create a manipulator for playing animations
- CreateAttachedBeam
INFO: CreateAttachedBeam(entity, bone, army, length, thickness, texture_filename)
- CreateAttachedEmitter
INFO: CreateAttachedEmitter(entity, bone, army, emitter_blueprint)
- CreateBeamEmitter
INFO: emitter = CreateBeamEmitter(blueprint,army)
- CreateBeamEmitterOnEntity
INFO: emitter = CreateBeamEmitterOnEntity(entity, tobone, army, blueprint )
- CreateBeamEntityToEntity
INFO: CreateBeamEntityToEntity(entity, bone, other, bone, army, blueprint) 
- CreateBeamToEntityBone
INFO: CreateBeamToEntityBone(entity, bone, other, bone, army, thickness, texture_filename)
- CreateBuilderArmController
INFO: CreateBuilderArmController(unit,turretBone, [barrelBone], [aimBone])
- CreateCollisionDetector
INFO: CreateCollisionDetector(unit) -- create a collision detection manipulator
- CreateDecal
INFO: handle = CreateDecal(position, heading, textureName1, textureName2, type, sizeX, sizeZ, lodParam, duration, army, fidelity)
- CreateEconomyEvent
INFO: event = CreateEconomyEvent(unit, energy, mass, timeInSeconds)
- CreateEmitterAtBone
INFO: CreateEmitterAtBone(entity, bone, army, emitter_blueprint)
- CreateEmitterAtEntity
INFO: CreateEmitterAtEntity(entity,army,emitter_bp_name)
- CreateEmitterOnEntity
INFO: CreateEmitterOnEntity(entity,army,emitter_bp_name)
- CreateFootPlantController
INFO: CreateFootPlantController(unit, footBone, kneeBone, hipBone, [straightLegs], [maxFootFall])
- CreateInitialArmyUnit
INFO: CreateInitialArmyUnit(armyName, initialUnitName
- CreateLightParticle
INFO: CreateLightParticle(entity, bone, army, size, lifetime, textureName, rampName)
- CreateLightParticleIntel
INFO: CreateLightParticle(entity, bone, army, size, lifetime, textureName, rampName)
- CreateProp
INFO: CreateProp(location,prop_blueprint_id)
- CreatePropHPR
INFO: blueprint, x, y, z, heading, pitch, roll
CreateResourceDeposit
INFO: type, x, y, z, size
CreateRotator
INFO: manip = CreateRotator(unit, bone, axis, [goal], [speed], [accel], [goalspeed])
CreateSlaver
INFO: manip = CreateSlaver(unit, dest_bone, src_bone)
Create a manipulator which copies the motion of src_bone onto dst_bone.Priority matters! Only manipulators which come before the slave manipulator will be copied.
CreateSlider
INFO: CreateSlider(unit, bone, [goal_x, goal_y, goal_z, [speed, [world_space]]])
CreateSplat
INFO: CreateSplat(position, heading, textureName, sizeX, sizeZ, lodParam, duration, army, fidelity)
CreateSplatOnBone
INFO: CreateSplatOnBone(boneName, offset, textureName, sizeX, sizeZ, lodParam, duration, army)
Add a splat to the game at an entity bone position and heading.
CreateStorageManip
INFO: CreateStorageManip(unit, bone, resouceName, minX, minY, minZ, maxX, maxY, maxZ)
CreateThrustController
INFO: CreateThrustController(unit, label, thrustBone)
CreateTrail
INFO: CreateTrail(entity, bone, army, trail_blueprint)
CreateUnit
INFO: blueprint, army, tx, ty, tz, qx, qy, qz, qw, [layer]
CreateUnit2
INFO: blueprint, army, layer, x, z, heading
CreateUnitHPR
INFO: blueprint, army, x, y, z, pitch, yaw, roll
Damage
INFO: Damage(instigator, target, amount, damageType)
DamageArea
INFO: DamageArea(instigator,location,radius,amount,damageType,damageFriendly,[damageSelf])
DamageRing
INFO: DamageRing(instigator,location,minRadius,maxRadius,amount,damageType,damageFriendly,[damageSelf])
DebugGetSelection
INFO: Get DEBUG info for UI selection
DrawCircle
INFO: Draw a 3d circle at a with size s and color c
DrawLine
INFO: Draw a 3d line from a to b with color c
DrawLinePop
INFO: Draw a 3d line from a to b with color c with a circle at the end of the target line
EconomyEventIsDone
INFO: bool = EconomyEventIsDone(event)
EndGame
INFO: Signal the end of the game.:Acts like a permanent pause.
EntityCategoryContains
INFO: See if a unit category contains this unit
EntityCategoryCount
INFO: Count how many units fit the specified category
EntityCategoryCountAroundPosition
INFO: Count how many units fit the specified category around a position
EntityCategoryFilterDown
INFO: Filter a list of units to only those found in the category
FlattenMapRect
INFO: FlattenRect(x, z, sizex, sizez, elevation)
FlushIntelInRect
INFO: FlushIntelInRect( minX, minZ, maxX, maxZ )
GenerateArmyStart
INFO: army
GenerateRandomOrientation
INFO: rotation = GenerateRandomOrientation()
GetArmyBrain
INFO: army
GetArmyUnitCap
INFO: army
GetArmyUnitCostTotal
INFO: army
GetBlueprint
INFO: blueprint = GetBlueprint(entity)
GetCurrentCommandSource
INFO: Return the (1 based) index of the current command source.
GetEntitiesInRect
INFO: Return the enitities inside the given rectangle
GetEntityById
INFO: Get entity by entity id
GetFocusArmy
INFO: GetFocusArmy()
GetGameTick
INFO: Get the current game time in ticks. The game time is the simulation time, that stops when the game is paused.
GetGameTimeSeconds
INFO: Get the current game time in seconds. The game time is the simulation time, that stops when the game is paused.
GetMapSize
INFO: sizeX, sizeZ = GetMapSize()
GetReclaimablesInRect
INFO: Return the reclamable things inside the given rectangle
GetSurfaceHeight
INFO: type = GetSurfaceHeight(x,z)
GetSystemTimeSecondsOnlyForProfileUse
INFO: float GetSystemTimeSecondsOnlyForProfileUse() - returns System time in seconds
GetTerrainHeight
INFO: type = GetTerrainHeight(x,z)
GetTerrainType
INFO: type = GetTerrainType(x,z)
GetTerrainTypeOffset
INFO: type = GetTerrainTypeOffset(x,z)
GetUnitBlueprintByName
INFO: blueprint = GetUnitBlueprintByName(bpName)
GetUnitById
INFO: Get entity by entity id
GetUnitsInRect
INFO: Return the units inside the given rectangle
HasLocalizedVO
INFO: HasLocalizedVO(language)
InitializeArmyAI
INFO: army
IsAlly
INFO: IsAlly(army1,army2)
IsBlip
INFO: Blip = IsBlip(entity)
IsCollisionBeam
INFO: CollisionBeam = IsCollisionBeam(entity)
IsCommandDone
INFO: IsCommandDone
IsEnemy
INFO: IsEnemy(army1,army2)
IsEntity
INFO: bool = IsEntity(object)
IsGameOver
INFO: Return true if the game is over (i.e. EndGame() has been called).
IsNeutral
INFO: IsNeutral(army1,army2)
IsProjectile
INFO: Projectile = IsProjectile(entity)
IsProp
INFO: Prop = IsProp(entity)
IsUnit
INFO: Unit = IsUnit(entity)
IssueAggressiveMove
INFO: IssueAggressiveMove
IssueAttack
INFO: IssueAttack
IssueBuildFactory
INFO: IssueBuildFactory
IssueBuildMobile
INFO: IssueBuildMobile
IssueCapture
INFO: IssueCapture
IssueClearCommands
INFO: IssueClearCommands
IssueClearFactoryCommands
INFO: IssueClearFactoryCommands
IssueDestroySelf
INFO: IssueDestroySelf
IssueDive
INFO: IssueDive
IssueFactoryAssist
INFO: IssueFactoryAssist
IssueFactoryRallyPoint
INFO: IssueFactoryRallyPoint
IssueFerry
INFO: IssueFerry
IssueFormAggressiveMove
INFO: IssueFormAggressiveMove
IssueFormAttack
INFO: IssueFormAttack
IssueFormMove
INFO: IssueFormMove
IssueFormPatrol
INFO: IssueFormPatrol
IssueGuard
INFO: IssueGuard
IssueKillSelf
INFO: IssueKillSelf
IssueMove
INFO: IssueMove
IssueMoveOffFactory
INFO: IssueMoveOffFactory
IssueNuke
INFO: IssueNuke
IssueOverCharge
INFO: IssueOverCharge
IssuePatrol
INFO: IssuePatrol
IssuePause
INFO: IssuePause
IssueReclaim
INFO: IssueReclaim
IssueRepair
INFO: IssueRepair
IssueSacrifice
INFO: IssueSacrifice
IssueScript
INFO: IssueScript
IssueSiloBuildNuke
INFO: IssueSiloBuildNuke
IssueSiloBuildTactical
INFO: IssueSiloBuildTactical
IssueStop
INFO: IssueStop
IssueTactical
INFO: IssueTactical
IssueTeleport
INFO: IssueTeleport
IssueTeleportToBeacon
INFO: IssueTeleportToBeacon
IssueTransportLoad
INFO: IssueTransportLoad
IssueTransportUnload
INFO: IssueTransportUnload
IssueTransportUnloadSpecific
INFO: IssueTransportUnloadSpecific
IssueUpgrade
INFO: IssueUpgrade
LUnitMove
INFO: ScriptTask.LUnitMove(self,target)
LUnitMoveNear
INFO: ScriptTask.LUnitMoveNear(self,target,range)
ListArmies
INFO:
MetaImpact
INFO: MetaImpact(instigator,location,fMaxRadius,iAmount,affectsCategory,[damageFriendly])
NotifyUpgrade
INFO: NotifyUpgrade(from,to)
OkayToMessWithArmy
INFO: Return true if the current command source is authorized to mess with the given army.:Or if cheats are enabled.
ParseEntityCategory
INFO: parse a string to generate a new entity category
PlayLoop
INFO: handle = PlayLoop(self,sndParams)
Random
INFO: Random([[min,] max])
RemoveBuildRestriction
INFO: RemoveBuildRestriction(army,category) - Remove a category from the restricted list
RemoveEconomyEvent
INFO: RemoveEconomyEvent(unit, event)
SelectedUnit
INFO: unit = SelectedUnit() -- Returns the currently selected unit. For use at the lua console, so you can call Lua methods on a unit.
SetAlliance
INFO: SetAlliance(army1,army2,<Neutral|Enemy|Ally>)
SetAllianceOneWay
INFO: SetAllianceOneWay(army1,army2,<Neutral|Enemy|Ally>)
SetAlliedVictory
INFO: SetAlliedVictory(army,bool)
SetArmyAIPersonality
INFO: SetArmyAIPersonality(army,personality)
SetArmyColor
INFO: SetArmyColor(army,r,g,b)
SetArmyColorIndex
INFO: SetArmyColorIndex(army,index)
SetArmyEconomy
INFO: army, mass, energy
SetArmyFactionIndex
INFO: SetArmyFactionIndex(army,index)
SetArmyOutOfGame
INFO: SetArmyOutOfGame(army) -- indicate that the supplied army has been defeated.
SetArmyPlans
INFO: army, plans
SetArmyShowScore
INFO: SetArmyColor(army, bool) - determines if the user should be able to see the army score
SetArmyStart
INFO: army, x, z
SetArmyStatsSyncArmy
INFO: Set the army index for which to sync army stats (-1 for none)
SetArmyUnitCap
INFO: army, unitCap
SetIgnoreArmyUnitCap
INFO: army, flag
SetIgnorePlayableRect
INFO: army, flag
SetPlayableRect
INFO: SetPlayableRect( minX, minZ, maxX, maxZ )
SetTerrainType
INFO: SetTerrainType(x,z,type)
SetTerrainTypeRect
INFO: SetTerrainType(rect,type)
ShouldCreateInitialArmyUnits
INFO:
SimConExecute
INFO: SimConExecute('command string') -- Perform a console command
SplitProp
INFO: SplitProp(original, blueprint_name) -- split a prop into multiple child props, one per bone; returns all the created props
StopLoop
INFO: StopLoop(self,handle)
SubmitXMLArmyStats
INFO: Request that we submit xml army stats to gpg.net.
TryCopyPose
INFO: TryCopyPose(unitFrom,entityTo,bCopyWorldTransform)
Warp
INFO: Warp( unit, location, [orientation] )
_c_CreateEntity
INFO: _c_CreateEntity(spec)
_c_CreateShield
INFO: _c_CreateShield(spec)
print
INFO: Print a log message
### Sim.CAiAttackerImpl
CanAttackTarget
INFO: Loop through the weapons to see if the target can be attacked
FindBestEnemy
INFO: Find the best enemy target for a weapon
ForceEngage
INFO: Force to engage enemy target
GetDesiredTarget
INFO: Get the desired target
GetMaxWeaponRange
INFO: Loop through the weapons to find the weapon with the longest range that is not manual fire
GetPrimaryWeapon
INFO: Loop through the weapons to find our primary weapon
GetTargetWeapon
INFO: Loop through the weapons to find one that we can use to attack target
GetUnit
INFO: Returns the unit this attacker is bound to.
GetWeaponCount
INFO: Return the count of weapons
HasSlavedTarget
INFO: Check if the attack has a slaved weapon that currently has a target
IsTargetExempt
INFO: Check if the target is exempt from being attacked
IsTooClose
INFO: Check if the target is too close to our weapons
IsWithinAttackRange
INFO: Check if the target is within any weapon range
ResetReportingState
INFO: Reset reporting state
SetDesiredTarget
INFO: Set the desired target
Stop
INFO: Stop the attacker
moho.CAiAttackerImpl_methods
INFO:
### Sim.CAiBrain
AssignThreatAtPosition
INFO: CAiBrain:AssignThreatAtPosition(position, threat, [decay], [threattype])
AssignUnitsToPlatoon
INFO: CAiBrain:AssignUnitsToPlatoon()
BuildPlatoon
INFO: brain:BuildPlatoon()
BuildStructure
INFO: brain:BuildStructure(builder, structureName, locationInfo)
BuildUnit
INFO: brain:BuildUnit()
CanBuildPlatoon
INFO: brain:CanBuildPlatoon()
CanBuildStructureAt
INFO: brain:CanBuildStructureAt(blueprint, location)
CheckBlockingTerrain
INFO: CAiBrain:CheckBlockingTerrain( startPos, endPos, arcType )
CreateResourceBuildingNearest
INFO: brain:CreateResourceBuildingNearest(structureName, posX, posY)
CreateUnitNearSpot
INFO: brain:CreateUnitNearSpot(unitName, posX, posY)
DecideWhatToBuild
INFO: brain:DecideWhatToBuild(builder, type, buildingTypes)
DisbandPlatoon
INFO: CAiBrain:DisbandPlatoon()
DisbandPlatoonUniquelyNamed
INFO: CAiBrain:DisbandPlatoonUniquelyNamed()
FindClosestArmyWithBase
INFO: CAiBrain:FindClosestArmyWithBase()
FindPlaceToBuild
INFO: brain:FindPlaceToBuild(type, structureName, buildingTypes, relative, builder, optIgnoreAlliance, optOverridePosX, optOverridePosZ, optIgnoreThreatOver)
FindUnit
INFO: brain:FindUnit(unitCategory, needToBeIdle) -- Return an unit that matches the unit name (can specify idle or not)
FindUnitToUpgrade
INFO: brain:FindUnitToUpgrade(upgradeList) -- Return a unit and it's upgrade blueprint
FindUpgradeBP
INFO: brain:FindUpgradeBP(unitName, upgradeList) -- Return an upgrade blueprint for the unit passed in
GetArmyIndex
INFO: Returns the ArmyIndex of the army represented by this brain
GetArmyStartPos
INFO: brain:GetArmyStartPos()
GetArmyStat
INFO: brain:GetArmyStat(StatName,defaultValue)
GetAttackVectors
INFO: CAiBrain:GetAttackVectors()
GetAvailableFactories
INFO: brain:GetAvailableFactories()
GetBlueprintStat
INFO: Return a blueprint stat filtered by category
GetCurrentEnemy
INFO: Return this brain's current enemy
GetCurrentUnits
INFO: Return how many units of the given categories exist
GetEconomyIncome
INFO: CAiBrain:GetEconomyIncome()
GetEconomyRequested
INFO: CAiBrain:GetEconomyRequested()
GetEconomyStored
INFO: CAiBrain:GetEconomyStored()
GetEconomyStoredRatio
INFO: CAiBrain:GetEconomyStoredRatio()
GetEconomyTrend
INFO: CAiBrain:GetEconomyTrend()
GetEconomyUsage
INFO: CAiBrain:GetEconomyUsage()
GetFactionIndex
INFO: Returns the faction of the army represented by this brain
GetHighestThreatPosition
INFO: CAiBrain:GetHighestThreatPosition( ring, restriction, [threatType], [armyIndex] )
threatposition, threatvalue = GetHighestThreatPosition( rings, restriction, [threatType], [armyIndex] )
Always reports a threatvalue of zero for Allies or self
GetListOfUnits
INFO: brain:GetListOfUnits(entityCategory, needToBeIdle, requireBuilt)
requireBuilt flag defaults to false which excludes units that are NOT finished
GetMapWaterRatio
INFO: CAiBrain:GetMapWaterRatio()
GetNoRushTicks
INFO: CAiBrain:GetNoRushTicks()
GetNumPlatoonsTemplateNamed
INFO: GetNumPlatoonsTemplateNamed
GetNumPlatoonsWithAI
INFO: GetNumPlatoonsWithAI
GetNumUnitsAroundPoint
INFO: CAiBrain:GetNumUnitsAroundPoint()
GetPersonality
INFO: Return the personality for this brain to use
GetPlatoonUniquelyNamed
INFO: CAiBrain:GetPlatoonUniquelyNamed()
GetPlatoonsList
INFO: CAiBrain:GetPlatoonsList()
GetThreatAtPosition
INFO: CAiBrain:GetThreatAtPosition(position, ring, restriction, [threatType], [armyIndex] )
GetThreatBetweenPositions
INFO: CAiBrain:GetThreatBetweenPositions( position, position, restriction, [threatType], [armyIndex] )
GetThreatsAroundPosition
INFO: CAiBrain:GetThreatsAroundPosition( position, ring, restriction, [threatType], [armyIndex] )
GetUnitBlueprint
INFO: blueprint = brain:GetUnitBlueprint(bpName)
GetUnitsAroundPoint
INFO: CAiBrain:GetUnitsAroundPoint( category, position, radius, 'Ally' or 'Enemy')
-- returns list of all units (finished or not finished) within the given parameters
GiveResource
INFO: GiveResource(type,amount)
GiveStorage
INFO: GiveStorage(type,amount)
IsAnyEngineerBuilding
INFO: brain:IsAnyEngineerBuilding(category)
IsOpponentAIRunning
INFO: Returns true if opponent AI should be running
MakePlatoon
INFO: CAiBrain:MakePlatoon()
NumCurrentlyBuilding
INFO: brain:NumCurrentlyBuilding( entityCategoryOfBuildee, entityCategoryOfBuilder )
PickBestAttackVector
INFO: CAiBrain:PickBestAttackVector()
PlatoonExists
INFO: CAiBrain:PlatoonExists()
RemoveArmyStatsTrigger
INFO: Remove an army stats trigger
SetArmyStat
INFO: SetArmyStat(statname,val)
SetArmyStatsTrigger
INFO: Sets an army stat trigger
SetCurrentEnemy
INFO: Set the current enemy for this brain to attack
SetCurrentPlan
INFO: Set the current plan for this brain to run
SetGreaterOf
INFO: SetGreaterOf(statname,val)
SetResourceSharing
INFO: SetResourceSharing(bool)
SetUpAttackVectorsToArmy
INFO: CAiBrain:SetUpAttackVectorsToArmy()
TakeResource
INFO: taken = TakeResource(type,amount)
moho.aibrain_methods
INFO:
### Sim.CAiNavigatorImpl
AtGoal
INFO:
BroadcastResumeTaskEvent
INFO: Broadcast event to resume any listening task that is currently suspended
CanPathToGoal
INFO:
FollowingLeader
INFO:
GetCurrentTargetPos
INFO: This returns the current navigator target position for the unit
GetGoalPos
INFO: This returns the current goal position of our navigator
GetStatus
INFO:
HasGoodPath
INFO:
IgnoreFormation
INFO:
IsIgnorningFormation
INFO:
SetDestUnit
INFO: Set the navigator's destination as another unit (chase/follow)
SetGoal
INFO: Set the navigator's destination as a particular position
SetSpeedThroughGoal
INFO::Set flag in navigator so the unit will know whether to stop at final goal:or speed through it. This would be set to True during a patrol or a series:of waypoints in a complex path.
moho.navigator_methods
INFO:
### Sim.CAiPersonality
GetAirUnitsEmphasis
INFO: CAiPersonality:GetAirUnitsEmphasis()
GetArmySize
INFO: CAiPersonality:GetArmySize()
GetAttackFrequency
INFO: CAiPersonality:GetAttackFrequency()
GetBotUnitsEmphasis
INFO: CAiPersonality:GetBotUnitsEmphasis()
GetChatFrequency
INFO: CAiPersonality:GetChatFrequency()
GetChatPersonality
INFO: CAiPersonality:GetChatPersonality()
GetCoordinatedAttacks
INFO: CAiPersonality:GetCoordinatedAttacks()
GetCounterForces
INFO: CAiPersonality:GetCounterForces()
GetDefenseDriven
INFO: CAiPersonality:GetDefenseDriven()
GetDifficulty
INFO: CAiPersonality:GetDifficulty()
GetDirectDamageEmphasis
INFO: CAiPersonality:GetDirectDamageEmphasis()
GetEconomyDriven
INFO: CAiPersonality:GetEconomyDriven()
GetExpansionDriven
INFO: CAiPersonality:GetExpansionDriven()
GetFactoryTycoon
INFO: CAiPersonality:GetFactoryTycoon()
GetFavouriteStructures
INFO: CAiPersonality:GetFavouriteStructures()
GetFavouriteUnits
INFO: CAiPersonality:GetFavouriteUnits()
GetFormationUse
INFO: CAiPersonality:GetFormationUse()
GetInDirectDamageEmphasis
INFO: CAiPersonality:GetInDirectDamageEmphasis()
GetIntelBuildingTycoon
INFO: CAiPersonality:GetIntelBuildingTycoon()
GetIntelGathering
INFO: CAiPersonality:GetIntelGathering()
GetPersonalityName
INFO: CAiPersonality:GetPersonalityName()
GetPlatoonSize
INFO: CAiPersonality:GetPlatoonSize()
GetQuittingTendency
INFO: CAiPersonality:GetQuittingTendency()
GetRepeatAttackFrequency
INFO: CAiPersonality:GetRepeatAttackFrequency()
GetSeaUnitsEmphasis
INFO: CAiPersonality:GetSeaUnitsEmphasis()
GetSpecialtyForcesEmphasis
INFO: CAiPersonality:GetSpecialtyForcesEmphasis()
GetSuperWeaponTendency
INFO: CAiPersonality:GetSuperWeaponTendency()
GetSupportUnitsEmphasis
INFO: CAiPersonality:GetSupportUnitsEmphasis()
GetSurvivalEmphasis
INFO: CAiPersonality:GetSurvivalEmphasis()
GetTankUnitsEmphasis
INFO: CAiPersonality:GetTankUnitsEmphasis()
GetTargetSpread
INFO: CAiPersonality:GetTargetSpread()
GetTeamSupport
INFO: CAiPersonality:GetTeamSupport()
GetTechAdvancement
INFO: CAiPersonality:GetTechAdvancement()
GetUpgradesDriven
INFO: CAiPersonality:GetUpgradesDriven()
moho.aipersonality_methods
INFO:
### Sim.CAimManipulator
OnTarget
INFO: AimManipulator:OnTarget()
SetAimHeadingOffset
INFO: AimManipulator:SetAimHeadingOffset( offset )
SetEnabled
INFO: AimManipulator:SetEnabled(flag)
SetFiringArc
INFO: AimManipulator:SetFiringArc(minHeading, maxHeading, headingMaxSlew, minPitch, maxPitch, pitchMaxSlew)
SetHeadingPitch
INFO: AimManipulator:SetHeadingPitch( heading, pitch )
SetResetPoseTime
INFO: AimManipulator:SetResetPoseTime(resetTime)
base
INFO: derived from IAniManipulator
moho.AimManipulator
INFO:
### Sim.CAnimationManipulator
GetAnimationFraction
INFO: fraction = AnimationManipulator:GetAnimationFraction()
GetAnimationTime
INFO: time = AnimationManipulator:GetAnimationTime()
GetRate
INFO: rate = AnimationManipulator:GetRate()
PlayAnim
INFO: AnimManipulator:PlayAnim(entity, animName, looping=false)
SetAnimationFraction
INFO: AnimationManipulator:SetAnimationFraction(fraction)
SetAnimationTime
INFO: AnimationManipulator:SetAnimationTime(fraction)
SetBoneEnabled
INFO: AnimationManipulator:SetBoneEnabled(bone, value, include_decscendants=true)
SetDirectionalAnim
INFO: AnimationManipulator:SetDirectionalAnim(bool)
SetDisableOnSignal
INFO: AnimationManipulator:SetDisableOnSignal(bool)
SetOverwriteMode
INFO: AnimationManipulator:SetOverwriteMode(bool)
SetRate
INFO: AnimationManipulator:SetRate(rate)
Set the relative rate at which this anim plays; 1.0 is normal speed.
Rate can be negative to play backwards or 0 to pause.
base
INFO: derived from IAniManipulator
moho.AnimationManipulator
INFO:
### Sim.CBoneEntityManipulator
base
INFO: derived from IAniManipulator
moho.BoneEntityManipulator
INFO:
### Sim.CBuilderArmManipulator
SetAimingArc
INFO: BuilderArmManipulator:SetAimingArc(minHeading, maxHeading, headingMaxSlew, minPitch, maxPitch, pitchMaxSlew)
SetHeadingPitch
INFO: CBuilderArmManipulator:SetHeadingPitch( heading, pitch )
base
INFO: derived from IAniManipulator
moho.BuilderArmManipulator
INFO:
### Sim.CCollisionManipulator
Enable
INFO: Fixme: this should just use base manipulator enable/disable
EnableTerrainCheck
INFO: Make manipulator check for terrain height intersection
WatchBone
INFO: CollisionDetector:WatchBone(bone) -- add the given bone to those watched by this manipulator
base
INFO: derived from IAniManipulator
moho.CollisionManipulator
INFO:
### Sim.CDamage
GetTarget
INFO: CDamage:GetTarget()
SetInstigator
INFO: CDamage:SetInstigator()
SetTarget
INFO: CDamage:SetTarget()
moho.CDamage
INFO:
### Sim.CDecalHandle
moho.CDecalHandle
INFO:
### Sim.CEconomyEvent
moho.EconomyEvent
INFO:
### Sim.CFootPlantManipulator
moho.FootPlantManipulator
INFO:
### Sim.CPlatoon
AttackTarget
INFO: CPlatoon:AttackTarget()
CalculatePlatoonThreat
INFO: CPlatoon:CalculatePlatoonThreat()
CalculatePlatoonThreatAroundPosition
INFO: CPlatoon:CalculatePlatoonThreatAroundPosition()
CanAttackTarget
INFO: CPlatoon:CanAttackTarget()
CanConsiderFormingPlatoon
INFO: CPlatoon:CanConsiderFormingPlatoon()
CanFormPlatoon
INFO: CPlatoon:CanFormPlatoon()
Destroy
INFO: CPlatoon:Destroy()
DisbandOnIdle
INFO: CPlatoon:DisbandOnIdle()
FerryToLocation
INFO: CPlatoon:FerryToLocation()
FindClosestUnit
INFO: CPlatoon:FindClosestUnit()
FindClosestUnitToBase
INFO: CPlatoon:FindClosestUnitToBase()
FindFurthestUnit
INFO: CPlatoon:FindFurthestUnit()
FindHighestValueUnit
INFO: CPlatoon:FindHighestValueUnit()
FindPrioritizedUnit
INFO: CPlatoon:FindPrioritizedUnit()
FormPlatoon
INFO: CPlatoon:FormPlatoon()
GetAIPlan
INFO: CPlatoon:GetAIPlan()
GetBrain
INFO: CPlatoon:GetBrain()
GetFactionIndex
INFO: CPlatoon:GetFactionIndex()
GetFerryBeacons
INFO: CPlatoon:GetFerryBeacons()
GetPersonality
INFO: CPlatoon:GetPersonality()
GetPlatoonLifetimeStats
INFO: CPlatoon:GetPlatoonLifetimeStats()
GetPlatoonPosition
INFO: CPlatoon:GetPlatoonPosition()
GetPlatoonUniqueName
INFO: CPlatoon:GetPlatoonUniqueName()
GetPlatoonUnits
INFO: platoon:GetPlatoonUnits()
GetSquadPosition
INFO: CPlatoon:GetSquadPosition()
GetSquadUnits
INFO: CPlatoon:GetSquadUnits()
GuardTarget
INFO: CPlatoon:GuardTarget()
IsAttacking
INFO: CPlatoon:IsAttacking()
IsCommandsActive
INFO: CPlatoon:IsCommandsActive()
IsFerrying
INFO: CPlatoon:IsFerrying()
IsMoving
INFO: CPlatoon:IsMoving()
IsOpponentAIRunning
INFO: CPlatoon:IsOpponentAIRunning()
IsPatrolling
INFO: CPlatoon:IsPatrolling()
LoadUnits
INFO: CPlatoon:LoadUnits()
MoveToLocation
INFO: CPlatoon:MoveToLocation()
MoveToTarget
INFO: CPlatoon:MoveToTarget()
Patrol
INFO: CPlatoon:Patrol()
PlatoonCategoryCount
INFO: Count how many units fit the specified category
PlatoonCategoryCountAroundPosition
INFO: Count how many units fit the specified category around a position
SetPlatoonFormationOverride
INFO: CPlatoon:SetPlatoonFormationOverride()
SetPrioritizedTargetList
INFO: CPlatoon:SetPrioritizedTargetList()
Stop
INFO: CPlatoon:Stop()
SwitchAIPlan
INFO: CPlatoon:SwitchAIPlan()
UniquelyNamePlatoon
INFO: CPlatoon:UniquelyNamePlatoon()
UnloadAllAtLocation
INFO: CPlatoon:UnloadAllAtLocation()
UnloadUnitsAtLocation
INFO: CPlatoon:UnloadUnitsAtLocation()
UseFerryBeacon
INFO: CPlatoon:UseFerryBeacon()
UseTeleporter
INFO: CPlatoon:UseTeleporter()
moho.platoon_methods
INFO:
### Sim.CRotateManipulator
ClearGoal
INFO: RotateManipulator:ClearGoal()
GetCurrentAngle
INFO: RotateManipulator:GetCurrentAngle()
SetAccel
INFO: RotateManipulator:SetAccel(degrees_per_second_squared)
SetCurrentAngle
INFO: RotateManipulator:SetCurrentAngle(angle)
SetFollowBone
INFO: RotateManipulator:SetFollowBone(bone)
SetGoal
INFO: RotateManipulator:SetGoal(self, degrees)
SetSpeed
INFO: RotateManipulator:SetSpeed(self, degrees_per_second)
SetSpinDown
INFO: RotateManipulator:SetSpinDown(self, flag)
SetTargetSpeed
INFO: RotateManipulator:SetTargetSpeed(degrees_per_second)
base
INFO: derived from IAniManipulator
moho.RotateManipulator
INFO:
### Sim.CSlaveManipulator
base
INFO: derived from IAniManipulator
moho.SlaveManipulator
INFO:
### Sim.CSlideManipulator
SetAcceleration
INFO: CSlideManipulator:SetAcceleration(acc)
SetDeceleration
INFO: CSlideManipulator:SetDeceleration(dec)
SetGoal
INFO: CSlideManipulator:SetGoal(goal_x, goal_y, goal_z)
SetSpeed
INFO: CSlideManipulator:SetSpeed(speed)
SetWorldUnits
INFO: CSlideManipulator:SetWorldUnits(bool)
base
INFO: derived from IAniManipulator
moho.SlideManipulator
INFO:
### Sim.CStorageManipulator
moho.StorageManipulator
INFO:
### Sim.CThrustManipulator
base
INFO: derived from IAniManipulator
moho.ThrustManipulator
INFO:
### Sim.CUnitScriptTask
SetAIResult
INFO: Set the AI result, success or fail
moho.ScriptTask_Methods
INFO:
### Sim.CollisionBeamEntity
Enable
INFO: CollisionBeamEntity:Enable()
GetLauncher
INFO: CollisionBeamEntity:GetLauncher()
IsEnabled
INFO: bool = CollisionBeamEntity:IsEnabled()
SetBeamFx
INFO: CollisionBeamEntity:SetBeamFx(beamEmitter, checkCollision) -- set an emitter to be controlled by this beam. Its length parameter will be set from the beam entity's collision distance.
__init
INFO: beam = CreateCollisionBeam(spec)
spec is a table with the following fields defined:
spec.Weapon = <weapon to attach to>
spec.OtherBone = <bone of weapon's unit to attach to>
spec.CollisionCheckInterval = <interval in ticks>
spec.BeamBone = <which end of beam to attach>
base
INFO: derived from Entity
moho.CollisionBeamEntity
INFO:
### Sim.Entity
AddManualScroller
INFO: Entity:AddManualScroller(scrollSpeed1, scrollSpeed2)
AddPingPongScroller
INFO: Entity:AddPingPongScroller(ping1, pingSpeed1, pong1, pongSpeed1, ping2, pingSpeed2, pong2, pongSpeed2)
AddShooter
INFO: AddShooter(shooter)
AddThreadScroller
INFO: Entity:AddThreadScroller(sideDist, scrollMult)
AddWorldImpulse
INFO: AddWorldImpulse(self, Ix, Iy, Iz, Px, Py, Pz) Note: Does not appear to be functional.
AdjustHealth
INFO: Entity:AdjustHealth(instigator, delta)
AttachBoneTo
INFO: Entity:AttachBoneTo(selfbone, entity, bone)
AttachBoneToEntityBone
INFO: Attach a unit bone position to an entity bone position
AttachTo
INFO: Entity:AttachTo(entity, bone)
BeenDestroyed
INFO: Entity:BeenDestroyed()
CreateProjectile
INFO: Entity:CreateProjectile(proj_bp, [ox, oy, oz], [dx, dy, dz]
CreateProjectileAtBone
INFO: Entity:CreateProjectileAtBone(projectile_blueprint, bone)
CreatePropAtBone
INFO: Entity:CreatePropAtBone(boneindex,prop_blueprint_id)
Destroy
INFO: Entity:Destroy()
DetachAll
INFO: Entity:DetachAll(bone,[skipBallistic])
DetachFrom
INFO: Entity:DetachFrom([skipBallistic])
DisableIntel
INFO: Intel:DisableIntel(type)
EnableIntel
INFO: EnableIntel(type)
FallDown
INFO: Entity:FallDown(dx,dy,dz,force) -- start falling down
GetAIBrain
INFO: GetAIBrain(self)
GetArmy
INFO: GetArmy(self)
GetBlueprint
INFO: blueprint = Entity:GetBlueprint()
GetBoneCount
INFO: Entity:GetBoneCount() -- returns number of bones in this entity's skeleton
GetBoneDirection
INFO: Entity:GetBoneDirection(bone_name)
GetBoneName
INFO: Entity:GetBoneName(i) -- return the name of the i'th bone of this entity (counting from 0)
GetCollisionExtents
INFO: Entity:GetCollisionExtents()
GetEntityId
INFO: Entity:GetEntityId()
GetFractionComplete
INFO: Entity:GetFractionComplete()
GetHeading
INFO: Entity:GetHeading()
GetHealth
INFO: Entity:GetHealth()
GetIntelRadius
INFO: GetIntelRadius(type)
GetMaxHealth
INFO: Entity:GetMaxHealth()
GetOrientation
INFO: Entity:GetOrientation()
GetParent
INFO: Entity:GetParent()
GetPosition
INFO: Entity:GetPosition([bone_name])
GetPositionXYZ
INFO: Entity:GetPositionXYZ([bone_name])
GetScale
INFO: Entity:GetScale() -> sx,sy,sz -- return current draw scale of this entity
InitIntel
INFO: InitIntel(army,type,<radius>)
IsIntelEnabled
INFO: IsIntelEnabled(type)
IsValidBone
INFO: Entity:IsValidBone(nameOrIndex,allowNil=false)
Kill
INFO: Entity:Kill(instigator,type,excessDamageRatio)
PlaySound
INFO: Entity:PlaySound(params)
PushOver
INFO: Entity:PushOver(nx, ny, nz, depth)
ReachedMaxShooters
INFO: ReachedMaxShooters()
RemoveScroller
INFO: Entity:RemoveScroller()
RemoveShooter
INFO: RemoveShooter(shooter)
RequestRefreshUI
INFO: Entity:RequestRefreshUI()
SetAmbientSound
INFO: Entity:SetAmbientSound(paramTableDetail,paramTableRumble)
SetCollisionShape
INFO: Entity:SetCollisionShape(['Box'|'Sphere'|'None'], centerX, Y, Z, size) -- size is radius for sphere, x,y,z extent for box
SetDrawScale
INFO: Entity:SetDrawScale(size): Change mesh scale on the fly
SetHealth
INFO: Entity:SetHealth(instigator,health)
SetIntelRadius
INFO: SetRadius(type,radius)
SetMaxHealth
INFO: Entity:SetMaxHealth(maxhealth)
SetMesh
INFO: Entity:SetMesh(meshBp, bool keepActor): Change mesh on the fly
SetOrientation
INFO: Entity:SetOrientation(orientation, immediately )
SetParentOffset
INFO: Entity:SetParentOffset(vector)
SetPosition
INFO: Entity:SetPosition(vector,[immediate])
SetScale
INFO: Entity:SetScale(s) or Entity:SetScale(sx,sy,sz)
SetVizToAllies
INFO: SetVizToAllies(type)
SetVizToEnemies
INFO: SetVizToEnemies(type)
SetVizToFocusPlayer
INFO: SetVizToFocusPlayer(type)
SetVizToNeutrals
INFO: SetVizToNeutrals(type)
ShakeCamera
INFO: Entity:ShakeCamera(radius, max, min, duration)
Shake the camera. This is a method of entities rather than a global function
because it takes the position of the entity as the epicenter where it shakes more.
radius - distance from epicenter at which shaking falls off to 'min'
max - size of shaking in world units, when looking at epicenter
min - size of shaking in world units, when at 'radius' distance or farther
duration - length of time to shake for, in seconds
SinkAway
INFO: Entity:SinkAway(vy) -- sink into the ground
moho.entity_methods
INFO:
### Sim.IAniManipulator
Disable
INFO: Manipulator:Disable() -- disable a manipulator. This immediately removes it from the bone computation, which may result in the bone's position snapping.
Enable
INFO: Manipulator:Enable() -- enable a manipulator. Manipulators start out enabled so you only need this after calling Disable().
SetPrecedence
INFO: Manipulator:SetPrecedence(integer) -- change the precedence of this manipulator. Manipulators with higher precedence run first.
moho.manipulator_methods
INFO:
### Sim.IEffect
OffsetEmitter
INFO: Effect:OffsetEmitter(x,y,z)
ResizeEmitterCurve
INFO: Effect:ResizeEmitterCurve(parameter, time_in_ticks)Resize the emitter curve to the number of ticks passed in.
This is so if we change the lifetime of the emitter we can rescale some of the curves to match if needed.
Arguably this should happen automatically to all curves but the original design was screwed up.
returns the effect so you can chain calls like:
effect:SetEmitterParam('x',1):ScaleEmitter(3.7)
ScaleEmitter
INFO: effect:ScaleEmitter(param, scale)
returns the effect so you can chain calls like:
effect:SetEmitterParam('x',1):ScaleEmitter(3.7)
SetBeamParam
INFO: effect:SetBeamParam('name', value)
SetEmitterCurveParam
INFO: Effect:SetEmitterCurveParam(param_name, height, size)
SetEmitterParam
INFO: effect:SetEmitterParam('name', value)returns the effect so you can chain calls like:
effect:SetEmitterParam('x',1):ScaleEmitter(3.7)
moho.IEffect
INFO:
### Sim.MotorFallDown
moho.MotorFallDown
INFO:
### Sim.Projectile
ChangeDetonateBelowHeight
INFO: Change the detonate below height for the projectile
ChangeMaxZigZag
INFO: Change the amount of zig zag in degrees per second
ChangeZigZagFrequency
INFO: Change the frequency of the zig zag --> min "0" (0 %), 0.5 (50%), max "1.0" (100%)
CreateChildProjectile
INFO: Projectile:CreateChildProjectile(blueprint)
GetCurrentSpeed
INFO: Projectile:GetCurrentSpeed() -> val
GetCurrentTargetPosition
INFO: Projectile:GetCurrentTargetPosition()
GetLauncher
INFO: Get who launched this projectile
GetTrackingTarget
INFO: Projectile:GetTrackingTarget()
GetVelocity
INFO: Projectile:GetVelocity() -> x,y,z
SetAcceleration
INFO: Projectile:SetAcceleration(accel)
SetBallisticAcceleration
INFO: Wrong number of arguments to Projectile:SetAccelerationVector(), expected 1, 2, or 4 but got %d
SetCollideEntity
INFO: Projectile:SetCollideEntity(onoff)
SetCollideSurface
INFO: Projectile:SetCollideSurface(onoff)
SetCollision
INFO: Projectile:SetCollision(onoff)
SetDamage
INFO: Projectile:SetDamage(amount, radius) -- change how much damage this projectile will do. Either amount or radius can be nil to leave unchanged.
SetDestroyOnWater
INFO: Projectile:SetDestroyOnWater(flag)
SetLifetime
INFO: Projectile:SetLifetime(seconds)
SetLocalAngularVelocity
INFO: Projectile:SetLocalAngularVelocity(x,y,z)
SetMaxSpeed
INFO: Projectile:SetMaxSpeed(speed)
SetNewTarget
INFO: Projectile:SetNewTarget( entity )
SetNewTargetGround
INFO: Projectile:SetNewTargetGround( location )
SetScaleVelocity
INFO: Projectile:SetScaleVelocity(vs) or Projectile:SetScaleVelocity(vsx, vsy, vsz)
SetStayUpright
INFO: Projectile:SetStayUpright(truefalse)
SetTurnRate
INFO: Projectile:SetTurnRate(radians_per_second)
SetVelocity
INFO: Projectile:SetVelocity(speed) or Projectile:SetVelocity(vx,vy,vz)
SetVelocityAlign
INFO: Projectile:SetVelocityAlign(truefalse)
SetVelocityRandomUpVector
INFO: SetVelocityRandomUpVector(self)
StayUnderwater
INFO: Projectile:StayUnderwater(onoff)
TrackTarget
INFO: Projectile:TrackTarget(onoff)
base
INFO: derived from Entity
moho.projectile_methods
INFO:
### Sim.Prop
base
INFO: derived from Entity
moho.prop_methods
INFO:
### Sim.ReconBlip
GetSource
INFO: unit = ReconBlip:GetSource()
IsKnownFake
INFO: bool = ReconBlip:IsKnownFake()
IsMaybeDead
INFO: bool = ReconBlip:IsMaybeDead()
IsOnOmni
INFO: bool = ReconBlip:IsOnOmni()
IsOnRadar
INFO: bool = ReconBlip:IsOnRadar()
IsOnSonar
INFO: bool = ReconBlip:IsOnSonar()
IsSeenEver
INFO: bool = ReconBlip:IsSeenEver()
IsSeenNow
INFO: bool = ReconBlip:IsSeenNow()
base
INFO: derived from Entity
moho.blip_methods
INFO:
### Sim.Shield
moho.shield_methods
INFO:
### Sim.Unit
AddCommandCap
INFO: unit:AddCommandCap(capName) -- Add a command cap to a unit.
AddToggleCap
INFO: unit:AddToggleCap(capName) -- Add a toggle cap to a unit.
AddUnitToStorage
INFO: Unit:AddUnitToStorage( storedUnit )
AlterArmor
INFO: Unit:AlterArmor(damageTypeName, multiplier)
CalculateWorldPositionFromRelative
INFO: Calculate the desired world position from the supplied relative vector from the center of the unit
CanBuild
INFO: CanBuild(self, blueprint
CanPathTo
INFO: See if the unit can path to the goal
CanPathToRect
INFO: See if the unit can path to the goal rectangle
ClearFocusEntity
INFO: ClearFocusEntity(self)
EnableManipulators
INFO: Unit:EnableManipulators([string boneName | int boneIndex], bool Enable)
GetArmorMult
INFO: mult = Unit:GetArmorMult(damageTypeName)
GetAttacker
INFO: GetAttacker() - get the tactical attack manager object of this unit
GetBlip
INFO: blip = GetBlip(armyIndex) - returns a blip (if any) that the given army has for the unit
GetBuildRate
INFO: unit:GetBuildRate() -- returns the build rate of a unit: what fraction of target unit it builds per second.
GetCargo
INFO: GetCargo(self)
GetCommandQueue
INFO: Unit:GetCommandQueue()
GetConsumptionPerSecondEnergy
INFO: Get the consumption of energy of the unit
GetConsumptionPerSecondMass
INFO: Get the consumption of mass of the unit
GetCurrentLayer
INFO: GetUnitId(self)
GetCurrentMoveLocation
INFO: Unit:GetCurrentMoveLocation()
GetFireState
INFO: Get the fire state for the unit
GetFocusUnit
INFO: GetFocusUnit(self)
GetFuelRatio
INFO: Get the fuel ratio
GetFuelUseTime
INFO: Get the fuel use time
GetGuardedUnit
INFO: Unit:GetGuardedUnit()
GetGuards
INFO: Unit:GetGuards()
GetHealth
INFO: GetHealth(self)
GetNavigator
INFO: GetNavigator() - get the navigator object of this unit
GetNukeSiloAmmoCount
INFO: Unit:GetNukeSiloAmmoCount()
GetNumBuildOrders
INFO: Get number of factory/engineer build orders that fit in the specified category
GetProductionPerSecondEnergy
INFO: Get the production of energy of the unit
GetProductionPerSecondMass
INFO: Get the production of mass of the unit
GetRallyPoint
INFO: Get the rally point for the factory
GetResourceConsumed
INFO: Return the fraction of requested resources this unit consumed last tick. Normally 1, but can be fractional if economy is struggling.
GetScriptBit
INFO: Get the current toggle state of the script bit that matches the string
GetShieldRatio
INFO: Get the shield ratio
GetStat
INFO: GetStat(Name[,defaultVal])
GetTacticalSiloAmmoCount
INFO: Unit:GetTacticalSiloAmmoCount()
GetTargetEntity
INFO: Return our target unit if we have one
GetTransportFerryBeacon
INFO: Unit:GetTransportFerryBeacon()
GetUnitId
INFO: GetUnitId(self)
GetVelocity
INFO: GetVelocity() -> x,y,z
GetWeapon
INFO: GetWeapon(self,index) -- return the index'th weapon of this unit. Index must be between 1 and self:GetWeaponCount(), inclusive.
GetWeaponCount
INFO: GetWeaponCount(self) -- return the number of weapons on this unit. Note that dummy weapons are not included in the count, so this may differ from the number of weapons defined in the unit's blueprint.
GetWorkProgress
INFO: GetWorkProgress()
GiveNukeSiloAmmo
INFO: Unit:GiveNukeSiloAmmo(num)
GiveTacticalSiloAmmo
INFO: Unit:GiveTacticalSiloAmmo(num)
HasMeleeSpaceAroundTarget
INFO: Unit:HasMeleeSpaceAroundTarget(target)
HasValidTeleportDest
INFO: Unit:HasValidTeleportDest()
HideBone
INFO: HideBone(self,bone,affectChildren)
IsBeingBuilt
INFO: Unit:IsBeingBuilt()
IsCapturable
INFO: Returns if this unit can be captured or not
IsIdleState
INFO: IsIdleState(unit)
IsMobile
INFO: bool IsMobile() - Is this a mobile unit?
IsMoving
INFO: bool IsMoving() - Is this unit moving?
IsOverchargePaused
INFO: Returns if this unit has its overcharge paused
IsPaused
INFO: Unit:IsPaused()
IsStunned
INFO: IsStunned(unit)
IsUnitState
INFO: IsUnitState(unit, stateName)
IsValidTarget
INFO: bool = IsValidTarget(self)
KillManipulator
INFO: Kill a specific manipulator held by a script object
KillManipulators
INFO: Unit:KillManipulators([boneName|boneIndex])
MeleeWarpAdjacentToTarget
INFO: Unit:MeleeWarpAdjacentToTarget(target)
PrintCommandQueue
INFO: Unit:PrintCommandQueue()
RecoilImpulse
INFO: RecoilImpulse(self, x, y, z)
RemoveBuildRestriction
INFO: Allow building of categories for this unit
RemoveCommandCap
INFO: unit:RemoveCommandCap(capName) -- Remove a command cap to a unit.
RemoveNukeSiloAmmo
INFO: Unit:RemoveNukeSiloAmmo(num)
RemoveTacticalSiloAmmo
INFO: Unit:RemoveTacticalSiloAmmo(num)
RemoveToggleCap
INFO: unit:RemoveToggleCap(capName) -- Remove a toggle cap to a unit.
RestoreBuildRestrictions
INFO: Restore buildable categories to that as defined in the blueprint
RestoreCommandCaps
INFO: Restore the command caps of the unit back to blueprint spec.
RestoreToggleCaps
INFO: Restore the toggle caps of the unit back to blueprint spec.
RevertCollisionShape
INFO: Revert the collision shape to the blueprint spec
RevertElevation
INFO: Revert the elevation of the unit back to the blueperint spec
RevertRegenRate
INFO: Restore regen rate of the unit back to blueprint spec.
ScaleGetBuiltEmitter
INFO: ScaleGetBuiltEmitter(self, emitter)
SetAccMult
INFO: Set the acceleration multiplier of the unit
SetAutoMode
INFO: Set auto silo build mode to on/off
SetBlockCommandQueue
INFO: SetBlockCommandQueue(unit, flag)
SetBreakOffDistanceMult
INFO: Set the break off distance multiplier of the unit
SetBreakOffTriggerMult
INFO: Set the break off trigger multiplier of the unit
SetBuildRate
INFO: unit:SetBuildRate(frac) -- Set the build rate of a unit: what fraction of target unit it builds per second.
SetBusy
INFO: SetBusy(unit, flag)
SetCapturable
INFO: Set if this unit can be captured or not.
SetConsumptionActive
INFO: Unit:SetConsumptionActive(flag)
SetConsumptionPerSecondEnergy
INFO: unit:SetConsumptionPerSecondEnergy(value) -- Set the consumption of energy of a unit
SetConsumptionPerSecondMass
INFO: Set the consumption of mass of the unit
SetCreator
INFO: Set the creator for this unit
SetCustomName
INFO: Unit:SetCustomName(name)
SetDoNotTarget
INFO: SetDoNotTarget(unit, flag)
SetElevation
INFO: Set the elevation of the unit
SetFireState
INFO: Set a specific fire state for the retaliation state of the unit
SetFocusEntity
INFO: SetFocusUnit(self, focus)
SetFuelRatio
INFO: Set the fuel ratio
SetFuelUseTime
INFO: Set the fuel use time
SetImmobile
INFO: SetImmobile(unit, flag)
SetIsValidTarget
INFO: SetIsValidTarget(self,bool)
SetOverchargePaused
INFO: Set if this unit has an overcharge pasued.
SetPaused
INFO: Unit:SetPaused()
SetProductionActive
INFO: Unit:SetProductionActive(flag)
SetProductionPerSecondEnergy
INFO: Set the production of energy of the unit
SetProductionPerSecondMass
INFO: Set the production of mass of the unit
SetReclaimable
INFO: Set if this unit can be reclaimed or not.
SetRegenRate
INFO: unit:SetRegenRate(rate) -- Set the regen rate of a unit.
SetScriptBit
INFO: Set the script bit that matches the string to the desired state
SetShieldRatio
INFO: Set the shield ratio
SetSpeedMult
INFO: Set the speed multiplier of the unit
SetStat
INFO: SetStat(Name, Value)
SetStrategicUnderlay
INFO: SetStrategicUnderlay(icon)
SetStunned
INFO: SetStunned(unit, time)
SetTurnMult
INFO: Set the turn multiplier of the unit
SetUnSelectable
INFO: SetUnSelectable(unit, flag)
SetUnitState
INFO: SetUnitState(name, bool)
SetWorkProgress
INFO: SetWorkProgress(float)
ShowBone
INFO: ShowBone(self,bone,affectChildren)
StopSiloBuild
INFO: StopSiloBuild(unit)
TestCommandCaps
INFO: Test if a unit has this specified set to true in the blueprint spec.
TestToggleCaps
INFO: Test if a unit has this specified set to true in the blueprint spec.
ToggleFireState
INFO: Toggle the fire state for the retaliation state of the unit
ToggleScriptBit
INFO: Toggle the script bit that matches the string
TransportDetachAllUnits
INFO: DetachAllUnits(self,destroySomeUnits)
TransportHasAvailableStorage
INFO: TransportHasAvailableStorage(self)
TransportHasSpaceFor
INFO: TransportHasSpaceFor(self,target)
base
INFO: derived from Entity
moho.unit_methods
INFO:
### Sim.UnitWeapon
CanFire
INFO: UnitWeapon:CanFire()
ChangeDamage
INFO: UnitWeapon:ChangeDamage(value)
ChangeDamageRadius
INFO: UnitWeapon:ChangeDamageRadius(value)
ChangeDamageType
INFO: UnitWeapon:ChangeDamageType(typeName)
ChangeFiringTolerance
INFO: UnitWeapon:ChangeFiringTolerance(value)
ChangeMaxHeightDiff
INFO: UnitWeapon:ChangeMaxHeightDiff(value)
ChangeMaxRadius
INFO: UnitWeapon:ChangeMaxRadius(value)
ChangeMinRadius
INFO: UnitWeapon:ChangeMinRadius(value)
ChangeProjectileBlueprint
INFO: Change the projectile blueprint of a weapon
ChangeRateOfFire
INFO: UnitWeapon:ChangeRateOfFire(value)
CreateProjectile
INFO: UnitWeapon:CreateProjectile(muzzlebone)
DoInstaHit
INFO: UnitWeapon:DoInstaHit(bone, r,g,b, glow, width, texture, lifetime)
FireWeapon
INFO: bool = UnitWeapon:FireWeapon()
GetBlueprint
INFO: blueprint = UnitWeapon:GetBlueprint()
GetCurrentTarget
INFO: UnitWeapon:GetCurrentTarget()
GetCurrentTargetPos
INFO: UnitWeapon:GetCurrentTargetPos()
GetFireClockPct
INFO: Get the firing clock percent (0 - 1)
GetFiringRandomness
INFO: Get the firing randomness
GetProjectileBlueprint
INFO: blueprint = UnitWeapon:GetProjectileBlueprint()
IsFireControl
INFO: UnitWeapon:IsFireControl(label)
PlaySound
INFO: UnitWeapon:PlaySound(weapon,ParamTable)
ResetTarget
INFO: UnitWeapon:ResetTarget()
SetEnabled
INFO: UnitWeapon:SetEnabled(enabled)
SetFireControl
INFO: UnitWeapon:SetFireControl(label)
SetFireTargetLayerCaps
INFO: UnitWeapon:SetFireTargetLayerCaps(mask)
SetFiringRandomness
INFO: Set the firing randomness
SetTargetEntity
INFO: UnitWeapon:SetTarget(entity)
SetTargetGround
INFO: UnitWeapon:SetTarget(location)
SetTargetingPriorities
INFO: Set the targeting priorities for the unit
TransferTarget
INFO: Transfer target from 1 weapon to another
WeaponHasTarget
INFO: bool = UnitWeapon:HasTarget()
moho.weapon_methods
INFO:

## Unsafe
## Unsafe {.tabset}
### `Unsafe.<global>`
SHGetFolderPath
INFO: (name, create?) -- Interface to Win32 SHGetFolderPath api

## User
## User {.tabset}
### `User.<global>`
AddBlinkyBox
INFO: AddBlinkyBox(entityId, onTime, offTime, totalTime)
AddCommandFeedbackBlip
INFO: AddCommandFeedbackBlip(meshInfoTable, duration)
AddConsoleOutputReciever
INFO: handler AddConsoleOutputReciever(func(text))
AddInputCapture
INFO: AddInputCapture(control) - set a control as the current capture
AddSelectUnits
INFO: Add these units to the currently Selected lists
AddToSessionExtraSelectList
INFO: Add unit to the session extra select list
AnyInputCapture
INFO: bool AnyInputCapture() - returns true if there is anything currently on the capture stack
AudioSetLanguage
INFO: AudioSetLanguage(name()
ClearBuildTemplates
INFO: clear and disable the build templates.
ClearCurrentFactoryForQueueDisplay
INFO: ClearCurrentFactoryForQueueDisplay()
ClearFrame
INFO: ClearFrame(int head) - destroy all controls in frame, nil head will clear all frames
ClearSessionExtraSelectList
INFO: Clear the session extra select list
ConExecute
INFO: ConExecute('command string') -- Perform a console command
ConExecuteSave
INFO: ConExecuteSave('command string') -- Perform a console command, saved to stack
ConTextMatches
INFO: strings ContextMatches(string)
CopyCurrentReplay
INFO: CopyCurrentReplay(string profile, string newFilename) - copy the current replay to another file
CreateUnitAtMouse
INFO: CreateUnitAtMouse
CurrentTime
INFO: Get the current time in seconds, counting from 0 at application start. This is wall-clock time and is unaffected by gameplay.
DebugFacilitiesEnabled
INFO: bool DebugFacilitiesEnabled() - returns true if debug facilities are enabled.
DecreaseBuildCountInQueue
INFO: DecreaseBuildCountInQueue(queueIndex, count)
DeleteCommand
INFO: DeleteCommand(id)
DisableWorldSounds
INFO: DisableWorldSounds
EjectSessionClient
INFO: EjectSessionClient(int clientIndex) -- eject another client from your session
EnableWorldSounds
INFO: EnableWorldSounds
EngineStartFrontEndUI
INFO: EngineStartFrontEndUI() - kill current UI and start main menu from top
EngineStartSplashScreens
INFO: EngineStartSplashScreens() - kill current UI and start splash screens
EntityCategoryContains
INFO: See if a unit category contains this unit
EntityCategoryFilterDown
INFO: Filter a list of units to only those found in the category
EntityCategoryFilterOut
INFO: Filter a list of units to exclude those found in the category
ExecLuaInSim
INFO: Execute some lua code in the sim
ExitApplication
INFO: ExitApplication - request that the application shut down
ExitGame
INFO: ExitGame() - Quits the sim, but not the app
FlushEvents
INFO: FlushEvents() -- flush mouse/keyboard events
FormatTime
INFO: string FormatTime(seconds) - format a string displaying the time specified in seconds
GameTick
INFO: Get the current game time in ticks. The game time is the simulation time, that stops when the game is paused.
GameTime
INFO: Get the current game time in seconds. The game time is the simulation time, that stops when the game is paused.
GenerateBuildTemplateFromSelection
INFO: generate and enable build templates from the current selection.
GetActiveBuildTemplate
INFO: get active build template back to lua.
GetAntiAliasingOptions
INFO: obj GetAntiAliasingOptions()
GetArmiesTable
INFO: armyInfo GetArmiesTable()
GetArmyAvatars
INFO: table GetArmyAvatars() - return a table of avatar units for the army
GetArmyScore
INFO: int GetArmyScore(armyIndex)
GetAssistingUnitsList
INFO: Get a list of units assisting me
GetAttachedUnitsList
INFO: Get a list of units blueprint attached to transports
GetBlueprint
INFO: blueprint = GetBlueprint()
GetCamera
INFO: GetCamera(name)
GetCommandLineArg
INFO: CommandArgTable GetCommandLineArg(option, number)
GetCurrentUIState
INFO: state GetCurrentUIState() - returns 'splash', 'frontend' or 'game' depending on the current state of the ui
GetCursor
INFO: GetCursor()
GetEconomyTotals
INFO: table GetEconomyTotals()
GetFireState
INFO: Get the right fire state for the units passed in
GetFocusArmy
INFO: GetFocusArmy()
GetFrame
INFO: frame GetFrame(int head) - return the root UI frame for a given head
GetFrontEndData
INFO: table GetFrontEndData(key)
GetGameSpeed
INFO: Return the current game speed
GetGameTime
INFO: string GetGameTime() - returns a formatted string displaying the time the game has been played
GetGameTimeSeconds
INFO: float GetGameTimeSeconds() - returns game time in seconds
GetIdleEngineers
INFO: table GetIdleEngineers() - return a table of idle engineer units for the army
GetIdleFactories
INFO: table GetIdleFactories() - return a table of idle factory units for the army
GetInputCapture
INFO: control GetInputCapture() - returns the current capture control, or nil if none
GetIsAutoMode
INFO: See if anyone in the list is auto building
GetIsAutoSurfaceMode
INFO: See if anyone in the list is auto surfacing
GetIsPaused
INFO: Is anyone ins this list builder paused?
GetIsSubmerged
INFO: Determine if units are submerged (-1), not submerged(1) or unable to tell (0)
GetMouseScreenPos
INFO: vector GetMouseScreenPos()
GetMouseWorldPos
INFO: vector GetMouseWorldPos()
GetMovieVolume
INFO: GetMovieVolume()
GetNumRootFrames
INFO: int GetNumRootFrames() - returns the current number of root frames (typically one per head
GetOptions
INFO: obj GetOptions()
GetPreference
INFO: obj GetPreference(string, [default])
GetResourceSharing
INFO: bool GetResourceSharing()
GetRolloverInfo
INFO: rolloverInfo GetRolloverInfo()
GetScriptBit
INFO: Get the state for the script big
GetSelectedUnits
INFO: table GetSelectedUnits() - return a table of the currently selected units
GetSessionClients
INFO: GetSessionClients() -- return a table of the various clients in the current session.
GetSimRate
INFO: number GetSimRate()
GetSimTicksPerSecond
INFO: int GetSimTicksPerSecond()
GetSpecialFileInfo
INFO: table GetSpecialFileInfo(string profileName, string basename, string type) - get information on a profile based file, nil if unable to find
GetSpecialFilePath
INFO: string GetSpecialFilePath(string profilename, string filename, string type) - Given the base name of a special file, retuns the complete path
GetSpecialFiles
INFO: table GetSpecialFiles(string type)- returns a table of strings which are the names of files in special locations (currently SaveFile, Replay)
GetSpecialFolder
INFO: string GetSpecialFolder(string type)
GetSystemTime
INFO: string GetSystemTime() - returns a formatted string displaying the System time
GetSystemTimeSeconds
INFO: float GetSystemTimeSeconds() - returns System time in seconds
GetTextureDimensions
INFO: width, height GetTextureDimensions(filename, border = 1)
GetUIControlsAlpha
INFO: float GetUIControlsAlpha() -- get the alpha multiplier for 2d UI controls
GetUnitById
INFO: GetUnitById(id)
GetUnitCommandData
INFO: orders, buildableCategories, GetUnitCommandData(unitSet) -- given a set of units, gets the union of orders and unit categories (for determining builds)
GetUnitCommandFromCommandCap
INFO: string GetUnitCommandFromCommandCap(string) - given a RULEUCC type command, return the equivalent UNITCOMMAND command
GetValidAttackingUnits
INFO: table GetValidAttackingUnits() - return a table of the currently selected units
GetVolume
INFO: float GetVolume(category)
GpgNetActive
INFO: bool GpgNetActive()
GpgNetSend
INFO: GpgNetSend(cmd,args...)
HasCommandLineArg
INFO: HasCommandLineArg(option)
HasLocalizedVO
INFO: HasLocalizedVO(languageCode)
IN_AddKeyMapTable
INFO: IN_AddKeyMapTable(keyMapTable) - add a set of key mappings
IN_ClearKeyMap
INFO: IN_ClearKeyMap() - clears all key mappings
IN_RemoveKeyMapTable
INFO: IN_RemoveKeyMapTable(keyMapTable) - removes the keys from the key map
IncreaseBuildCountInQueue
INFO: DecreaseBuildCountInQueue(queueIndex, count)
InternalCreateBitmap
INFO: InternalCreateBitmap(luaobj,parent) -- for internal use by CreateBitmap()
InternalCreateBorder
INFO: InternalCreateBorder(luaobj,parent) -- for internal use by CreateBorder()
InternalCreateDiscoveryService
INFO: InternalCreateDiscoveryService(class)
InternalCreateDragger
INFO: InternalCreateDragger(luaobj) -- for internal use by CreateDragger()
InternalCreateEdit
INFO: InternalCreateEdit(luaobj,parent)
InternalCreateFrame
INFO: InternalCreateFrame(luaobj) -- For internal use by CreateFrame()
InternalCreateGroup
INFO: InternalCreateGroup(luaobj,parent) -- For internal use by CreateGroup()
InternalCreateHistogram
INFO: InternalCreateHistogram(luaobj,parent) -- For internal use by CreateHistogram()
InternalCreateItemList
INFO: InternalCreateItemList(luaobj,parent) -- for internal use by CreateItemList()
InternalCreateLobby
INFO: InternalCreateLobby(class, string protocol, int localPort, int maxConnections, string playerName, string playerUID, Boxed<weak_ptr<INetNATTraversalProvider> > natTraversalProvider)
InternalCreateMapPreview
INFO: InternalCreateMapPreview(luaobj,parent)
InternalCreateMesh
INFO: InternalCreateMesh(luaobj,parent) -- for internal use by CreateMesh()
InternalCreateMovie
INFO: InternalCreateMovie(luaobj,parent) -- for internal use by CreateMovie()
InternalCreateScrollbar
INFO: InternalCreateScrollbar(luaobj,parent,axis) -- for internal use by CreateScrollBar()
InternalCreateText
INFO: InternalCreateText(luaobj,parent)
InternalCreateWldUIProvider
INFO: InternalCreateWldUIProvider(luaobj) - create the C++ script object
InternalCreateWorldMesh
INFO: InternalCreateWorldMesh(luaobj) -- for internal use by WorldMesh()
InternalSaveGame
INFO: InternalSaveGame(filename, friendlyname, oncompletion) -- save the current session.
IsAlly
INFO: IsAlly(army1,army2)
IsEnemy
INFO: IsEnemy(army1,army2)
IsKeyDown
INFO: IsKeyDown(keyCode)
IsNeutral
INFO: IsNeutral(army1,army2)
IsObserver
INFO: IsObserver()
IssueBlueprintCommand
INFO: IssueBlueprintCommand(command, blueprintid, count, clear = false)
IssueCommand
INFO: IssueCommand(command,[string],[clear])
IssueDockCommand
INFO: IssueDockCommand(clear)
IssueUnitCommand
INFO: IssueUnitCommand(unitList,command,[string],[clear])
KeycodeMSWToMaui
INFO: int KeycodeMSWToMaui(int) - given a MS Windows char code, returns the Maui char code
KeycodeMauiToMSW
INFO: int KeycodeMauiToMSW(int) - given a char code from a key event, returns the MS Windows char code
LaunchGPGNet
INFO: LaunchGPGNet()
LaunchReplaySession
INFO: bool LaunchReplaySession(filename) - starts a replay of a given file, returns false if unable to launch
LaunchSinglePlayerSession
INFO: LaunchSinglePlayerSession(sessionInfo) -- launch a new single player session.
LoadSavedGame
INFO: bool LoadSavedGame(filename)
MapBorderAdd
INFO: MapBorderAdd(blueprintid)
MapBorderClear
INFO: MapBorderClear()
OpenURL
INFO: OpenURL(string) - open the default browser window to the specified URL
ParseEntityCategory
INFO: parse a string to generate a new entity category
PauseSound
INFO: PauseSound(categoryString,bPause)
PauseVoice
INFO: PauseVoice(categoryString,bPause)
PlaySound
INFO: handle = PlaySound(sndParams,prepareOnly)
PlayTutorialVO
INFO: PlayTutorialVO(params)
PlayVoice
INFO: PlayVoice(params,duck)
PostDragger
INFO: PostDragger(originFrame, keycode, dragger)
Make 'dragger' the active dragger from a particular frame. You can pass nil to cancel the current dragger.
PrefetchSession
INFO: PrefetchSession(mapname, mods, hipri) -- start a background load with the given map and mods. If hipri is true, this will interrupt any previous loads in progress.
Random
INFO: Random([[min,] max])
RemoveConsoleOutputReciever
INFO: RemoveConsoleOutputReciever(handler)
RemoveFromSessionExtraSelectList
INFO: Remove unit from the session extra select list
RemoveInputCapture
INFO: RemoveInputCapture(control) - remove the control from the capture array (always first from back)
RemoveProfileDirectories
INFO: RemoveProfileDirectories(string profile) - Removes the profile directory and all special files
RemoveSpecialFile
INFO: RemoveSpecialFile(string profilename, string basename, string type) - remove a profile based file from the disc
RenderOverlayEconomy
INFO: RenderOverlayEconomy(bool)
RenderOverlayIntel
INFO: RenderOverlayIntel(bool)
RenderOverlayMilitary
INFO: RenderOverlayMilitary(bool)
RestartSession
INFO: RestartSession() - Restart the current mission/skirmish/etc
SavePreferences
INFO: SavePreferences()
SelectUnits
INFO: Select the specified units
SessionCanRestart
INFO: Return true iff the active session can be restarted.
SessionEndGame
INFO: End the current game session.:The session says active, we just disconnect from everyone else and freeze play.
SessionGetCommandSourceNames
INFO: Return a table of:command sources.
SessionGetLocalCommandSource
INFO: Return the local command source.:Returns 0 if the local client can't issue commands.
SessionGetScenarioInfo
INFO: Return the table of scenario info that was originally passed to the sim on launch.
SessionIsActive
INFO: Return true iff there is a session currently running
SessionIsBeingRecorded
INFO: Return true iff the active session is a being recorded.
SessionIsGameOver
INFO: Return true iff the session has been won or lost yet.
SessionIsMultiplayer
INFO: Return true iff the active session is a multiplayer session.
SessionIsObservingAllowed
INFO: Return true iff observing is allowed in the active session.
SessionIsPaused
INFO: Return true iff the session is paused.
SessionIsReplay
INFO: Return true iff the active session is a replay session.
SessionRequestPause
INFO: Pause the world simulation.
SessionResume
INFO: Resume the world simulation.
SessionSendChatMessage
INFO: SessionSendChatMessage([client-or-clients,] message)
SetActiveBuildTemplate
INFO: set this as an active build template.
SetAutoMode
INFO: See if anyone in the list is auto building
SetAutoSurfaceMode
INFO: See if anyone in the list is auto surfacing
SetCurrentFactoryForQueueDisplay
INFO: currentQueueTable SetCurrentFactoryForQueueDisplay(unit)
SetCursor
INFO: SetCursor(cursor)
SetFireState
INFO: Set the specific fire state for the units passed in
SetFocusArmy
INFO: SetFocusArmy(armyIndex or -1)
SetFrontEndData
INFO: SetFrontEndData(key, data)
SetGameSpeed
INFO: Set the desired game speed
SetMovieVolume
INFO: SetMovieVolume(volume): 0.0 - 2.0
SetOverlayFilter
INFO: SetOverlayFilter()
SetOverlayFilters
INFO: SetOverlayFilters(list)
SetPaused
INFO: Pause builders in this list
SetPreference
INFO: SetPreference(string, obj)
SetUIControlsAlpha
INFO: SetUIControlsAlpha(float alpha) -- set the alpha multiplier for 2d UI controls
SetVolume
INFO: SetVolume(category, volume)
SimCallback
INFO: SimCallback(callback[,bool]): Execute a lua function in sim
callback = {
 Func =: function name (in the SimCallbacks.lua module) to call
 Args =: Arguments as a lua object
}
If bool is specified and true, sends the current selection with the command
SoundIsPrepared
INFO: bool = SoundIsPrepared(handle)
StartSound
INFO: StartSound(handle)
StopAllSounds
INFO: StopAllSounds
StopSound
INFO: StopSound(handle,[immediate=false])
SyncPlayableRect
INFO: SyncPlayableRect(region)
TeamColorMode
INFO: TeamColorMode(bool)
ToggleFireState
INFO: Set the right fire state for the units passed in
ToggleScriptBit
INFO: Set the right fire state for the units passed in
UISelectAndZoomTo
INFO: UISelectAndZoomTo(userunit,[seconds])
UISelectionByCategory
INFO: UISelectionByCategory(expression, addToCurSel, inViewFrustum, nearestToMouse, mustBeIdle) - selects units based on a category expression
UIZoomTo
INFO: UIZoomTo(units,[seconds])
UnProject
INFO: VECTOR3 UnProject(self,VECTOR2)
ValidateIPAddress
INFO: str = ValidateIPAddress(ipaddr)
ValidateUnitsList
INFO: Validate a list of units
WorldIsLoading
INFO: bool = WorldIsLoading()
WorldIsPlaying
INFO: bool = WorldIsPlaying()
_c_CreateCursor
INFO: _c_CreateCursor(luaobj,spec)
_c_CreateDecal
INFO: Create a decal in the user layer
_c_CreatePathDebugger
INFO: _c_CreatePathDebugger(luaobj,spec)
print
INFO: Print a log message
### User.CDiscoveryService
GetGameCount
INFO: CDiscoveryService.GetCount(self)
Reset
INFO: CDiscoveryService.Reset(self)
moho.discovery_service_methods
INFO:
### User.CLobby
ConnectToPeer
INFO: void CLobby.ConnectToPeer(self,address,name,uid
DebugDump
INFO: void CLobby.DebugDump()
Destroy
INFO: CLobby.Destroy(self)
DisconnectFromPeer
INFO: void CLobby.DisconnectFromPeer(self,uid
EjectPeer
INFO: void CLobby.EjectPeer(self,targetID,reason)
GetLocalPlayerID
INFO: int CLobby.GetLocalPlayerID(self)
GetLocalPlayerName
INFO: string CLobby.GetLocalPlayerName(self)
GetLocalPort
INFO: int-or-nil CLobby.GetLocalPort(self)
GetPeer
INFO: table CLobby.GetPeer(self,uid)
GetPeers
INFO: table CLobby.GetPeers(self)
HostGame
INFO: void CLobby.HostGame(self)
IsHost
INFO: bool CLobby.IsHost(self)
JoinGame
INFO: void CLobby.JoinGame(self, string-or-boxedInt32 address, string-or-nil remotePlayerName, string remotePlayerUID)
LaunchGame
INFO: void CLobby.LaunchGame(self,gameConfig)
MakeValidGameName
INFO: string CLobby.MakeValidGameName(self,origName)
MakeValidPlayerName
INFO: string CLobby.MakeValidPlayerName(self,uid,origName)
SendData
INFO: void CLobby.SendData(self,targetID,table)
moho.lobby_methods
INFO:
### User.CLuaWldUIProvider
moho.WldUIProvider_methods
INFO:
### User.CMauiBitmap
GetNumFrames
INFO: GetNumFrames()
InternalSetSolidColor
INFO: Bitmap:InternalSetSolidColor(color)
Loop
INFO: Loop(bool)
Play
INFO: Play()
SetBackwardPattern
INFO: SetBackwardPattern()
SetForwardPattern
INFO: SetForwardPattern()
SetFrame
INFO: SetFrame(int)
SetFramePattern
INFO: SetFramePattern(pattern)
SetFrameRate
INFO: SetFrameRate(float)
SetLoopPingPongPattern
INFO: SetLoopPingPongPattern()
SetNewTexture
INFO: Bitmap:SetNewTexture(filename(s), border=1)
SetPingPongPattern
INFO: SetPingPongPattern()
SetTiled
INFO: SetTiled(bool)
SetUV
INFO: Bitmap:SetUV(float u0, float v0, float u1, float v1)
ShareTextures
INFO: ShareTextures(bitmap) - allows two bitmaps to use the same textures
Stop
INFO: Stop()
UseAlphaHitTest
INFO: UseAlphaHitTest(bool)
base
INFO: derived from CMauiControl
moho.bitmap_methods
INFO:
### User.CMauiBorder
SetSolidColor
INFO: SetSolidColor(color)
base
INFO: derived from CMauiControl
moho.border_methods
INFO:
### User.CMauiControl
AcquireKeyboardFocus
INFO: AcquireKeyboardFocus(bool blocksKeyDown)
ApplyFunction
INFO: ApplyFunction(func) - applys a function to this control and all children, function will recieve the control object as the only parameter
ClearChildren
INFO: ClearChildren()
Destroy
INFO: Control:Destroy() -- destroy a control.
DisableHitTest
INFO: Control:DisableHitTest([recursive]) -- hit testing will be skipped for this control
Dump
INFO: Dump
EnableHitTest
INFO: Control:EnableHitTest([recursive]) -- hit testing will be checked for this control
GetAlpha
INFO: float GetAlpha()
GetCurrentFocusControl
INFO: GetCurrentFocusControl()
GetName
INFO: string GetName()
GetParent
INFO: Control:GetParent() -- return the parent of this control, or nil if it doesn't have one.
GetRenderPass
INFO: int GetRenderPass()
GetRootFrame
INFO: Frame GetRootFrame()
Hide
INFO: Control:Hide() -- stop rendering and hit testing the control
HitTest
INFO: bool HitTest(x, y) - given x,y coordinates, tells you if the control is under the coordinates
IsHidden
INFO: Control:IsHidden() -- determine if the control is hidden
IsHitTestDisabled
INFO: Control:IsHitTestDisabled() -- determine if hit testing is disabled
NeedsFrameUpdate
INFO: bool NeedsFrameUpdate()
SetAlpha
INFO: SetAlpha(float, children) - Set the alpha of a given control, if children is true, also sets childrens alpha
SetHidden
INFO: Control:SetHidden() -- set the hidden state of the control
SetName
INFO: SetName(string)
SetNeedsFrameUpdate
INFO: SetNeedsFrameUpdate(bool needsIt)
SetParent
INFO: Control:SetParent(newParentControl) -- change the control's parent
SetRenderPass
INFO: int SetRenderPass()
Show
INFO: Control:Show() -- start rendering and hit testing the control
moho.control_methods
INFO:
User.CMauiCursor
ResetToDefault
INFO: Cursor:ResetToDefault()
SetDefaultTexture
INFO: Cursor:SetDefaultTexture(filename, hotspotX, hotspotY)
SetNewTexture
INFO: Cursor:SetTexture(filename, hotspotX, hotspotY)
Show
INFO: Cursor:Show()
moho.cursor_methods
INFO:
### User.CMauiEdit
AcquireFocus
INFO: AcquireFocus()
ClearText
INFO: Edit:ClearText()
DisableInput
INFO: Edit:Disable()
EnableInput
INFO: Edit:EnableInput()
GetBackgroundColor
INFO: color Edit:GetBackgroundColor()
GetCaretColor
INFO: color Edit:GetCaretColor()
GetCaretPosition
INFO: int GetCaretPosition
GetFontHeight
INFO: int GetFontHeight()
GetForegroundColor
INFO: color Edit:GetForegroundColor()
GetHighlightBackgroundColor
INFO: color GetHighlightBackgroundColor()
GetHighlightForegroundColor
INFO: color GetHighlightForegroundColor()
GetMaxChars
INFO: int Edit:GetMaxChars()
GetStringAdvance
INFO: number Edit:GetAdvance(string) - get the advance of a string using the same font as the control
GetText
INFO: string Edit:GetText()
IsBackgroundVisible
INFO: bool Edit:IsBackgroundVisible()
IsCaretVisible
INFO: bool Edit:IsCaretVisible()
IsEnabled
INFO: bool Edit:IsEnabled()
SetCaretCycle
INFO: edit:SetCaretCycle(float seconds, uint32 minAlpha, uint32 maxAlpha)
SetCaretPosition
INFO: SetCaretPosition(int)
SetDropShadow
INFO: SetDropShadow(bool)
SetMaxChars
INFO: Edit:SetMaxChars(int size)
SetNewBackgroundColor
INFO: Edit:SetNewBackgroundColor(color)
SetNewCaretColor
INFO: Edit:SetNewCaretColor(color)
SetNewFont
INFO: Edit:SetNewFont(family, pointsize)
SetNewForegroundColor
INFO: Edit:SetNewForegroundColor(color)
SetNewHighlightBackgroundColor
INFO: SetNewHighlightBackgroundColor(color)
SetNewHighlightForegroundColor
INFO: SetNewHightlightForegroundColor(color)
SetText
INFO: Edit:SetText(string text)
ShowBackground
INFO: Edit:ShowBackground(bool)
ShowCaret
INFO: Edit:ShowCaret(bool)
base
INFO: derived from CMauiControl
moho.edit_methods
INFO:
### User.CMauiFrame
GetTopmostDepth
INFO: float GetTopmostDepth()
SetTargetHead
INFO: SetTargetHead(int)
base
INFO: derived from CMauiControl
moho.frame_methods
INFO:
### User.CMauiGroup
moho.group_methods
INFO:
### User.CMauiHistogram
SetXIncrement
INFO: SetXIncrement(int)
SetYIncrement
INFO: SetYIncrement(int)
base
INFO: derived from CMauiControl
moho.histogram_methods
INFO:
### User.CMauiItemList
DeleteAllItems
INFO: itemlist = ItemList:DeleteAllItems()
DeleteItem
INFO: itemlist = ItemList:DeleteItem(index)
Empty
INFO: bool ItemList:Empty()
GetItem
INFO: item = ItemList:GetItem(index)
GetItemCount
INFO: int ItemList:GetItemCount()
GetRowHeight
INFO: float ItemList:GetRowHeight()
GetSelection
INFO: index = ItemList:GetSelection()
GetStringAdvance
INFO: number ItemList:GetAdvance(string) - get the advance of a string using the same font as the control
ModifyItem
INFO: itemlist = ItemList:ModifyItem(index, string)
NeedsScrollBar
INFO: bool NeedsScrollBar() - returns true if a scrollbar is needed, else false
ScrollToBottom
INFO: ItemList:ScrollToBottom()
ScrollToTop
INFO: ItemList:ScrollToTop()
SetNewColors
INFO: ItemList:SetNewColors(foreground, background, selected_foreground, selected_background)
SetNewFont
INFO: ItemList:SetNewFont(family, pointsize) -- set the font to use in this ItemList control
SetSelection
INFO: ItemList:SetSelection(index)
ShowItem
INFO: ItemList:ShowItem(index)
ShowMouseoverItem
INFO: ShowMouseoverItem(bool) - enable or disable the showing of the mouseover item
ShowSelection
INFO: ShowSelection(bool) - enable or disable the highlighting of the selected item
base
INFO: derived from CMauiControl
moho.item_list_methods
INFO:
### User.CMauiLuaDragger
moho.dragger_methods
INFO:
### User.CMauiMesh
SetOrientation
INFO: SetOrientation(quaternion)
base
INFO: derived from CMauiControl
moho.mesh_methods
INFO:
### User.CMauiMovie
GetNumFrames
INFO: int GetNumFrames() - returns the number of frames in the movie
InternalSet
INFO: bool Movie:InternalSet(filename)
IsLoaded
INFO: IsLoaded()
Loop
INFO: Loop(bool)
Play
INFO: Play()
Stop
INFO: Stop()
base
INFO: derived from CMauiControl
moho.movie_methods
INFO:
### User.CMauiScrollbar
DoScrollPages
INFO: DoScrollPages(float)
SetNewTextures
INFO: Scrollbar:SetTextures(background, thumbMiddle, thumbTop, thumbBottom)
SetScrollable
INFO: Scrollbar:SetScrollable(scrollable) -- set the scrollable object connected to this scrollbar
base
INFO: derived from CMauiControl
moho.scrollbar_methods
INFO:
### User.CMauiText
GetText
INFO: string Text:GetText()
SetCenteredHorizontally
INFO: Text:SetCenteredHorizontally(bool)
SetCenteredVertically
INFO: Text:SetCenteredVertically(bool)
SetDropShadow
INFO: Text:SetDropShadow(bool)
SetNewClipToWidth
INFO: SetNewClipToWidth(bool) - will cause the control to only render as many charachters as fit in its width
SetNewColor
INFO: Text:SetNewColor(color)
SetNewFont
INFO: Text:SetNewFont(family, pointsize)
SetText
INFO: Text:SetText(text)
base
INFO: derived from CMauiControl
moho.text_methods
INFO:
### User.CPathDebugger
moho.PathDebugger_methods
INFO:
### User.CUIMapPreview
SetTexture
INFO: CUIMapPreview:SetTexture(texture_name)
SetTextureFromMap
INFO: CUIMapPreview:SetTextureFromMap(map_name)
base
INFO: derived from CMauiControl
moho.ui_map_preview_methods
INFO:
### User.CUIWorldMesh
GetInterpolatedAlignedBox
INFO: Vector WorldMesh:GetInterpolatedAlignedBox()
GetInterpolatedOrientedBox
INFO: Vector WorldMesh:GetInterpolatedOrientedBox()
GetInterpolatedPosition
INFO: Vector WorldMesh:GetInterpolatedPosition()
GetInterpolatedScroll
INFO: Vector WorldMesh:GetInterpolatedScroll()
GetInterpolatedSphere
INFO: Vector WorldMesh:GetInterpolatedSphere()
IsHidden
INFO: bool WorldMesh:IsHidden()
SetAuxiliaryParameter
INFO: WorldMesh:SetAuxiliaryParameter(float param)
SetColor
INFO: WorldMesh:SetColor(bool hidden)
SetFractionCompleteParameter
INFO: WorldMesh:SetFractionCompleteParameter(float param)
SetFractionHealthParameter
INFO: WorldMesh:SetFractionHealthParameter(float param)
SetHidden
INFO: WorldMesh:SetHidden(bool hidden)
SetLifetimeParameter
INFO: WorldMesh:SetLifetimeParameter(float param)
SetMesh
INFO: WorldMesh:SetMesh(meshDesc)
SetScale
INFO: WorldMesh:SetScale(vector scale)
SetStance
INFO: WorldMesh:SetStance(vector position, [quaternion orientation])
moho.world_mesh_methods
INFO:
### User.CUIWorldView
EnableResourceRendering
INFO: EnableResourceRendering(bool)
GetRightMouseButtonOrder
INFO: string moho.UIWorldView:GetRightMouseButtonOrder()
GetScreenPos
INFO: (vector2f|nil) = GetScreenPos(unit)
GetsGlobalCameraCommands
INFO: moho.UIWorldView:GetsGlobalCameraCommands(bool getsCommands)
HasHighlightCommand
INFO: bool moho.UIWorldView:HasHighlightCommand()
IsCartographic
INFO: bool IsCartographic()
IsInputLocked
INFO: IsInputLocked(camera)
IsResourceRenderingEnabled
INFO: bool IsResourceRenderingEnabled()
LockInput
INFO: LockInput(camera)
Project
INFO: VECTOR2 Project(self,VECTOR3) - given a point in world space, projects the point to control space
SetCartographic
INFO: SetCartographic(bool)
SetHighlightEnabled
INFO: SetHighlightEnabled(bool)
ShowConvertToPatrolCursor
INFO: bool moho.UIWorldView:ShowConvertToPatrolCursor()
UnlockInput
INFO: UnlockInput(camera)
ZoomScale
INFO: ZoomScale(x, y, wheelRot, wheelDelta) - cause the world to zoom based on wheel rotation event
__init
INFO: moho.UIWorldView:__init(parent_control, cameraName, depth, isMiniMap, trackCamera)
base
INFO: derived from CMauiControl
moho.UIWorldView
INFO:
### User.CameraImpl
EnableEaseInOut
INFO: Camera:EnableEaseInOut()
GetFocusPosition
INFO: Camera:GetFocusPosition()
GetMaxZoom
INFO: Camera:GetMaxZoom()
GetMinZoom
INFO: Camera:GetMinZoom()
GetTargetZoom
INFO: Camera:GetTargetZoom()
GetZoom
INFO: Camera:GetZoom()
HoldRotation
INFO: Camera:HoldRotation()
MoveTo
INFO: Camera:MoveTo(position, orientationHPR, zoom, seconds)
MoveToRegion
INFO: Camera:MoveTo(region[,seconds])
NoseCam
INFO: Camera:NoseCam(ent,pitchAdjust,zoom,seconds,transition)
Reset
INFO: Camera:Reset()
RestoreSettings
INFO: Camera:RestoreSettings(settings)
RevertRotation
INFO: Camera:RevertRotation()
SaveSettings
INFO: Camera:SaveSettings()
SetAccMode
INFO: Camera:SetAccMode(accTypeName)
SetMaxZoomMult
INFO: Camera:SetMaxZoomMult() - set zoom scale to allow zooming past or before the point where map fills control
SetTargetZoom
INFO: Camera:SetTargetZoom(zoom)
SetZoom
INFO: Camera:SetZoom(zoom,seconds)
SnapTo
INFO: Camera:SnapTo(position, orientationHPR, zoom)
Spin
INFO: Camera:Spin(headingRate[,zoomRate])
TargetEntities
INFO: Camera:TargetEntities(ents,zoom,seconds)
TrackEntities
INFO: Camera:TrackEntities(ents,zoom,seconds)
UseGameClock
INFO: Camera:UseGameClock()
UseSystemClock
INFO: Camera:UseSystemClock()
### User.ScriptedDecal
SetPosition
INFO: Set the position based on wolrd coords
SetPositionByScreen
INFO: Set the position based on screen space mouse coords
SetScale
INFO: Scale the text
SetTexture
INFO: Set the texture and add it to the decal manager
moho.userDecal_methods
INFO:
### User.UserUnit
CanAttackTarget
INFO: UserUnit:CanAttackTarget(target, rangeCheck)
GetArmy
INFO: GetArmy() -- returns the army index
GetBlueprint
INFO: blueprint = UserUnit:GetBlueprint()
GetBuildRate
INFO: GetBuildRate() -- return current unit build rate
GetCommandQueue
INFO: table GetCommandQueue() - returns table of commands
GetCreator
INFO: GetCreator() -- returns the units creator, or nil
GetCustomName
INFO: string GetCustomName() -- get the current custom name, nil if none
GetEconData
INFO: GetEconData() - returns a table of economy data
GetEntityId
INFO: Entity:GetEntityId()
GetFocus
INFO: GetFocus() -- returns the unit this unit is currently focused on, or nil
GetFootPrintSize
INFO: UserUnit:GetFootPrintSize()
GetFuelRatio
INFO: GetFuelRatio()
GetGuardedEntity
INFO: GetGuardedEntity() -- returns the units guard target, or nil
GetHealth
INFO: GetHealth() -- return current health
GetMaxHealth
INFO: GetMaxHealth() -- return max health
GetMissileInfo
INFO: table GetMissileInfo() - returns a table of the missile info for this unit
GetPosition
INFO: VECTOR3 GetPosition() - returns the current world posititon of the unit
GetSelectionSets
INFO: table GetSelectionSets() -- get table of all selection sets unit belongs to
GetShieldRatio
INFO: GetShieldRatio()
GetStat
INFO: GetStat(Name[,defaultVal])
GetUnitId
INFO: UserUnit:GetUnitId()
GetWorkProgress
INFO: GetWorkProgress()
HasSelectionSet
INFO: bool HasSelectionSet(string) -- see if a unit belongs to a given selection set
HasUnloadCommandQueuedUp
INFO: See if this unit already has an unload from transport queued up
IsAutoMode
INFO: bool = UserUnit:IsAutoMode()
IsAutoSurfaceMode
INFO: bool = UserUnit:IsAutoSurfaceMode()
IsDead
INFO: IsDead() -- return true if the unit has been destroyed
IsIdle
INFO: IsIdle() -- return true if the unit is idle
IsInCategory
INFO: bool = UserUnit:IsInCategory(category)
IsOverchargePaused
INFO: IsOverchargePaused() -- return current overcharge paused status
IsRepeatQueue
INFO: bool = UserUnit:IsRepeatQueue()
IsStunned
INFO: flag = UserUnit:IsStunned()
ProcessInfo
INFO: UserUnit:ProcessInfoPair()
RemoveSelectionSet
INFO: RemoveSelectionSet(string) -- remove a selection set name from a unit
SetCustomName
INFO: SetCustomName(string) -- Set a custom name for the unit

## Core
## Core{.tabset}
### `Core.<global>`
AITarget
INFO: Create a target object
Basename
INFO: base = Basename(fullPath,stripExtension?) -- return the last component of a path
BeginLoggingStats
INFO: Begin logging stats
BlueprintLoaderUpdateProgress
INFO:
CreatePrefetchSet
INFO: create an empty prefetch set
CurrentThread
INFO: thread=CurrentThread() -- get a handle to the running thread for later use with ResumeThread() or KillThread()
Dirname
INFO: base = Dirname(fullPath) -- return a path with trailing filename removed
DiskFindFiles
INFO: files = DiskFindFiles(directory, pattern)
returns a list of files in a directory
DiskGetFileInfo
INFO: info = DiskGetFileInfo(filename)
returns a table describing the given file, or false if the file doesn't exist.
info.IsFolder -- true if the filename refers to a folder
info.IsReadOnly -- true if file is read-only
info.SizeBytes -- size of file in bytes
info.LastWriteTime -- timestamp of last write to file
DiskToLocal
INFO: localPath = DiskToLocal(SysOrLocalPath)
Converts a system path to a local path. Leaves path alone if already local.
EndLoggingStats
INFO: EndLoggingStats(bool exit) - End logging stats and optionally exit app
EntityCategoryEmpty
INFO: Test for an empty category
EntityCategoryGetUnitList
INFO: Get a list of units blueprint names from a category
EnumColorNames
INFO: table EnumColorNames() - returns a table containing strings of all the color names
EulerToQuaternion
INFO: quaternion EulerToQuaternion(float roll, float pitch, float yaw) - converts euler angles to a quaternion
FileCollapsePath
INFO: path = FileCollapsePath(fullPath) -- collapse out any intermediate /./ or /../ directory names from a path
ForkThread
INFO: thread = ForkThread(function, ...)
Spawns a new thread running the given function with the given args.
GetCueBank
INFO: cue,bank = GetCueBank(params)
GetMovieDuration
INFO: GetMovieDuration(localFileName)
GetVersion
INFO: GetVersion() -> string
IsDestroyed
INFO: Has the c++ object been destroyed?
KillThread
INFO: KillThread(thread) -- destroy a thread started with ForkThread()
LOG
INFO: Print a log message
MATH_IRound
INFO: Round a number to the nearest integer
MATH_Lerp
INFO: MATH_Lerp(s, a, b) or MATH_Lerp(s, sMin, sMax, a, b) -> number -- linear interpolation from a (at s=0 or s=sMin) to b (at s=1 or s=sMax)
MinLerp
INFO: quaternion MinLerp(float alpha, quaternion L, quaternion R) - returns minimal lerp between L and R
MinSlerp
INFO: quaternion MinSlerp(float alpha, quaternion L, quaternion R) - returns minimal slerp between L and R
OrientFromDir
INFO: quaternion OrientFromDir(vector)
PointVector
INFO: Create a point vector(px,py,pz, vx,vy,vz)
RPCSound
INFO: RPCSound( {cue,bank,cutoff} ) - Make a sound parameters object
Rect
INFO: Create a 2d Rectangle (x0,y0,x1,y1)
RegisterBeamBlueprint
INFO: BeamBlueprint { spec } - define a beam effect
RegisterEmitterBlueprint
INFO: EmitterBlueprint { spec } - define a particle emitter
RegisterMeshBlueprint
INFO: MeshBlueprint { spec } - define mesh properties
RegisterProjectileBlueprint
INFO: ProjectileBlueprint { spec } - define a type of projectile
RegisterPropBlueprint
INFO: PropBlueprint { spec } - define a type of prop
RegisterTrailEmitterBlueprint
INFO: TrailEmitterBlueprint { spec } - define a polytrail emitter
RegisterUnitBlueprint
INFO: UnitBlueprint { spec } - define a type of unit
ResumeThread
INFO: ResumeThread(thread) -- resume a thread that had been suspended with SuspendCurrentThread(). Does nothing if the thread wasn't suspended.
SPEW
INFO: Spew to log
STR_GetTokens
INFO: table STR_GetTokens(string,delimiter)
STR_Utf8Len
INFO: int STR_Utf8Len(string) - return the number of characters in a UTF-8 string
STR_Utf8SubString
INFO: string STR_Utf8SubString(string, start, count) - return a substring from start to count
STR_itox
INFO: string STR_itox(int) - converts an integer into a hexidecimal string
STR_xtoi
INFO: int STR_xtoi(string) - converts a hexidecimal string to an integer
SecondsPerTick
INFO: SecondsPerTick() - Return how many seconds in a tick
Sound
INFO: Sound( {cue,bank,cutoff} ) - Make a sound parameters object
SpecFootprints
INFO: SpecFootprints { spec } -- define the footprint types for pathfinding
SuspendCurrentThread
INFO: SuspendCurrentThread() -- suspend this thread indefinitely. Some external event must eventually call ResumeThread() to resume it.
Trace
INFO: Trace(true) -- turns on debug tracing
Trace(false) -- turns it off again
VAdd
INFO: Addition of two vectors
VDiff
INFO: Difference of two vectors
VDist2
INFO: Distance between two 2d points (x1,y1,x2,y2)
VDist2Sq
INFO: Square of Distance between two 2d points (x1,y1,x2,y2)
VDist3
INFO: Distance between two 3d points (v1,v2)
VDist3Sq
INFO: Square of Distance between two 3d points (v1,v2)
VDot
INFO: Dot product of two vectors
VMult
INFO: Multiplication of vector with scalar
VPerpDot
INFO: Perp dot product of two vectors
Vector
INFO: Create a vector (x,y,z)
Vector2
INFO: Create a vector (x,y)
WARN
INFO: Pop up a warning dialog
WaitFor
INFO: WaitFor(event) -- suspend this thread until the event is set
doscript
INFO: doscript(script, [env]) -- run another script. The environment table, if given, will be used for the script's global variables.
exists
INFO: exists(name) -> bool -- returns true if the given resource file exists
### Core.CPrefetchSet
Update
INFO: CPrefetchSet:Update({d3d_textures=..., batch_textures=..., models=..., anims=...})
moho.CPrefetchSet
INFO:
### Core.EntityCategory
__mul
INFO: Generate a category list that is an intersection of cat1 and cat2
__sub
INFO: Generate a category list of units that is of cat1 but not of cat2
moho.EntityCategory
INFO:

