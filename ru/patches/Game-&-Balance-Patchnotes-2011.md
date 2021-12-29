---
title: Game & Balance Patchnotes 2011
description: 
published: true
date: 2021-12-29T14:53:05.765Z
tags: 
editor: markdown
dateCreated: 2021-12-25T00:05:34.584Z
---

# Complete Changelog of all chnages in 2011 {.tabset}
## 3609
### Изменения и исправления, связанные с FAF
- Отображение корректной версии патча в лобби и в файлах реплея;
- Исправлены неплравильные результаты, некорректно полученные при настройках авторазброс по командам = нет и случайно = выключено;
- Снято ограничение на лимит юнитов равный 500;
- Изменен лимит юнитов для ранговых игр на 1000.
### Новые функции
- Добавлен Sorian AI. Sorian AI теперь доступен для использования в FAF;
- Добавлена новая и улучшенная функция генерации случайных фракций, благодаря которой серафим не выпадает с 75% шансом;
- Добавлены обломки инженеров в воде;
- Добавлена Autoget фунция в качестве обязательной и включена для всех игроков. (Юниты автоматически передаются через 20 секунд после смерти, если включена передача войск.);
- Добавлены значки без технологического уровня для хранилищ энергии, чтобы их было легче найти;
- Все сооружения теперь оставляют обломки при разрушении в воде;
- Новые текстуры лобби от Moritz.
### Исправления ошибок
- fixed aeon hover sheild floating wreckage bug (fix in default units).
- fixed ACU upgrades exploit
- Fixed UEF ACU nano regen upgrade... it no longer gets overwritten by veterancy.
- Adjusted the seraphim T2 destroyer anti-torp further. It's performance is now improved.
- TML weapon on strategic missile subs now have the correct range ring
- Fixed Seraphim destroyer, UEF Atlantis and Aeon Exp Battleship wreckages. They now sink and wreck on the sea floor properly.
- Fixed a transport bug/exploit.
- fix for the UEF ACU build drones. Now the destruction of one drone does not adversely affect the other. Further, drones are     automatically re-built upon death at their original cost (160 mass, 1600 energy). Drone re-building takes 10 seconds and does not interfere with other ACU processes, such as moving, shooting or constructing.

## 3608
### Новые функции
-	New scoring system
- All hover and amphibious combat units will now leave wreckage when destroyed on or under the water.
- All ACUs and Engineers have a visual ring indicating their build radius when selected.
- Seraphim T3 Sniper now has a range ring for it's "Sniper Mode" and a visual effect to indicate when it is active.
- All T1 torpedo launchers can now shoot at targets directly beneath them.

## 3606

### Исправления ошибок
- Firing tolerance increased from 2 to 6 for Aeon T2 mercy.
- Absolver tanks now uses 3 transports slots instead of 1.
- Added janus speed reduction for when it does not have fuel.
- Corsair low fuel condition added in script.
- All T1 bombers firing tolerance increased.
- UEF, Cybran and Seraphim T2 bomber firing tolerance increased (should work better now).
- All bomber torpedo firing tolerance increased.
- Aeon T3 torpedo bomber firing tolerance increased.
- All strategic bombers firing tolerance increased.
- T1 Aeon bomber bone changed.
- T1 Aeon bomber no longer stuns walls.
- Aeon TMD dummy range category added and now vulnerable to torpedoes.
- UEF, Cybran, Aeon and Seraphim ACU regen rate for T3 engineering update now 35, rather than 15.
- Added 2 target bones to Aeon GC.
- UEF T1 spy plane turn speed improved.
- UEF Fatboy added 4 target bones.
- Cybran T1 arty medusa no longer stuns walls.
- Cybran T2 tank wagner now displays amphibious abilities.
- Cybran T4 scathis now has 90 turret pitch range.
- Cybran ML now has indirect fire overlay for bolters, direct for beam weapon.
- Cybran T2 cruiser now has projectile lifetime on main gun (proton gun).
- Aeon T3 rapid fire arty adjacency bug fixed.
- Aeon T3 optics facility adjacency bug fixed.
- UEF T3 ravager threat level changed (no air threat, now surface threat).
- UEF Percival added target bone for turret.
- UEF Shield boat has weapon ring now for shield.
- Cybran rebuild bonus for soothsayer.
- Cybran megalith main guns projectile lifetime added.
- Seraphim T4 Ahwassa firing tolerance increased.
- Seraphim T1, T2 and T3 naval factories rollout point corrected.
- Seraphim T1 and T2 mex rebuild bonus only itself.
- Seraphim T3 engineering quite health increased.
- Seraphim ACU added kill and capture sound.
- Seraphim ACU regen buffs fix, fixed blast attack stacking.
- fixed Seraphim selen scout transport animation.
- fixed Seraphim T1 artillery not firing at units within range.
- fixed Seraphim T2 bot icon.
- Fixed Seraphim T3 tank not conforming to terrain.
- fixed Seraphim T3 arty transport drop animation.
- Fixed bug allowing all seraphim structures/XP finished be seen through fow due to flash.
- fixed pause and delay in seraphim engineers building stuff (t1/t2/t3).
- Fixed seraphim T3 sam projectile not tracking targets.
- Fixed ACU build time, now x100, now 100 times harder to repair but uses 1% of the E to do so.
- Fixed seraphim air factory, now offloads engineers much faster: Compared to land factory, roughly same speed.... higher speed heading south, less speed heading laterally and north, but starts building new units sooner than land factory.
- Added fix for radar and other intel turning off during upgrades during low-mass conditions.
- Seraphim torpedo projectiles now immune to splash damage... torpedoes will not die if torpedo launcher is shot by a frigate.
- Added new calculation for bomb drops from bombers. Should be far, far more consistent now.


