---
title: Blueprint/Weapon
description: 
published: true
date: 2022-06-02T19:50:23.672Z
tags: modding
editor: markdown
dateCreated: 2022-06-02T17:45:53.023Z
---

## Basics
The weapons has to be defined in the UnitID_unit.bp under the category “Weapon” and in the UnitID_script.lua. Each weapon needs a projectile. Most of the weapons code is in script and can be found in the defaultweapons.lua (in lua.scd in the subdirectory \lua\modules\) under the category DefaultProjectileWeapon.

## Multiple Weapons
Each unit can have more then one weapon. The structure for multible weapons in the blueprint is:
```lua
Weapon = {
    {
        -- attributes for weapon1
    },
    { 
        -- attributes for weapon2 
    },
    {
        -- attributes for weapon3
    },
}
```

## Weapon Mechanics
A weapon consists of three parts: Turret, Rack and Muzzle.

A Turret holds Racks. A Rack holds Muzzles. Racks are controlled by the rate of fire of a weapon. Muzzles are controlled by the rack and their salvo size and delay. A weapon unpacks, charges, fires, reloads and repacks in that order. Those can be skipped if they are specified as not being part of the weapon. Unpacking/Packing happens when a weapon wants to be open during all of the firing the weapon will do in between getting a target and losing a target. Charge up happens before the racks fire. Firing a Rack runs throught it's muzzles and does the muzzle salvo there. Rack salvo size is how many times the Racks will fire before going to the reload phase.

## Camera Shake
A weapon can shake the camera (screen) when a projectile impacts. Defined could be following categories:
```lua
CameraShakeDuration = 'n' -- Time to maintain the camera shake
CameraShakeMax = 'n' -- Maximum size of the camera shake
CameraShakeMin = 'n' -- Minimum size of the camera shake
CameraShakeRadius = 'n' -- How far from the unit should the camera shake
```

## Aiming
Aiming is calculated with a combination of rack bones, muzzle bones and can have the option of beeing turreted in which case yaw, pitch and muzzle need to be defined in order for aiming to be accurate. Note that one of the most important parts of a weapon is the bone's axis orientation and alignment with muzzle, racks and turrets. All aiming is done with the assumption that bones are oriented on a right hand orientation where the index finger is the Z axis and the thumb is the Y axis. We also need to keep close attention to the alignment of all the bones used in the weapon. A weapon needs for all its aiming bones's Z axis to be coplanar and pointing along the same + or – direction.
```lua
BallisticArc = 'string' -- The ballistics arc that should be used on the projectile. Possible arcs are: 'RULEUBA_None', 'RULEUBA_LowArc' or 'RULEUBA_HighArc'
FiringRandomness = 'n' -- <How much random inaccuracy should be from the target. Randomness does not affect the ballistics calculation while aiming. It only changes the direction of the shot when the projectile is created.
FiringTolerance = 'n' -- How much misalignment can the barrel be before starting to fire. Used when you are trying to target ammo that does not require lots of accuracy due to the size of their damage radius or because the ammo does automatic targetting
MaxRadius = 'n' -- How far does the target need to be before we start firing

FireTargetLayerCapsTable = { onlayer1 = 'targetlayer1|targetlayer2', onlayer2 = 'targetlayer1|targetlayer2', }  -- FireTargetLayerCapsTable allows you to pick which layers you can target in relation to the layer that you are currently at. OnLayer is the Layer the unit is on. Targetlayers are the layers that could be targeted. There could be multible targetlayers per onplayer which have to be seperated with a “|”. Possible layers for onlayer and targetlayer are 'Seabed', 'Sub', 'Water', 'Land' and 'Air'.
```

## Damage
Each weapon should also do damage. Following subcategories define how and how much damage is dealt per hit.
```lua
CollideFriendly = true/false -- Define if the projectile collide against friendly units
DamageFriendly = true/false -- Define if the weapon will affect friendly units
Damage = 'n' -- The damage value per projectile
DamageRadius = 'n' -- The value for the blast radius
DamageType = 'string' -- The type of damage the unit will do. 'Normal' will affect all units
DoTTime = true/false -- Define if the projectile is doing damage over time (Napalm bombs from UEF T1 Attack Bomber for example)
DoTPulses = 'n' -- The number of times the damage will be dealt
```

## Economy
Some weapons require energy when used.
```lua
EnergyDrainPerSecond = 'n' -- How much energy this weapon will drain per second
EnergyRequired = 'n' -- How much energy is required to fire this weapon
```

