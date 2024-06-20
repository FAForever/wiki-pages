---
title: Rating-System
description: 
published: true
date: 2024-06-20T13:15:23.494Z
tags: 
editor: markdown
dateCreated: 2021-08-31T09:44:47.976Z
---

# **Why choose Trueskill over Elo ?**

The Elo rating system has some weaknesses that can make it unsuited to Forged Alliance. For example, ELO is unable to rate anything but 1 vs 1 matches.

## Team Games

ELO is only capable of rating even team games, such as 2v2, it cannot properly weigh a Free For All or a team game with more than two sides. Each team will be considered as a single player, so that the leaderboard will show a result for each pair of players, for every pair that ever exists.

TrueSkill however, can handle any match-up. Teams are the weighted sum of the players inside, and results are correctly calculated from the team results to the players in the teams. It can easily handle FFA, 2vs2vs2 and so on.

## Draws

The ELO system handles draws differently from Trueskill. For Elo, a draw is simply a half-win half-lost game.

TrueSkill measures a drawn outcome very differently Each map has a draw percentage based on all of the outcomes of games played on that map. TrueSkill considers draws as a meaningful outcome: You were matched with an equally skilled opponent.

But Let's consider two players with the same skill.

On a map where draws are more unlikely, a draw game will lead to no difference in skill, but the system is learning the player better (actual skills are accurate - see below). That result will also increase the overall draw probability for that map.

However, on a map like "Winter Duel" for example, where draws are a more likely outcome a draw is expected as a result, so the skill won't move, but the system doesn't know the players better, so that game is meaningless compared the "normal" map case. That result will also increase the draw probability on Winter Duel.

Now let's say that player 1 win.

On the "normal" map, the player will gain points, for example, 's sake say a gain +4 points, and the loser receives a penalty of -4. That result will decrease the draw probability on that map. 

Now, on the Winter Duel map a draw was a more likely outcome, the fact that player 1 wow means that he is significantly better than his opponent. As a result, his rating will be revised upwards, so instead of +4, he will gain +6, and the loser -6 for example. That result will then decrease the draw probability on Winter Duel. 

## Inflation

Elo systems can tend to inflate over time. Because it's only comparing 2 players' ratings to determine a new rating, a better player who plays often will gain more and more points over time. For example, at the beginning of the GPGnet ranked ladder the top 10 players were rated around 1900. Presently the highest-ranked player is around 2700. Does that mean that their skill is increasing? Maybe. But not that much. The rating increase because, like all good top-tier players, they play often. And as they are good, they win games, and gain points, increasing the rating over time.

To combat inflation, the ELO system has a "K-Factor", limiting the maximum points a player win or loss per game. GPGNet used a K-Factor of 30. In the Chess leaderboard, the K factor depends on the rating of the player (2400+ players got a K-Factor of 16 whereas a newer player got 32). That's arbitrary, not accurate and only artificially decreases the inflation problem. \[citation needed\]

True skill is less susceptible to inflation. When you start a game, TrueSkill calculates the possible -and probable- outcome of the game: it estimates what are your chances of winning.

Let's say it predicts that you will win that game.

If you win the game, as it was the expected outcome, you will gain points depending on the "chances of ranking" factor (itself depending on the difference in skill between players, and the outcome probability). If you lose the game, as an unexpected result, you will lose more points. On paper, it sounds a lot like Elo, but the algorithms behind are more evolved, and once you reach your real rating, unless you play badly or improve a lot, you will stay at that rank.

![mostrecentfoosballtrueskill.png](/images/mostrecentfoosballtrueskill.png)

This graph represents a true skill rating for a selection of football teams. As you can see, team 1 is the best, and their rank stays stable. Team 5 had a bad start (you lost your first games), and were badly rated. Over time, TrueSkill manages to correct that and find a stable skill. Team 2 is the most interesting case: It's a new team, really good. At the start, it was rated way under their real skill. You can see how fast the system was able to determine their correct rating. One of the advantages of Trueskill is that it can determine your correct rating very quickly.