## 3605

### Игровой движок
- video, CPU, and sound performance optimizations.
### Лобби
-   12 Players lobby support, and infinite numbers of observers.
-   Adding big preview of the map.
-   Adding random map selection.
-   Adding share condition : The given units can disappears when you die.
-   Adding automatic formation of teams (Top/Bottom, right/left, odd/even slot)
-   Adding more units limits options.
-   Adding more colors.
-   'No Game ender' restriction changed to restrict T3 & T4 Artillery, Paragon, Novax and Yolona Oss
-   'No Nuke' Build restriction now correctly also restricts nuke carrying naval vessels, strategic
### Исправления ошибок
-   Bug fix to prevent commander upgrades to be acquired at a lower cost through cancelling.
-   Fixed restoration field upgrade and advanced restoration field upgrade to not repair the ACU.
-   All Units shooting at the Seraphim ACU now aim at the correct bones instead of the feet.
-   Pausing a Mass Extractor while in mass deficit does now correctly stop mass consumption
-   Bomb drop prediction corrected on all T1 T2 T3 bombers
-   Seraphim Battleship now correctly plays a 'nuclear launch detected' sound when launching a nuke.
-   The Novax now correctly launches its satellite when the player is at pop cap.
-   Cybran Nuke Warheads now correctly detonate at their impact altitude, and not 20 units above
-   Nano Regeneration now gives Seraphim SCUs the correct amount of hitpoints (14k instead of 45k)
-   Seraphim SCU is no longer reclaimable
-   Seraphim Battleship nuke no longer flies at very high altitude.
-   Cybran Missile health normalized so that the parent missile has 1 health and the child missiles have 1 health each as well.
-   Gifting Units to allies bugs fixed
-   Change Naval yards to be hit with torpedoes, collision box lowered by 1
-   Hoplite now uses the correct amount of transport clamps
-   Fix Fatboy, Monkeylord, Megalith and the brick being able to fire from shallow water, being unattackable from land while doing so.
-   Increase lifetime & Speed on T3 Torpedo bomber torpedoes to avoid units outrunning them.
-   Fixed a bug that caused UEF ACU to deal damage to friendly units
-   UEF T2 Cruiser now can correctly use all weapons simultaneously
-   Seraphim Advanced Regeneration Field no longer provides a health bonus. It was permanent and wasn’t removed if the unit left the aura.

### Баланс

#### Основное

##### Сооружения
- Overcharge and Energy Storage gameplay improvement.
	>	- Energy Storage now costs 250M 1200E (from 120M 2400E), stores 5000E (from 2000E)
  > - Explodes for 2000 damage in a 5 radius (from 500 damage 3 radius), and has 500 health (from 1200)
  > - Start resources go to 4000E from 5000E, ACUs now generate 20E instead of 10 to compensate.
  > - Overcharge has an increased damage radius of 2.5 (from 2), and a reload of 0.3 (from 0.2).
  > - Overcharge now costs 5000E (from 3000). Damage vs Units is unaltered, damage vs ACUs is 400 (from 100), vs buildings 800 damage  from 500)

- Factories and Engineers no longer increase Energy Storage.
- T3 Air and T3 Naval Factories changed: mass cost equals land t3 factory now.
- T3 Air Factory energy cost increased (72000). Mass cost reduced to 2750 from 3150.
- T1 Anti-Air Turret
	> - Reduced mass and energy cost by 25%
	> - Reduced build time by 25%
  > - Reduced health to 800 from 1200
- T2 Artillery Installation
	> - Reduced mass and energy cost by 25%
	> - Reduced build time by 25%
- T2 Anti-Air Flak Artillery
	> - Reduced mass and energy cost by 30%
	> - Reduced health by 30%
