---
title: Adjacency-Bonus
description: 
published: true
date: 2021-10-13T06:35:26.628Z
tags: 
editor: markdown
dateCreated: 2021-08-31T09:41:57.317Z
---

![](Adjacency.jpg "fig:Adjacency.jpg") The Adjacency Bonus is a [game mechanic](Learning_SupCom#Tutorial_Videos "wikilink") in Supreme Commander which gives discounts and production bonuses to structures positioned next to each other. The nature of the bonus depends on both of the structures, and can be very useful. Mass or energy can saved or produced, leading to a total of 4 possible bonuses.

## General

![](Adjacency_Diagram.png "fig:Adjacency_Diagram.png") To have an adjacency bonus, there must be two structures placed next to each other; one giving the bonus and one receiving it.

-   Any structure which produces a resource is a bonus giver.
-   Any structure consuming a resource is a bonus receiver, including other bonus givers (upgrading mass extractors)
-   Additionally, Storages are bonus givers to resource producing buildings.
-   Doubling the number of adjacent bonus givers next to a structure doubles the adjacency bonus on that structure.

The Bonus amount is dependent on the number of bonus givers which can fit around a bonus receiver. (minimum:4 maximum:16) This means that the larger a bonus receiver the more bonus givers must be next to it to give the same bonus.
Examples:

- A factory surrounded by 16 T1 power generators receives the same discount as a radar surrounded by 4 T1 power generators.
- A mass extractor surrounded by 4 storages receives the same percentage production bonus as a T3 mass fabricator surrounded by 12 mass storages.

## Consumption Bonus

A structure which produces a resource gives a discount to all structures next to it which consume that resource. It should be noted that only structures receive this bonus, **not any engineers or engineering stations assisting them**.

### <img src="Mass_Icon.png" title="fig:Mass_Icon.png" width="30" alt="Mass_Icon.png" /> Mass

The values in this table are given for **one** mass producing structure next to a 4x4 building; more mass producing structures would increase the discount. The typical discount value is to give you an idea of what you would most commonly see in game, and should not be used for calculations.

| Mass Producing Structures                                                                                                                      | Discount Percentage | Typical Discount value                                                  | Comments                                                                                                                                            |
|------------------------------------------------------------------------------------------------------------------------------------------------|---------------------|-------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------|
| <img src="UEF_T1_Mass_Extractor.png" title="fig:UEF_T1_Mass_Extractor.png" width="40" alt="UEF_T1_Mass_Extractor.png" /> T1 Mass Extractor     | 7.5%                | 0.3-1 ![<File:Mass_Icon.png>](Mass_Icon.png "fig:File:Mass_Icon.png")   | Useful next to T1 Land Factories, if you're not going to eco much.                                                                                  |
| <img src="UEF_T2_Mass_Extractor.png" title="fig:UEF_T2_Mass_Extractor.png" width="40" alt="UEF_T2_Mass_Extractor.png" /> T2 Mass Extractor     | 10%                 | 1-2 ![<File:Mass_Icon.png>](Mass_Icon.png "fig:File:Mass_Icon.png")     | Useful next to T2 Land Factories.                                                                                                                   |
| <img src="UEF_T3_Mass_Extractor.png" title="fig:UEF_T3_Mass_Extractor.png" width="40" alt="UEF_T3_Mass_Extractor.png" /> T3 Mass Extractor     | 12.5%               | 2-4 ![<File:Mass_Icon.png>](Mass_Icon.png "fig:File:Mass_Icon.png")     | Useful next to T3 Land Factories, Note: Quantum gateways only receive 10%.                                                                          |
| <img src="UEF_T2_Mass_Fabricator.png" title="fig:UEF_T2_Mass_Fabricator.png" width="40" alt="UEF_T2_Mass_Fabricator.png" /> T2 Mass Fabricator | 1.25%               | 0.1-0.3 ![<File:Mass_Icon.png>](Mass_Icon.png "fig:File:Mass_Icon.png") | Not Very Useful. Note: If Both T2 T3 Fabricators are turned off bonus doesn't apply.                                                                |
| <img src="UEF_T3_Mass_Fabricator.png" title="fig:UEF_T3_Mass_Fabricator.png" width="40" alt="UEF_T3_Mass_Fabricator.png" /> T3 Mass Fabricator | 20%                 | 2-4 ![<File:Mass_Icon.png>](Mass_Icon.png "fig:File:Mass_Icon.png")     | Useful next to T3 factories and high mass consuming structures (20/s or more). Note: Quantum gateways receive only 3.75%. Nukes receive only 12.5%. |

Buildings which give mass discount bonuses

### <img src="Energy_Icon.png" title="fig:Energy_Icon.png" width="30" alt="Energy_Icon.png" /> Energy

The percentage discount value depends on how much of the structure in question is surrounded by power generators - as structures can be of different sizes, different numbers of pgens fit around them. This means that a factory that is 50% surrounded with 8 T1 pgens will receive the same bonus as, a radar surrounded by 2 T1 pgens - 12.5% for both. In this table the discount percentages are shown for a **fully surrounded** structure.

<table>
<caption>Buildings which give Energy discount bonuses</caption>
<thead>
<tr class="header">
<th><p>Energy Producing Structures</p>
<dl>
<dt></dt>
<dd><dl>
<dt></dt>
<dd>
</dd>
</dl>
</dd>
</dl></th>
<th><p>Discount Percentage</p></th>
<th><p>Typical Discount value</p></th>
<th><p>Comments</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><img src="UEF_T1_Power_Generator.png" title="fig:UEF_T1_Power_Generator.png" width="40" alt="UEF_T1_Power_Generator.png" /> T1 Power Generator</p></td>
<td><p>25%</p></td>
<td><p>1-5 <img src="Energy_Icon.png" title="fig:File:Energy_Icon.png" alt="File:Energy_Icon.png" /></p></td>
<td><p>Useful next to radar, air factories, not great next to land factories, but should still be used.</p></td>
</tr>
<tr class="even">
<td><p><img src="UEF_T1_Hydrocarbon_Power_Plant.png" title="fig:UEF_T1_Hydrocarbon_Power_Plant.png" width="40" alt="UEF_T1_Hydrocarbon_Power_Plant.png" /> T1 Hydrocarbon Power Plant</p></td>
<td><p>12.5%</p></td>
<td><p>10-50 <img src="Energy_Icon.png" title="fig:File:Energy_Icon.png" alt="File:Energy_Icon.png" /></p></td>
<td><p><strong>% value for ONE Hydro shown.</strong> Useful next to T1/2 air Factories, generally useful.</p></td>
</tr>
<tr class="odd">
<td><p><img src="UEF_Power_Generator.png" title="fig:UEF_Power_Generator.png" width="40" alt="UEF_Power_Generator.png" /> T2 Power Generator</p></td>
<td><p>50%</p></td>
<td><p>20-100 <img src="Energy_Icon.png" title="fig:File:Energy_Icon.png" alt="File:Energy_Icon.png" /></p></td>
<td><p>Useful next to T2 air Factories.</p></td>
</tr>
<tr class="even">
<td><p><img src="UEF_T3_Power_Generator.png" title="fig:UEF_T3_Power_Generator.png" width="40" alt="UEF_T3_Power_Generator.png" /> T3 Power Generator</p></td>
<td><p>75%</p></td>
<td><p>200-750 <img src="Energy_Icon.png" title="fig:File:Energy_Icon.png" alt="File:Energy_Icon.png" /></p></td>
<td><p>Very Useful next to T3 air Factories.</p></td>
</tr>
<tr class="odd">
<td><p><img src="A_Paragon.PNG" title="fig:A_Paragon.PNG" width="40" alt="A_Paragon.PNG" /> T4 Paragon</p></td>
<td><p>0%</p></td>
<td><p>0 <img src="Energy_Icon.png" title="fig:File:Energy_Icon.png" alt="File:Energy_Icon.png" /></p></td>
<td><p>Useless - better to shield it.</p></td>
</tr>
</tbody>
</table>

Buildings which give Energy discount bonuses

It should be noted that mass extractors consume energy to generate mass, but T1 pgens should only be used for adjacency when the extractor is upgrading from T1 to T2 very early in the game, to save some energy while upgrading.

## Production Bonus

Any structure which produces a resource, when placed next to a storage of that resource, will produce a bonus percentage of that resource. This is most commonly seen when mass extractor are surrounded by storages to increase their mass income. 

-   Bonus is 12,5% per fully surrounded side by storages.
    -   Maximum is 50% bonus income for fully surrounded building by
        storages.

### <img src="Mass_Icon.png" title="fig:Mass_Icon.png" width="30" alt="Mass_Icon.png" /> Mass

| Mass Producing Structures                                                                                                                      | Production Bonus for one storage                                       | Production Bonus for all storages                                     | Comments                                                                                                    |
|------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------|-----------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------|
| <img src="UEF_T1_Mass_Extractor.png" title="fig:UEF_T1_Mass_Extractor.png" width="40" alt="UEF_T1_Mass_Extractor.png" /> T1 Mass Extractor     | +0.25 ![<File:Mass_Icon.png>](Mass_Icon.png "fig:File:Mass_Icon.png")  | +1 ![<File:Mass_Icon.png>](Mass_Icon.png "fig:File:Mass_Icon.png")    | Not very useful. Also not obvious due to how the game rounds the displayed values, same for t2 fabricators. |
| <img src="UEF_T2_Mass_Extractor.png" title="fig:UEF_T2_Mass_Extractor.png" width="40" alt="UEF_T2_Mass_Extractor.png" /> T2 Mass Extractor     | +0.75 ![<File:Mass_Icon.png>](Mass_Icon.png "fig:File:Mass_Icon.png")  | +3 ![<File:Mass_Icon.png>](Mass_Icon.png "fig:File:Mass_Icon.png")    | Useful.                                                                                                     |
| <img src="UEF_T3_Mass_Extractor.png" title="fig:UEF_T3_Mass_Extractor.png" width="40" alt="UEF_T3_Mass_Extractor.png" /> T3 Mass Extractor     | +2.25 ![<File:Mass_Icon.png>](Mass_Icon.png "fig:File:Mass_Icon.png")  | +9 ![<File:Mass_Icon.png>](Mass_Icon.png "fig:File:Mass_Icon.png")    | Very Useful.                                                                                                |
| <img src="UEF_T2_Mass_Fabricator.png" title="fig:UEF_T2_Mass_Fabricator.png" width="40" alt="UEF_T2_Mass_Fabricator.png" /> T2 Mass Fabricator | +0.125 ![<File:Mass_Icon.png>](Mass_Icon.png "fig:File:Mass_Icon.png") | +0.5 ![<File:Mass_Icon.png>](Mass_Icon.png "fig:File:Mass_Icon.png")  | Not Very Useful, unless the storages are next to an extractor.                                              |
| <img src="UEF_T3_Mass_Fabricator.png" title="fig:UEF_T3_Mass_Fabricator.png" width="40" alt="UEF_T3_Mass_Fabricator.png" /> T3 Mass Fabricator | +0.48 ![<File:Mass_Icon.png>](Mass_Icon.png "fig:File:Mass_Icon.png")  | +5.76 ![<File:Mass_Icon.png>](Mass_Icon.png "fig:File:Mass_Icon.png") | Not Very Useful - better to place near t3 Pgens, same for t2 mass fabs.                                     |

Buildings which are affected by mass storages

### <img src="Energy_Icon.png" title="fig:Energy_Icon.png" width="30" alt="Energy_Icon.png" /> Energy

| Energy Producing Structures                                                                                                                                                    | Production Bonus for one storage                                              | Production Bonus for all storages                                           | Comments                                                   |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------|-----------------------------------------------------------------------------|------------------------------------------------------------|
| <img src="UEF_T1_Power_Generator.png" title="fig:UEF_T1_Power_Generator.png" width="40" alt="UEF_T1_Power_Generator.png" /> T1 Power Generator                                 | +2.5 ![<File:Energy_Icon.png>](Energy_Icon.png "fig:File:Energy_Icon.png")    | +10 ![<File:Energy_Icon.png>](Energy_Icon.png "fig:File:Energy_Icon.png")   | Almost useless due to the explosion when the storage dies. |
| <img src="UEF_T1_Hydrocarbon_Power_Plant.png" title="fig:UEF_T1_Hydrocarbon_Power_Plant.png" width="40" alt="UEF_T1_Hydrocarbon_Power_Plant.png" /> T1 Hydrocarbon Power Plant | +4 ![<File:Energy_Icon.png>](Energy_Icon.png "fig:File:Energy_Icon.png")      | +50 ![<File:Energy_Icon.png>](Energy_Icon.png "fig:File:Energy_Icon.png")   | Almost useless due to the explosion when the storage dies. |
| <img src="UEF_Power_Generator.png" title="fig:UEF_Power_Generator.png" width="40" alt="UEF_Power_Generator.png" /> T2 Power Generator                                          | +27.78 ![<File:Energy_Icon.png>](Energy_Icon.png "fig:File:Energy_Icon.png")  | +250 ![<File:Energy_Icon.png>](Energy_Icon.png "fig:File:Energy_Icon.png")  | Almost useless due to the explosion when the storage dies. |
| <img src="UEF_T3_Power_Generator.png" title="fig:UEF_T3_Power_Generator.png" width="40" alt="UEF_T3_Power_Generator.png" /> T3 Power Generator                                 | +78.125 ![<File:Energy_Icon.png>](Energy_Icon.png "fig:File:Energy_Icon.png") | +1250 ![<File:Energy_Icon.png>](Energy_Icon.png "fig:File:Energy_Icon.png") | Almost useless due to the explosion when the storage dies. |

Buildings which are affected by Energy storages

Note: Adjacency Bonus should be used well-considered. Players with little experience tend to surround hydrocarbon power plants with energy storages to get 50% more energy, or similar things. The bonus you want to have, can quickly turn into an economic disadvantage if you try to profit that way. Keep in mind the costs of 12 energy storages which amount to 14400 energy and 3000 mass. It would take 5 minutes until you profit from the energy bonus. The mass covers about the costs of a T3 power generator which would produce 2500 energy instead of 50.

## Weapon Bonuses

Placing Power Generators next to energy-consuming weapons will reduce the reload time of the weapon, the duration of energy consumption as a result, and the energy consumption itself. All static artilleries benefit from the rate of fire bonus and energy drain reduction. UEF T3 Point Defense is an exception and only gains a reduction in energy drain.

The values in the following tables are given when a unit is completely surrounded by a specific power generator.

### Rate Of Fire Bonus

When placed next to power generators, static artillery units gain a rate of fire bonus which can be very significant, especially when considering that a 60% reload time can be achieved, and how much cheaper 4 T3 power generators are than a T3 artillery installation. The reduction of a reload time can be calculated with the following scheme if a unit is fully surrounded with the same type of power generators:

-   10% discount for T1 power generators.
-   20% discount for T2 power generators/hydrocarbon power plant.
-   40% discount for T3 Power generators.

The Aeon T3 Rapid-fire Artillery can achieve the maximum possible reload time discount (42%) because you can place a T1 power generator on each side in addition to a T3 power generator.

This table shows all possible time values:

| Artillery Unit                                                                                                                 | T1 Power Generator | Hydrocarbon Power plant | T2 Power Generator | T3 Power Generator | Comments                                                                                                            |
|--------------------------------------------------------------------------------------------------------------------------------|--------------------|-------------------------|--------------------|--------------------|---------------------------------------------------------------------------------------------------------------------|
| <img src="UEF_T2_Arty.png" title="fig:UEF_T2_Arty.png" width="40" alt="UEF_T2_Arty.png" /> T2 Artillery                        | 2s                 | 5s                      | 5s                 | 8s                 | T1 pgens useful, especially with multiple artillery structures.                                                     |
| <img src="UEF_T3_Static_Arty.png" title="fig:UEF_T3_Static_Arty.png" width="40" alt="UEF_T3_Static_Arty.png" /> T3 Artillery   | 1s                 | 2.5s                    | 2.5s               | 4s                 | Very useful with T3 pgens, or any pgens. Note: Aeon artillery has twice the reload time, and so twice the discount. |
| <img src="A_T3_Rapid_Arty.PNG" title="fig:A_T3_Rapid_Arty.PNG" width="40" alt="A_T3_Rapid_Arty.PNG" /> T3 Rapid-fire Artillery | 0.31s              | 0.775s                  | 0.775s             | 1.24s              | The size allows you to surround it with a T3 and T1 pgen. Reload time discount: 1.302s.                             |
| <img src="UEF_T4_Static_Arty.png" title="fig:UEF_T4_Static_Arty.png" width="40" alt="UEF_T4_Static_Arty.png" /> T4 Artillery   | 0.8s               | 2s                      | 2s                 | 3.2s               | Very useful with T3 pgens, or any pgens.                                                                            |
| <img src="UEF_T3_PD.png" title="fig:UEF_T3_PD.png" width="40" alt="UEF_T3_PD.png" /> T3 Ravager                                | 0s                 | 0s                      | 0s                 | 0s                 | Only profits from energy consumption reduction (see table below). Quite useless.                                    |

Reload Time discount on Artillery structures

### Energy Consumption Reduction

The rate of fire bonus reduces the time structures consume energy, but will also increase the frequency of energy consumption as a result of the increased fire rate. But in addition to that, powergenerators give a general discount on energy consumption to static artilleries. Making decisions around this behaviour is not recommended as the energy reduction is very low compared to the resources invested. This table is mostly to provide you information of how it works.

| Energy Producing Structures                                                                                                                                                    | Discount Percentage | Typical Discount value                                                        | Comments                                                                     |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------|-------------------------------------------------------------------------------|------------------------------------------------------------------------------|
| <img src="UEF_T1_Power_Generator.png" title="fig:UEF_T1_Power_Generator.png" width="40" alt="UEF_T1_Power_Generator.png" /> T1 Power Generator                                 | 10%                 | 15-750 ![<File:Energy_Icon.png>](Energy_Icon.png "fig:File:Energy_Icon.png")  | Useful next to all static artillery, especially T2, when safety is important |
| <img src="UEF_T1_Hydrocarbon_Power_Plant.png" title="fig:UEF_T1_Hydrocarbon_Power_Plant.png" width="40" alt="UEF_T1_Hydrocarbon_Power_Plant.png" /> T1 Hydrocarbon Power Plant | 20%                 | 30-1500 ![<File:Energy_Icon.png>](Energy_Icon.png "fig:File:Energy_Icon.png") | Useful next to T2/T3 static artillery                                        |
| <img src="UEF_Power_Generator.png" title="fig:UEF_Power_Generator.png" width="40" alt="UEF_Power_Generator.png" /> T2 Power Generator                                          | 20%                 | 30-1500 ![<File:Energy_Icon.png>](Energy_Icon.png "fig:File:Energy_Icon.png") | Useful next to T2/T3 static artillery                                        |
| <img src="UEF_T3_Power_Generator.png" title="fig:UEF_T3_Power_Generator.png" width="40" alt="UEF_T3_Power_Generator.png" /> T3 Power Generator                                 | 30%                 | 60-3000 ![<File:Energy_Icon.png>](Energy_Icon.png "fig:File:Energy_Icon.png") | Useful next to T3/T4 static artillery                                        |

Buildings which give Energy discount bonuses