## TrueSkill advantages

TrueSkill can rate ANY game. That's why ANY custom game or ranked will contribute to your skill rating. TrueSKill can lower the impact of your result: A FFA is less meaningful than a 1v1, so the outcome of an FFA will contribute less.

# **How Trueskill works**

### Your rating and you!

The number you see in the leaderboards is an *approximation* of your real rating.

What this means is that two players with the same rating can in reality perform at different skill levels. At this time we are displaying the approximation - you can see the actual distribution by right-clicking on your name in the player list and selecting *View Player Statistics.* 

In reality, your rating is a [Gaussian bell curve](http://en.wikipedia.org/wiki/Normal_distribution).

It's comprised of two values: Your mean and your deviation.

It sounds complicated (which is why we haven't shown them to you yet) but it's easy to understand.

Don't be intimidated by the graphs, the concept is very simple.

The **mean** represents your maximum skill/rating. The system thinks that it cannot be higher than that. True skill believes at your current skill level, you can't perform at a higher level, but possibly also at a lower one. Technically speaking, for a real-valued random variable X, the mean is the expectation of X. For more information on the maths behind this, visit [Wikipedia](http://en.wikipedia.org/wiki/Mean).

The **standard deviation** is the "uncertainty" factor. The bigger it is, the higher your possible real rating is. Standard deviation is a widely used measure of variability or diversity used in statistics and probability theory. It shows how much variation or "dispersion" exists from the average (mean, or expected value) 

The mean is often quoted along with the standard deviation: the mean describes the central location of the data, and the standard deviation describes the spread.

Let's take the value of a new player. By default, you have 1500 in mean and 500 in deviation. 1500 is the **average level**.

![1ula41330944573.png](/images/1ula41330944573.png)

When you join, the system predicts you will perform on average (1500). However, as you can see on the curve, the probability that you will perform at either 1000 or 2000 is still very high.

Quite simply, the system doesn't have enough data to accurately predict your level of performance & thus you have a high level of deviation or, uncertainty.

Let's use the values of a higher-rated player as an example.

The mean is 2189 and the deviation is 56.8 (after 500 games).

![123gt1330944863.png](/images/123gt1330944863.png)

As you can see, the system predicts they will perform between 2150 and 2250. A performance higher or lower than that is considered statistically unlikely.

Now let's examine a random player after 30 games.

Mean = 1188 deviation = 91

![1mynw1330945052.png](/images/1mynw1330945052.png)

That player is below the statistical average. Trueskill thinks that his rating is between 1100 and 1300. As before, Truskill thinks it's statistically unlikely that they will perform higher or lower than that.

### What you see in the leaderboard

It's a simple mathematic formula: Rating = Mean - 3 \* deviation. (meaning 0 at the start).

That's a very simple representation, and should be pondered by the number of games of the players: Under 30, it's not meaningful.

Why we are using that? It's a conservative estimate value. With a rating of 1200, it means that you probably perform higher than 1200, but unlikely under 1200.

So by checking that number, you can be sure that the player has all the chances to perform at least to a certain level, and probably best.

### Why did I gain nothing from a game?

"Before" the game, Trueskill is "betting" on a particular outcome. If you have a 90% chance of winning, and win, it means that your current rating is correct, and therefore doesn't require adjusting. But your deviation will decrease as the system is now more *statistically* certain of your actual rating. 

But if it "bet" a 40% probability of losing and you win, that means that your rating need to be adjusted as it's probably wrong. Your deviation will still decrease (as any additional data is valuable), but not a lot.

In conclusion, you won't gain points for winning games that you should win, or lose points for games that you are unlikely to win. This is why the TrueSkill system doesn't suffer from inflation.

### Why did I lose points/don't gain points with a win?

Before each game, the server is adding more deviation to your score. It's not supposed to happen, but it's there to reflect the fact that you are not a robot and add more dynamism to the ladder. What can happen in very balance games or very unbalanced ones, is this :
- Your mean is slightly increased as it should be. But not a lot as the outcome of the game confirm your current rank.
- Your deviation is lowered as it should be, but not that much as the game was not meant for an adjustment. The result is your deviation being inferior to the number we add to it before it starts. (increasing your deviation).

As your rating is Mean - 3 \* deviation and your mean doesn't move a lot while your deviation slightly increases, the result is a lower rating.

It doesn't mean that you lose points. Your mean will still be increased correctly. When this happens, it can be a 1 or 2 points decrease maximum. It's not meaningful.

**Remember that true skill is supposed to put you in the right place, once determined, you won't move a lot. So you can't always gain points for a victory !** Once you reach your rank, your rating won't move a lot. This is perfectly normal.

### How does it work in team games?

Each team is the sum of each player's rating. You can think that it's not true because some members of the team probably work harder than others. 

Additionally, sometimes special dynamics occur that make the sum greater than the parts.

But it will be impossible to consider these. Instead, Trueskill follows one rule :

*“Statistically sophisticated or complex methods do not necessarily provide more accurate forecasts than simpler ones”*

At the end of the game, the result of the team is propagated to your rating. Meaning that a teammate can gain a lot from a game while you don't gain anything.

### Conclusion

At first, your deviation is so high that your rating is meaningless.

That also means that in your first games, your rating can be very "jumpy" or very low/high for no good reason. This is normal, as your deviation will have more importance than your mean (Mean - **3 \* deviation**, higher the deviation, higher the "jumpiness").

Your deviation is decreasing after each game, no matter what (maybe a lot, maybe not, that depends on the relevance of that game).

**After 30-40 games, the system "learns" you, and your rating starts to make sense.**

## External links

„\[<http://www.moserware.com/2010/03/computing-your-skill.html>\|
Computing Your Skill\]“ – Moserware

# **Game balance index**

### Quick explanation
- 100 % = Game is balanced.
- 75 % = Game is most likely balanced.
- 50 % = Game is maybe balanced.
- 25 % = Game is most likely not balanced.
- 0 % = Don't bother launching that game.

40% doesn't mean that the game will be awful. 5% means it.

You maybe want to read the [conclusion](/Rating-System#the-game-balance-index) too.

### What is it?

The game balance index is a representation of how well the teams in your match are balanced, according to the current team composition.

For example:

In an x Vs x situation :

An index, of 1 (100%) means that both teams have an equal chance of winning the game.

An index of 0 ( 0% ) means that one team have statistically no chance of winning. This is a non-zero probability but extremely unlikely.

### Why do two teams/players with the same rating don't have a 100% index?

First, because of what is explained here : [How Trueskill works](/Rating-System#how-trueskill-works).

Two players with the same visual rating can have very different mean and deviation values.

But even two players with the same mean and deviation won't get you a 100% balance rating!

If the deviation is high, the chances that your "mean" is correct are low. (your deviation is reflected by the colour of your rating in the lobby. Whiter = closer to your real rating)

As a new player :
![1ula41330944573.png](/images/1ula41330944573.png)

In a 1v1, two players with that graph can perform between/around 1000 or 2000. Meaning that possibly, we are matching an 1100-rated player against a 1700-rated player!

As we don't know, the game balance is pondered. That kind of match-up will result in a game quality factor of 44%.

![1mynw1330945052.png](/images/1mynw1330945052.png)

With two players with these values (Mean = 1188, deviation = 91, after 30 games), the game quality would be 94%.

### Conclusion

As the values are pondered by the deviation of each player, the game quality index can be used in a reliable way to determine if the game is balanced or not.

**But it's only a simple representation of it**, it doesn't mean that a game rated 20% will be horrible to play, there are many other factors, unknown by the system :
- The position of the players. Maybe A player can be very good at one spot and very bad at another.
- The map: One player can be a poor player in general, but very good on a specific map he played over and over.
- The kind of game: Maybe a player is very good at custom 1v1, but doesn't perform as well in team games.
- The fact that one team is used to play with each other.

So don't judge if a game should be played or not by that index. It's only there to help you determine the overall balance in a random situation!

It's recommended that you follow [Widely Accepted Guidelines](https://goo.gl/koNAkt) when balancing team games.

## How does it compute that index in an X vs X vs X (vs X) situation?

You must first understand what that index is.

It's the probability of getting a draw for all participants.

It uses a skill chain to do it.

![betaskillchainillustration.png](/images/betaskillchainillustration.png)

You can think of beta as the number of points to guarantee about an 80% chance of winning.

The skill chain is composed of the worst player/team on the far left and the best player/team on the far right.

Each subsequent person on the skill chain is “beta” points better and has an 80% win probability against the weaker player.

So, to have a high Game quality in that case, each player/team should have a low beta difference in each link. (meaning that every player has a high chance to get a draw from another player).

# **What is 'Global Ranking'**?

FAF uses a real rating system for every game. This system gives a real-time rating of all players who have participated in custom and/or ladder FAF games. A player's score depends on his in-game performance; good performance leads to an increased rating, while poor performance causes a drop in rating. You can find your exact rating [here](https://faforever.com/competitive/leaderboards/global), but keep in mind, a high rating does not mean you're good, but you may have a high rating because you're good.

### Which games affect Global Ranking?

**Only Custom Games** affect global rating. [TMM](/Play/Client/tmm) matches affected 1v1 and global rating for a while, but now 1v1 games affect a different rating only, your "Ladder rating"
- Your rating increases when you win a rated game, and decreases when you lose a rated game. In-game performance, beyond win or loss, has no effect.
- Your rating, the rating of your opponent, your rating's volatility, and the volatility of your opponent's rating determines how much your rating changes. For an intuitive explanation, watch this video guide: [How Does the Rating System Work?](https://goo.gl/dzSEhP)

#### When is the game rated?

Generally, **all standard** games are rated, but a few exceptions exist:
- ***Certain game settings***
	- ***Victory condition is not Assassination***
	- ***Fog of war is turned off***
	- ***Cheats are enabled***
	- ***Prebuilt units are enabled***
	- ***No Rush is enabled***
	- ***There are unit restrictions***
	- ***Teams are unlocked***
- ***There are too many desyncs*** - there will be popups; after about 20 of them the game won't get rated
- ***The Map itself is unranked*** - for example, "12 The Pass" or "Rush Me More"; this can be because the map is unbalanced or because the creator chose to unranked it
- ***Uneven numbers of players*** - e.g 3v2
- ***Free for all games*** are not rated, however, they have been in the past due to bugs. Do not intentionally rate FFA games as it is [considered an exploit.](http://forums.faforever.com/viewtopic.php?f=12&t=11322#p116202)
- ***Games under 60 seconds per player present*** in real time (not the in-game time, and observers are not counted)
- ***[Sim Mods](/Mod-Vault#sim-mods)***
	- ([RK's Explosions](https://forums.faforever.com/viewtopic.php?f=41&t=6813) mod IS rated)
	- ([Auto Adjust NetLag](https://forums.faforever.com/viewtopic.php?f=41&t=4307) has some rated versions)
	- ([Santa is Coming Reloaded](https://forums.faforever.com/viewtopic.php?f=41&t=13543) mod IS rated)
- ***Information sent to the server after the game is faulty or conflicting*** - This can rarely happen because of bugs, report it so it can be fixed.

## **Ranking in the lobby**

You can access [TMM](/tmm) (1v1) ranking from the [Leaderboards](/Leaderboards) tab, but only players who played a [TMM](/tmm) game in the last two months are shown there. You can also see the approximate [Global Ranking](/Global-Ranking) in the chat when hovering over the icon of a user in [the list](/FAF-chat).

### Ranking in-game
 
You can see the global rating of any player next to his nickname in the FA lobby.
- To see the precise number, right-click on a player's name and select *View Player Statistics* - this will show you a Gaussian distribution (what the rating is) and you can see them *displayed rating* at the bottom of the window.