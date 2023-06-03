## Game balance index

### Quick explanation

-   100 % = Game is balanced.
-   75 % = Game is most likely balanced.
-   50 % = Game is maybe balanced.
-   25 % = Game is most likely not balanced.
-   0 % = Don't bother launching that game.

40% doesn't mean that the game will be awful. 5% means it.

You maybe want to read the
[conclusion](The_game_balance_index#Conclusion "wikilink") too.

### What is it ?

The game balance index is a representation of how well the teams in your
match are balanced, according to the current team composition.

For example:

In a x Vs x situation :

An index, of 1 (100%) means that both teams have an equal chance of
winning the game.

An index of 0 ( 0% ) means that one team have statistically no chance of
winning. This is a non-zero probability but extremely unlikely.

### Why two teams/players with the same rating don't have a 100% index ?

First, because of what is explained here : [How Trueskill
works](How_Trueskill_works "wikilink").

Two players with the same visual rating can have very different mean and
deviations values.

But even two players with the exact same mean and deviation won't get
you a 100% balance rating !

If the deviation is high, the chances that your "mean" is correct is
low. (your deviation is reflected by the color of your rating in the
lobby. Whiter = closer to your real rating)

As a new player :

![<File:1ula41330944573.png>](1ula41330944573.png "File:1ula41330944573.png")

In a 1v1, two players with that graph can perform between/around 1000 or
2000. Meaning that possibly, we are matching a 1100 rated players
against a 1700 rated player !

As we don't know, the game balance is pondered. That kind of match-up
will result in a game quality factor of 44%.

![<File:1mynw1330945052.png>](1mynw1330945052.png "File:1mynw1330945052.png")

With two players with these values (Mean = 1188, deviation = 91, after
30 games), the game quality would be 94%.

### Conclusion

As the values are pondered by the deviation of each players, the game
quality index can be used in a reliable way to determine if the game is
balanced or not.

**But it's only a simple representation of it**, it doesn't mean that a
game rated 20% will be horrible to play, there are many others factors,
unknown by the system :

-   The position of the players. Maybe A player can be very good at one
    spot and very bad at another.
-   The map: One player can be a poor player in general, but very good
    on a specific map he played over and over.
-   The kind of game: Maybe a player is very good at custom 1v1, but
    doesn't perform as well in team games.
-   The fact that one team is on teamspeak.
-   The fact that one team is used to play with each other.

So don't judge if a game should be play or not by that index. It's only
there to help you determine the overall balance in a totally random
situation!

It's recommended that you follow [Widely Accepted
Guidelines](https://goo.gl/koNAkt) when balancing team games.

## How does it compute that index in a X vs X vs X (vs X) situation ?

You must first understand what that index really is.

It's the probability of getting a draw for all participants.

It uses a skill chain to do it.

<figure>
<img src="BetaSkillChainIllustration.png" title="BetaSkillChainIllustration.png" width="600" alt="BetaSkillChainIllustration.png" /><figcaption aria-hidden="true">BetaSkillChainIllustration.png</figcaption>
</figure>

You can think of beta as the number of points to guarantee about an 80%
chance of winning.

The skill chain is composed of the worst player/team on the far left and
the best player/team on the far right.

Each subsequent person on the skill chain is “beta” points better and
has an 80% win probability against the weaker player.

So, to have a high Game quality in that case, each player/team should
have a low beta difference in each link. (meaning that every player has
high chances to get a draw from another player).
