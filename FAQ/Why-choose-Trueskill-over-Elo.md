## Why choose Trueskill over Elo ?

The Elo rating system has some weaknesses that can make it unsuited to
Forged Alliance. For example, ELO is unable to rate anything but 1 vs 1
matches.

## Team Games

ELO is only really capable of rating of even team games, such as 2v2, it
cannot properly weight a Free For All or a team game with more than two
sides. Each team will be considered as a single player, so that the
leader board will show a result for each pair of player, for every pair
that ever exists.

TrueSkill however, can handle any match up. Teams are the weighted sum
of the players inside, and results are correctly calculated from the
team result to the players in the teams. It can easily handle FFA,
2vs2vs2 and so on.

## Draws

The ELO system handles draws differently from Trueskill. For Elo, a draw
is simply a half-win half-lost game.

TrueSkill measures a drawn outcome very differently Each map has a draw
percentage based of all of the outcomes of games played on that map.
TrueSkill considers draws as a meaningful outcome : You were matched
with a equally skilled opponent.

But Let's considers two players with the same skill.

On a map where draws are more unlikely, a draw game will lead to no
difference in skill, but the system is learning the player better
(actual skills are accurate - see below). That result will also increase
the overall draw probability for that map.

However, on a map like "Winter Duel" for example, where draws are a more
likely outcome a draw is expected as result, so the skill won't move,
but the system doesn't know the players better, so that game is
meaningless compared the "normal" map case. That result will also
increase the draw probability on Winter Duel.

Now let's say that player 1 wins.

On the "normal" map, the player will gain points, for example's sake say
a gain +4 points, and the loser receives a penalty of -4. That result
will decrease the draw probability on that map.

Now, on the Winter Duel map as draw was a more likely outcome, the fact
that player 1 wow means that's he is actually significantly better than
his opponent. As a result his rating will be revised upwards, so instead
of +4, he will gain +6, and the loser -6 for example. That result will
then decrease the draw probability on Winter Duel.

## Inflation

Elo systems can have a tendency to inflate over time. Because it's only
comparing 2 players' ratings to determine an new rating, a better player
who plays often will gain more and more points over time. For example,
at the beginning of the GPGnet ranked ladder the top 10 players were
rated around 1900. Presently the highest ranked player is around 2700.
Does that means that their skill is increasing ? Maybe. But not that
much. The rating increase because, as all good top tier players, they
plays often. And as they are goods, they win games, and gain points,
increase the rating over time.

To combat inflation, ELO system has a "K-Factor", limiting the maximum
points a player win or loss per game. GPGNet used a K-Factor of 30. In
the Chess leaderboard the K factor depends of the rating of the player
(A 2400+ players got a K-Factor of 16 where a newer player got 32).
That's arbitrary, not accurate and only artificially decrease the
inflation problem. \[citation needed\]

Trueskill is less susceptible to inflation. When you start a game,
TrueSkill calculates the possible -and probable- outcome of the game :
it estimates what are your chances of winning.

Let's say it predicts that you will win that game.

If you win the game, as it was the expected outcome, you will gain
points depending of the "chances of ranking" factor (itself depending of
the difference in skill between players, and the outcome probability).
If you lose the game, as an unexpected result, you will lose more
points. On paper, it sounds a lot like Elo, but the algorithms behind
are more evolved, and once you reach your real rating, unless you play
really badly or improve a lot, you will stay at that rank.

![<File:MostRecentFoosballTrueSkill.png>](MostRecentFoosballTrueSkill.png "File:MostRecentFoosballTrueSkill.png")

This graph represents a trueSkill rating for a selection of football
teams. As you can see, team 1 is the best, and their rank stays stable.
Team 5 had a bad start (you lost your first games), and were badly
rated. Over time, TrueSkill manage to correct that and find a stable
skill. Team 2 is the most interesting case : It's a new team, really
good. At start, it was rated way under their real skill. You can see how
fast the system was able to determine their correct rating. One of the
advantages of Trueskill is that it can determine your correct rating
very quickly.

## TrueSkill advantages

TrueSkill can rate ANY game. That's why ANY custom game or ranked will
contribute to your skill rating. TrueSKill can lower the impact of your
result : A FFA is less meaningful than a 1v1, so the outcome of a FFA
will contribute less.