## Turrets
When a weapon needs to be turreted it means that we are going to use a turret to rotate its rack and muzzle and its aim will be dependant on those bones so the turret needs to define which bones are used for these rotations.
```lua
TurretBoneMuzzle = 'string' -- Muzzle bone name
TurretBonePitch = 'string' -- Bone name that will determine the pitch rotation (rotation along the X axis)
TurretBonePitch = 'string' -- Bone name that will determine the yaw rotation (rotation along the Y axis)
```
An important note to keep in mind is that if a weapon has both the pitch and yaw as the same bone then we require for the muzzle to be collinear. If they are not the same bones then they only need to be coplanar.

Another important situation that you might encounter is when we get an arm like set of bones like with bots. We need to make sure that all the weapon bones are coplanar and that the Muzzle bone's z axis is collinear with the point defining the turret pitch.

Look at the following image to get a better idea of what is described here. The bone set up for the units is 100% the responsibility of the artist in charge of the mesh creation of the unit.

Dual muzzle weapons are used with units that have 2 racks working in unison. We find this kind of weapons in bots. UEF light assault bot is a good example of a unit that has this type of weapon.
```lua
Turreted = 'true/false' -- Does this have a turret?
TurretBoneDualPitch = 'string' -- The second pitch bone for a turret, used for arms on bots as weapons
TurretBoneDualMuzzle = 'string' -- The second muzzle bone for a turret, used for arms on bots as weapons
TurretBoneMuzzle = 'string' -- The bone used as the muzzle bone for turrets. This is used for aiming as where the projectile would come out.
TurretBonePitch = 'string' -- The bone used to pitch the turret.
TurretBoneYaw = 'string' -- The bone used as the yaw for the turret
TurretDualManipulators = 'true/false' -- Do we need two manipulators? Used for bots with arms. Dual manipulators are when you want one weapon but two aiming mechanisms. Like two aiming arms on one bot that share the same torso. That's really the only time you want to use it.
TurretPitch = 'n' -- The center angle for determining pitch, based off the rest pose of the art
TurretPitchRange = 'n' -- The angle +/- off the pitch that is a valid angle to turn to
TurretPitchSpeed = 'n' -- The speed at which the turret can pitch
TurretYaw = 'n' -- The center angle for determining yaw, based off the rest pose of the art
TurretYawRange = 'n' -- The angle +/- off the yaw that is a valid angle to turn to
TurretYawSpeed = 'n' -- The speed at which the turret can yaw
```
Non-Turreted weapons are mainly set when you have seeking projectiles which do not require the weapon to have a particular direction and the projectile corrects the direction. A good example of such weapon is a torpedo from a sub. In this case the barrel and muzzle would be the same bone and the “Turreted” flag would be set to false. Look at unit URS0203 as an example.

Rack
Racks hold sets of muzzles with in them. You can have multiple sets of muzzles associated to a rack bone which will allow you manipulate their behavior with common attributes.

Racks can have telescopes which mean their barrels can recoil at the barrel's telescope bone. In addition it recoils the entire rack by a small distance.

Some weapons like the big guns on Cybran Battleship have multiple sets. This unit fires each muzzle set individually and recoils the entire rack on every fire event. It also does not use a telescope but the result is very similar since we could think of the telescope bone as the rack bone.

Racks hold muzzles. A rack can be anything from a single barrel to a missile tube that has 6 missiles. They are arbitrary. The main difference is that projectiles come out of muzzles and that's all the muzzles are there for. Racks can recoil and play animations when they fire. You can change how a weapon works simply by changing the rack/muzzle setup.
```lua
RackBones = {{MuzzleBones = {<list of muzzle bones>}, RackBone = '<Bone used for rack recoil>'},} -- Here are the MuzzleBones and the RackBone defined. There could be multible Muzzlebones and also multible sets of RackBones'.
```
Example for the UEF T1 Light Assault Bot with one barrel each on two arms:
```lua
RackBones = {
    {
        MuzzleBones = {
            'Arm_Right_Muzzle',
        },
        RackBone = 'Arm_Right_B02',
    },
    {
        MuzzleBones = {
            'Arm_Left_Muzzle',
        },
        RackBone = 'Arm_Left_B02',
    },
},
```