- T1 Mass Extractor Health reduced to 600 from 800
- T3 SAMs costs reduced significantly from 1400M 12000E to 800M 8000E
##### Воздух
- T1 Bomber cost decreased to 80M 1400E from 100M 2250E
- T1 Bomber decreased build time to 400 from 500
- T1 Air Scout : Reduced energy cost to 1300 from 1600 and Reduced build time to 17 from 20
- Cost (M, E, time) of T2 Gunships decreased by 20%
- Lowered T3 Bomber maxairspeed by 1 (18 -> 17)
- T3 Air Energy costs increased 50%, with the exception of the Solace and Air superiority Fighters, who increased +100%. The Mass cost and buildtime on all these Units stays the same.
##### Земля
- ACU Death nuke now does 2500 inner ring, 500 outer ring.
- T2 Mobile missile launchers damage increased 50%
- T3 Mobile missile launchers damage increased 100%
- Made T2 tanks slightly tougher and slower. T2 tanks now move at a 2.5 - 2.7 speed now, and have 20-25% more hitpoints in return. Cybran t2 tank got buffed more as it was too weak compared to the others. 
- Land Experimental cost increased \~20%, the cheaper ones increased more than the expensive ones (percentage wise).
- Increase striker, aurora and thaam movement speed by 0.1 (from 3 -> 3.1 or 3.3 -> 3.4)
- Landscout diversification:
	> - Uef damage = 4 (+2)
	> - Cybran cloak energy drain -5
	> - Aeon radar range +5, new health = 20 (-3)
	> - Seraphim radar range +5
- T2 Mobile Shields
	> - Mobile Shield Generator: Asylum. Shield Health set to 3800. Shield Regenrate set to 58 Now requires 105 E to operate.
	> - Shield HP reduced by 500
	> - Energy consumption reduced by 10
	> - built time increased by 10% (Aeon: 792 from 720/UEF: 660 from 600)
##### Море
- Buffed Cruiser Anti Air damage by 25%
- Decrease T3 ship costs (\~15%) and buildtime (cut in half for many).
- Decreased Frigate & t1 submarine cost by 10%
- Increase frigate anti-air dps to 15, attack boat anti-air dps to 35, and Battleship Antiair dps to 60
#### ОФЗ
- UEF Lobo t1 artillery health changed from 205 to 200
- UEF Mongoose health decreased from 900 to 650
- UEF Engineering Station Rover rebuild cost increased to 250M 2500E 750 time from 50M 500E 150 time (only applies if its shot down). Build rate decreased to 15.
- Billy reload timeout increased to avoid rapid firing through assisting
- Increase Shield ship cost by 30% from 1040M 10400E to 1300M 13000E
- Decrease T3 Air Transport costs by 30% (final E cost further adjusted by other changes)
#### Кибран
- Cybran Hoplite health decreased from 650 to 450.
- Cybran Engineering Stations: T1 cost increased to 500M 2500E from 450M 2250E. T2 build rate decreased to 25 from 30. T3 build rate decreased to 35 from 45.
- T1 Assault Bot: Mantis : Increased turret yaw speed to 90
- T2 Shield Generator: ED5 : Decreased mass cost to 1800, decreased energy cost to 26666, decreased build time to 1400, increased shield health to 15000
- Increased Cybran Deceiver (t2 mobile stealth generator) speed, acceleration and brake to match the values of other factions t2 mobile shields 
- T2 Point Defense dps increased damage to 13
- Firebeetle changed to deal 4500 damage, health lowered to 300, Firing tolerance increased to 100.
#### Эон
- Aeon T3 Engineer build rate increased to 20 from 15
- Mercy fuel increased from 70 to 110
- Restorer max airspeed reduced to 8 from 10, health reduced to 6500 from 7200 and anti ground damage per shot reduced to 24 from 32. AA weapon damage increased to 71 \* 2 from 65 \* 2. • Restorers cost 50% + 400 more energy than a Air Superiority fighter now.
- Transferred 2600 from the Harbringer’s shield to its health
- Eye of Rhianne remote viewing radius decreased from 45 to 25.
- T4 Experimental Aircraft Carrier: CZAR : -Increased health to 58000 from 48000 -Decreased crash damage from 15000 to 10000
#### Серафим
- Seraphim T3 Engineer build rate increased to 20 from 15
- T3 Submarine Hunter: Yathsou Decreased speed to 5 from 6
- T2 Point Defense dps increased +10% damage
- Seraphim cruiser direct fire Anti Air weapon and Seraphim T3 Anti Air cannon building weapon improved muzzle velocity.
### ИИ
- AI will now build firebases
- AI will now build Percivals or Rhinos
- AI can now consistently transport all valid units.
- The AI unit groups that are assigned to guard bases will no longer attack all over the map
- The AI now fires the Experimental nuke launcher more than once
- AI now sends out more than only the first land scout
- AI now can build the Megalith
- Cheating AIs now actually use their experimental units