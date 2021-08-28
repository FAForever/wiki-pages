## How Trueskill works

### Your rating and you!

The number you see in the leaderboards is an *approximation* of your
real rating.

What this means is that two players with the same rating can in reality
perform at different skill levels. At this time we are displaying the
approximation - you can see the actual distribution by right clicking on
your name in the player list and selecting *View Player Statistics.*

In reality, your rating is a [Gaussian bell
curve](http://en.wikipedia.org/wiki/Normal_distribution).

It's comprised of two values : Your mean and your deviation.

It sounds complicated (which is why we haven't shown them to you yet)
but it's easy to understand.

Don't be intimidated by the graphs, the concept is actually very simple.

The **mean** represent your maximum skill/rating. The system thinks that
it cannot be higher than that. Trueskill believes at your current skill
level, you can't perform at an higher level, but possibly also at a
lower one. Technically speaking, for a real-valued random variable X,
the mean is the expectation of X. For more information on the maths
behind this, visit Wikipedia. [1](http://en.wikipedia.org/wiki/Mean)

The **standard deviation** is the "uncertainty" factor. The bigger it
is, the higher your possible real rating is. Standard deviation is a
widely used measure of variability or diversity used in statistics and
probability theory. It shows how much variation or "dispersion" exists
from the average (mean, or expected value)

The mean is often quoted along with the standard deviation: the mean
describes the central location of the data, and the standard deviation
describes the spread.

Let's take the value of a new player. By default, you have 1500 in mean,
and 500 in deviation. 1500 is the **average level**.

![<File:1ula41330944573.png>](1ula41330944573.png "File:1ula41330944573.png")

When you join, the system predicts you will perform as average (1500).
However, as you can see on the curve, the probability that you will
perform at either 1000 or 2000 is still very high.

Quite simply, the system doesn't have enough data to accurately predict
your level of performance & thus you have a high level of deviation or,
uncertainty.

Let's use the values of a higher rated player as an example.

The mean is 2189 and the deviation is 56.8 (after 500 games).

![<File:123gt1330944863.png>](123gt1330944863.png "File:123gt1330944863.png")

As you can see, the system predicts they will perform between 2150 and
2250. A performance higher or lower than that is considered
statistically unlikely.

Now let's examine a random player after 30 games.

Mean = 1188 deviation = 91

![<File:1mynw1330945052.png>](1mynw1330945052.png "File:1mynw1330945052.png")

That player is below the statistical average. Trueskill thinks that his
rating is between 1100 and 1300. As before, Truskill thinks it's
statistically unlikely that they will perform higher or lower than that.

### What you see in the leader board

It's a simple mathematic formula : Rating = Mean - 3 \* deviation.
(meaning 0 at start).

That's a very simple representation, and should be pondered by the
number of games of the players : Under 30, it's not meaningful.

Why we are using that ? It's a conservative estimate value. With a
rating of 1200, it means that you probably perform higher than 1200, but
unlikely under 1200.

So by checking that number, you can be sure that the player has all the
chances to perform at least to a certain level, and probably best.

### Why did I gain nothing from a game ?

"Before" the game, Trueskill is "betting" on a particular outcome. If
you have 90% chances of winning, and win, it means that your current
rating is correct, and therefore doesn't require adjusting. But your
deviation will decrease as the system is now more *statistically*
certain of your actual rating.

But if it "bet" a 40% probability of losing and you win, that means that
your rating need to be adjusted as it's probably wrong. Your deviation
will still decrease (as any additional data is valuable), but not a lot.

In conclusion, you won't gain points for winning games that you should
win, or lose points for games that you are unlikely to win. This is why
the TrueSkill system doesn't suffer from inflation.(see [Why choose
Trueskill over Elo ?](Why_choose_Trueskill_over_Elo_? "wikilink")).

### Why did I lose points/don't gain point with a win ?

Before each game, the server is adding more deviation to your score.
It's not supposed to happen, but it's there to reflect the fact that you
are not a robot, and add more dynamism to the ladder. What can happen in
very balance games or very unbalanced ones, is this :

-   Your mean is slightly increased as it should be. But not a lot as
    the outcome of the game confirm your current rank.
-   Your deviation is lowered as it should be, but not that much as the
    game was not really meaningful for an adjustment. The result is your
    deviation being inferior to the number we add to it before it
    starts. (resulting in a increase of your deviation).

As your rating is Mean - 3 \* deviation, and your mean doesn't move a
lot while your deviation slightly increase, the result is a lower
rating.

It doesn't mean that you lose points. Your mean will still be increased
correctly. When this happen, it can be a 1 or 2 points decrease maximum.
It's not meaningful.

**Remember that trueskill is supposed to put you at your right place,
once determined, you won't move a lot. So you can't always gain points
for a victory !** Once you reach your rank, your rating won't move a
lot. This is perfectly normal.

### How does it work in team games ?

Each team is the sum of each player rating. You can think that it's not
true, because some members of the team probably work harder than others.

Additionally, sometimes special dynamics occur that make the sum greater
than the parts.

But it will be impossible to take these in considerations. Instead,
Trueskill follow one rule :

*“Statistically sophisticated or complex methods do not necessarily
provide more accurate forecasts than simpler ones”*

At the end of the game, the result of the team is propagated to your
personal rating. Meaning that a teammate can gain a lot from a game
while you don't gain anything.

### Conclusion

At first, your deviation is so high that your rating is meaningless.

That also mean that in your first games, your rating can be very "jumpy"
or very low/high for no good reason. This is totally normal, as your
deviation will have more importance than your mean (Mean - **3 \*
deviation**, higher the deviation, higher the "jumpiness").

Your deviation is decreasing after each game, no matter what (maybe a
lot, maybe not, that depend of the relevance of that game).

**After 30-40 games, the system "learn" you, and your rating starts to
make sense.**

## External links

„\[<http://www.moserware.com/2010/03/computing-your-skill.html>\|
Computing Your Skill\]“ – Moserware