Example for the UEF T1 Medium Tank with one barrel on one turret:
```lua
RackBones = {
    {
        MuzzleBones = {
            'Turret_Muzzle',
        },
        RackBone = 'Turret_Barrel',
    },
},
```
Example for the UEF T2 Heavy Tank with two barrels on one turret:
```lua
RackBones = {
    {
        MuzzleBones = {
        'Turret_Muzzle_01',
        'Turret_Muzzle_02',
        },
        RackBone = 'Turret_Barrel',
    },
},
```
Example for telescoping recoil:
```lua
RackBones = {
    {
        MuzzleBones = {
            'Muzzle1',
            'Muzzle2',
        },
        RackBone = 'Barrel',
        TelescopeBone = 'Telescope', #of course, this bone doesn't have to be named like that
    },
},
```

```lua
TelescopeBone = '?' -- Bone used for telescoping barrel recoil
TelescopeRecoilDistance = '?' -- Distance the telescoping part of the barrel will recoil
HideMuzzle = 'true/false' -- Indicates that the muzzle bones will be hidden when fired and turned back on before muzzle recharge and during idle. Useful for weapons that show the projectile in the art then fire it off. (Mobile missile launchers)
RackRecoilDistance = 'n' -- Distance racks will recoil, Z axis, local coords.
RackSalvoChargeTime = 'n' -- Time before the racks start firing
RackSalvoFiresAfterCharge = 'true/false' -- Does the racks immediately fire when charge is done or wait until next OnFire event?
RackSlavedToTurret = 'true/false' -- All rack bones are slaved to the turret pitch bone?
RackFireTogether = 'true/false' -- Do all racks fire simultaneously?
RateOfFire = 'n' -- Rack firings per second. You can use decimals for fire rates that are longer than a second
RackReloadTimeout = 'n' -- Seconds before the weapon will reload when it didn't go through all its racks
```
If you make one rack with 6 muzzles and a Rack Salvo Size of 1, it'll fire all 6 before reloading. If you make two racks with 3 muzzles each, it'll fire 3 then have to reload, and then fire the next 3 in the next firing cycle. And so on. By simply changing what the code thinks is muzzles and racks you can get different firing behaviors.

## Muzzle
The muzzle is the location (bone) of a piece of art that determines where a projectile or a beam comes out of the weapon. We can have multiple muzzles per rack.
```lua
MuzzleSalvoSize = 'n' -- Number of times the muzzle will fire during a rack firing
MuzzleSalvoDelay = 'n' -- Time in between muzzles firing. Setting to 0 = all muzzle fire together
MuzzleChargeDelay = 'n' -- The time that the muzzle will wait between playing the FxMuzzleFlash table and the creation of the projectile. Note: This will delay the firing of the projectile. So if you set the rate of fire to fire quickly, this will throttle it.
MuzzleVelocity = 'n' -- Speed in which the projectile comes out of the muzzle. This speed is used in the ballistics calculations. If you weapon doesn't fire at its max radius, this may be too low.
MuzzleVelocityReduceDistance – 'n' -- MuzzleVelocityReduceDistance was put there so weapons that have a high muzzle velocity because they have a huge range, like an artillery piece, wouldn't point right at something that's close, it'll slow down it's shot and still have a nice arc to it
```

## Salvo
Salvo is the ammo used by the rack. We need to define how they interact.
```lua
RackSalvoReloadTime = 'n' -- Time the racks will reload before starting its next charge/salve cycle
RackSalvoSize = 'n' -- Number of times the racks will fire before its reload period
ProjectileId = 'string' -- Blueprint of the projectile to fire
ProjectileLifetime = 'n' -- How long the projectile lives
```

## Targeting
Target priorities could be set, also exlusive categories or disallowed categories. Also a tracking radius could be set, which effects that units start tracking a unit even before it can open fire (when it is out of the MaxRadius).
```lua
TargetPriorities = {'<category string1>', '<category string2>',} -- Table of category strings that define the targetting order of this weapon. First category is the one with the highest priority.
TargetRestrictDisallow = '<category string>' -- The categories that we will not allow to target.
TargetRestrictOnlyAllow = '<category string>' -- Exclusive categories that we will allow to target.
TargetCheckInterval = 'n' -- Interval of time between looking for a target. When this is set too fast the unit may change targets too fast before the targets get destroyed. Is it too slow the unit may idle after killing a target before it is looking for a new target.
TrackingRadius = 'n' -- The radius that the weapon start tracking the target. This does not mean that the weapon will fire. The weapon will only fire when a target enters the maxradius.
HeadingArcCenter – '?' -- Controls what the weapon is allowed to target in reference to the heading of the unit.
HeadingArcRange – '?' -- Controls what the weapon is allowed to target in reference to the arc center, this is degrees on either side.
```

Category strings are strings that get converted to unit categories. They work exactly like the strings used for buildable categories. ie: You want TECH1 and MOBILE, the string would be 'TECH1 MOBILE'. If you wanted TECH1 and not MOBILE, it'd be 'TECH1 -MOBILE' and if you want LAND and AIR then you would do 'LAND, AIR' where the ',' will be the union token.

Examples for heading arc categories: I want a weapon to only target things in the front half of a unit: HeadingArcCenter = 0, HeadingArcRange = 90

I want a weapon that only targets things on the right side of the unit but have a 45 degree overlap to the left side: HeadingArcCenter = -90, HeadingArcRange = 135 (Basically, it won't target anything perpendicular to the left side +/- 45 degrees.

The heading arc stuff is based on the unit direction, not the default pose of the weapon. This is very handy for getting weapons on different sides of the unit to target different things. The Fatboy uses this extensively.

## Beam Weapons
```lua
BeamCollisionDelay = 'n' -- Every n + 0.1 seconds, this beam will collide and do damage
BeamLifetime = 'n' -- The amount of time the beam exists.
WeaponRepackTimeout = 'n' -- Amount of time after the unit has lost its target that it will pack back up
```
because by default, a beam with 0 BeamCollisionDelay hits once every 0.1 seconds (to keep the beam from destroying everything instantly), the "True" collision delay is actually 0.1 seconds longer the "BeamCollisionDelay" variable.

## Death Weapons
Some units explode and deal damage when they get killed (not destroyed). You can add a death weapon the following way.
```lua
Weapon = {
    {
    Damage = <Damage Amount>,
    DamageFriendly = <false/true>,
    DamageType = 'Normal',
    DamageRadius = <Blast Radius>,
    DummyWeapon = <true/false>,
    Label = 'DeathWeapon',
    },
}

DummyWeapon = 'true/false' -- This instructs the engine not to create a C++ weapon object that is usually linked with the script object. This is for purely script driven weapons (like death weapons).
Label – 'string' -- Label is linking the blueprints (unitid_unit.bp) weapon information with the script (unitid_script.lua) weapon information. For example: blueprint: Weapon { Label = 'FrontTurret01', } script: Weapons = { FrontTurret01 = Class(TDFGaussCannonWeapon) {} }. If the Label doeas not match the weapon will not be workable.
```
For Death Weapons Label has to be 'DeathWeapon' or ‘DeathImpact’ for air units crashing and dealing damage on impact. Weapon fires at the spot of the unit. Fires when the unit is killed not destroyed.

## Audio
Weapons also uses audio for firing, impacting, etc. Note: This category is a big stub.

## Buffs
Informations about the buff added to the units weapon when reaching a specific veteran level. Note: Buffs are going to be changed drastically.

## Other Commands
Here are some commands where it is not clear to which category they should be added
```lua
AutoInitiateAttackCommand – '?' -- If the unit has no issued commands and has a weapon that has AutoInitiateAttackCommand set, then if it finds a suitable target it will issue an attack command to go after the target.
DisplayName – 'string' -- Just for debugging. "dbg weapons" on the console shows the weapon names. Also some errors that we detect in script code will print the name of the weapon to help track down the issue.
NeedPrep – 'true/false' -- If NeedProp is true then whenever the unit aquires a new target and is ready to attack it it will first run the OnGotTarget script on the weapon.
AimsStraightOnDisable = 'true/false', -- This weapon will aim straight ahead when disabled.
AlwaysRecheckTarget = 'true/false', -- always recheck for better target regardless of whether you already have one or not.
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
FiringRandomnessWhileMoving = 'n', -- Different value of firing randomness, used only when moving; can be used to simulate inaccuracy while moving
NoPause = 'true/false', -- ?
```

## Deprecated Attributes
Changing/removing these categories will do nothing to the weapon.

`WeaponCategory`
`MetaImpactAmount`
`MetaImpactRadius`
`ProjectilesPerOnFire`

## What can't be done via only data
You can't take a beam weapon and make it a projectile weapon. If you want to do something like that you need to instantiate that type of weapon from the script file and make the necessary adjustments on the blueprint.