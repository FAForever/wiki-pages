---
title: Frequently Asked Questions
description: 
published: true
date: 2021-09-29T11:07:02.078Z
tags: 
editor: markdown
dateCreated: 2021-09-29T11:00:10.001Z
---

# Frequently asked Questions {.tabset}

## I lost acsess to my account!

### Case 1: You forgot your password
Use the [reset password](https://www.faforever.com/account/password/reset) form on the website

### Case 2: You forgot your password and don't remember your username
Did you really forget it or did you just forget that you renamed your account recently? Ok let's assume you forgot it:

Solution A: If you know your accounts email address, you can login to the website using your email address. Click on the user symbol in the top right, there you can then see your username.

Solution B: Use [password reset](https://www.faforever.com/account/password/reset) via Steam. After the Steam login you are redirect to a page that greets you with your username.

### Case 3: You forgot your password and the email address of the FAF account no longer exists or is inaccessible

Use [password reset](https://www.faforever.com/account/password/reset) via Steam. After the Steam login you are redirect to a page that greets you with your username. After the login change your email address!

### Case 4: You forgot your password and the email address of the FAF account no longer exists or is inaccessible and you have no access to your Steam account

Unless there is a moderator who knows you personally for years and can vouch for you, you are screwed. Since we can't verify your identity all you can do is create a new FAF account, buy the game on Steam once again with a new Steam account and link the new FAF account with the new Steam account.

### Case 5: You forgot your password and the email address of the FAF account no longer exists or is inaccessible and the account was never linked to Steam

Unless there is a moderator who knows you personally for years and can vouch for you, you are screwed. Since we can't verify your identity all you can do is create a new FAF account, buy the game on Steam and link the new FAF account with Steam.

## I bought Forged Alliance, but not on Steam. Can I still play on FAF?

### Case 1: You own a retail copy of Forged Alliance

According to [GPGs last statement](https://web.archive.org/web/20140903143132/http://forums.gaspowered.com/viewtopic.php?f=67&t=57459), you can use your CD key and redeem a licence on Steam.

If you have a gold edition (Supreme Commander and Forged Alliance in one) you have two CD keys, and from my personal experience each of them can be redeemed for a gold edition on Steam. (-> so you could give one cd key to a friend 😉 )

If you refuse to use Steam in general, then you can't play. (Read more why we require Steam See Why-do-I-need to-link-my-account-to-Steam?.)

### Case 2: You bough the game on [GOG.com](https://www.gog.com)

Sorry, we do not support licence checking on GOG. We are in contact with GOG to resolve this issue.

## Why do I need to link my account to Steam?

The legal entity of FAF (details here) doesn't own any copyright or trademark regarding Supreme Commander or Forged Alliance. We also do not have an explicit permission of the current rights holder Square Enix, however GPG explicitely [mentioned FAF](https://web.archive.org/web/20140903143132/http://forums.gaspowered.com/viewtopic.php?f=67&t=57459) as a replacement before shutting down GPGnet.

So basically FAF operates in a grey area of the law. To protect ourselves, we decided to make sure that each user of FAF owns a valid licence of Forged Alliance.

As of now, the only way to technically verify that each user owns a Forged Alliance copy is by looking up your Steam accounts game list, which is what happens during the Steam link process.

## I can't hear some of the Audio or other Sound issue. What should I do?

You need to make sure your audio is configured to stereo 16bit 44100MHz.

first set it to stereo, you do this by opening the old windows audio settings menu (go to configure) :

![1.png](/1.png)

Now select Stereo :

![eb531897-a516-4c5f-8e87-41aeca9f365a-image.png](/eb531897-a516-4c5f-8e87-41aeca9f365a-image.png)

Then you can set it to 44100 Hz in the "Advanced" tab :

![d999a623-d6c7-43ec-8b8d-93f9a78122c0-image.png](/d999a623-d6c7-43ec-8b8d-93f9a78122c0-image.png)

there. you're now in stereo audio but there's a good chance this won't be enough if the first time you installed and ran FA, your computer was configured to use surround sound audio.

to persist these changes into FA, delete your Game.prefs file at (warning you'll loose your FA user config for example what mods are enabled, what settings you set, build templates) :

%LOCALAPPDATA%\Gas Powered Games\Supreme Commander Forged Alliance\Game.prefs

and re-create it by running Forged Alliance from steam and re-creating your username.

Now FA understands that it is in a stereo environment and audio will work.

You can remake your templates, and add your settings and ui mods back.

The bottom line is Forged Alliance and 5.1 or 7.1 surround sound are incompatible as FA was built before these techs were on the market so you have to choose.

however, in my experience. so long as FA is shut down when you switch your audio back to 5.1 or 7.1 and you switch your audio back to stereo before running FA again, everything works out.

## What are my FAF ratings?

FAF utilizes three different trueskill values or "ratings" in order to gauge player capability in three different environments. There is the ladder rating which is meant to showcase your ability in the controlled environment of the 1v1 matchmaker. There is also the matchmaker rating which is meant to showcase your ability in the controlled environment of the 2v2 matchmaker. Finally, there is the global rating which is meant to reflect your ability to play ranked custom games. Ranked custom games could span a wide array of game types from 1v1 to 8v8 and can even include certain ranked mods such as Equilibrium.

These ratings are mutually exclusive and so they do not interact with one another. Playing ladder will not result in you losing or gaining global rating, nor will playing 1v1 custom games have an influence on your ladder rating.

However, it should be noted your global rating CAN impact your initial matchmaker rating when you first start playing it. To learn more about this, please look at problem 2 in this FAQ answer:

https://forum.faforever.com/topic/1192/how-does-the-matchmaker-match-players

You can keep track of your ratings by right clicking on your name in the client and hitting "show user info" or by simply using the website: https://www.faforever.com/competitive/leaderboards/1v1

## Who owns FAF and how is the organisation structured?

FAF basically can be seen from three perspectives:

---

**The community (+ content)**
The community is of coursed not owned by anybody. However we have a leadership structure called the "[Council of Setons](/User-Groups)". For a more detailled explanation have a look at this [Youtube tutorial](https://www.youtube.com/watch?v=ZraD244VywA).

The content of the community (maps & mods in particular) are owned by the particular creators. The legal entity is only hosting it.

The community live takes place mostly in

- the IRC chat access by the client (or any other IRC tool)
- the forum
- the official [Discord server](https://discord.com/invite/hgvj6Af)

We also have some dedicated places to meet, e.g.

- Zulip (invite only, contact a moderator or forum admin to get access)
- Map & Mods discord
- AI dev discord
- Nomads discord
- and some others
---
**The open source project**
The open source project runs on [Github](https://github.com/FAForever). As the name implies it's free software, to be used by everybody.

**Operations**
FAF operates legally as "Forged Alliance Forever LLC" in the USA. This company is owned by Jonathan Taylor aka Visionik.

The legal entity operates the infrastructure for FAF (domains, servers, 3rd party services...) and owns the data on the servers.

**However, all work (server admins, developers, supporters) is done by volunteers in their free time.**

## What is a UI mod and what is a sim mod? 

UI = User Interface
Sim = Simulation

A UI mod affects only your computer, it affects how you interact with the game. It can change how information is displayed to you (for example on the scoreboard) and it can turn things on and off for you, like it could sometimes turn your radar off to save power.

A SIM mod can make much more serious changes to the game for all players. For example, a SIM mod could change the amount of HP that a tank has or add new units. A SIM mod could change how the scoreboard looks to every player. Games with SIM mods are unrated.

Each player can choose their own selection of UI mods, but SIM mods (which can be activated in custom games by the host) need to be identical for every player in a game.

That is because each player's computer is simulating the entire game and they must stay synchronized. It would break ("desync") the game if, on your computer, a tank had 300 hp, and on your teammate's computer, the tank only had 250hp. To ensure this, when you join a lobby with activated SIM mods, your client will automatically attempt to download and activate (only) those mods.

## How Does the Matchmaker Match Players?

In order to understand FAF Matchmaking you're going to first be better off having a basic understanding of how TrueSkill itself works and then the problems with the system that FAF attempts to address. So let's begin with that.

**TrueSkill:**
Regardless of whether you're playing a teamgame or a 1v1, TrueSkill operates quite similarly for both types of games. In 1v1, the matching process is primarily centered around a player's mean (or mu) value which is the level the system is 50% confident you can play at. It then proceeds to try to find a player that is close to this mu value for you to then play a game against.

Once this game is over, the system is then able to calculate the impact of this game loss upon you by reviewing player deviation (or sigma). A high sigma player is going to get a larger magnitude in change from the game result than a low sigma player. This will continue until the system is able to properly place the player after putting them against a broad range of players. This is why lower rating players are often put against people quite a bit better than them, as the matchmaker itself needs to ensure that the player is not able to beat such players and then refine the matchmaking process further.

In teamgames, individual player mu values are combined to find the team's sum mu value at which point the game is treated like a "1v1" except the 1v1 values are formed from a sum of individual values. Player individual sigma will determine the impact of the game result on the individual player.

**Problem 1: New Player Mu and Sigma**
In FAF, a new player is given the values of 1500 for mu and 500 for sigma. The values themselves hold no intrinsic meaning and the reasoning for why they were chosen as the set values are irrelevant. Essentially 1500 mu and 500 sigma means that the intended bell curve of FAF is meant to peak at 1500 mu and the 500 sigma means that a new player shows as "0 rated" on leaderboards, lobbies, etc.

However, in FAF, the distribution of players is not the expected distribution that our TrueSkill values are meant to operate under. Namely, 1500 mu is not the top of our player distribution bell curve. There are many reasons for this but none are necessary to go into. 1500 mu is quite far off the top of our player population distribution curve and so it makes the new player experience quite awful as they are playing individuals they have nearly 0 chance of defeating in their first initial game. This makes the experience terrible for both players and also leads to inefficient data gathering for the algorithm.

So how does FAF solve it? We utilize a linear interpolation method for new players as the traditional TrueSkill method of player matching is not as practically efficient as it should theoretically be. For their first 10 games, a player will get MATCHED based on this adjusted rating when they are a new variable in the environment.

Here is a basic equation to explain how it works:

![linearinterpolation.png](/linearinterpolation.png)

Example: A new player's mu would be:

![linearinterpolationnew.png](/linearinterpolationnew.png)

Which simplifies to 500 mu.

**Note:** This interpolation has no impact on how your rating is recorded within our database nor how it shows up in game. This adjustment strictly happens when the system is creating matches.

So new players should expect to match up against people at around 500 mu, which is approximately 200-300 shown rating.

**Problem 2: What About Players that Play in Other Environments?**
FAF has several TrueSkill elements. We have 1v1 rating, 2v2 rating, and global rating. So how does the system try to account for the fact some people have way more experience than others?

Well, TrueSkill itself attempts to do through the high sigma value attached to new players. However, as we can be confident that the data attached to these other ratings have some sort of inherent value in determining the skill of an individual player, we can use this data to make the experience of transitioning between various closed environments of FAF more fluid.

What we do is we take the global mu and sigma of a player, add 150 sigma up to a maximum of 250 sigma, and then utilize this as your matchmaker rating. This will be the matchmaking rating that is recorded in the database for you and it will be what the system utilizes to determine your competency as a player PRIOR to the linear interpolation method. If this confuses you, please look at the example in the following post.

Why do we increase sigma? Because while we can be certain that a 1500 mu player in global games has a general understanding of the game that should be larger than what you would expect from an 800 mu player elsewhere in the environments on FAF, we can't be certain that it is equivalent to a 1300 mu player in these other environments. Hence, the sigma increase to account for the fact we have data of some value, but not absolutely certain data on the skill of a player as they transfer between environments.

**Problem 3: Getting New Players in Games as Fast as Possible**
No one likes waiting, particularly new players. It's up to us to prove that the game is fun and so we want them getting into a game as quickly as possible. For that reason, we decided to implement a controlled random matchmaking process that attempts to match new players as quickly as possible.

However this has a problem that circles back to Problem 1, namely that we do not want new players matching with extremely competent players as no one will enjoy such games. So instead, we devised a way to separate a "newbie" from a "top player" and utilized that in this controlled random process.

So first some definitions:

A top-level player is anyone with mu over 1600
A newbie is anyone with less than 10 games.
All teams with at least one newbie and no top-rated player will be matched randomly amongst each other if no decent game is initially found. If there are an odd number of newbie teams, the last newbie team can only match with a non-newbie team that has at least one failed matching attempt. If a team has a top-rated player, that team will not be eligible for random matching at all.

So in order to clarify this system a bit more, I'm going to walk through an example.

>Let's say we have a player that played pure astro in global games and is now 1500 rated with 150 sigma. This player >would now like to play this new 2v2 matchmaker he heard about. What will happen to him?
>
>Initially, the system will rate him by taking his global rating values (1500,150) and adding additional sigma to him to account for the potential growing pains of the player. Evidently astro gameplay is quite different from traditional 2v2 gameplay, and so a slight decrease in certainty should be expected.
>
>This player will now be considered (1500,250) by the system. Why not 300 sigma? Because it chooses the smallest value between (global sigma+150, 250).
>
>In addition, this player, for his first 10 games, will utilize the linear interpolation method when deciding who he will MATCH against not what his actual rating IS.
>
>We know from the equation above that this would put him at ((10-0)x500+(0x1500))/10 or 500 mu for his first game. On his second game, he will have (9*500+1x1502)/10 or 600 mu.
>
>You can see the player gained from 1500 mu to 1502 mu. Why such a small change? Because he faced someone around 500 mu and the system would expect an individual with 1500 mu to easily trounce someone with 500 mu. The slight adjustment reflects that. The linear interpolation will continue until the player reaches 10 games.
>
>In addition, if this player is queueing with another player that is also below 1600 mu, then these players should be matching up quite frequently due to the random matchmaking protocol.

## How is My Rating Bracket Determined for the Matchmaker?

Your TrueSkill rating is composed of two general elements. One is called mean (or mu) and another is deviation (or sigma). Mu is what level the system is 50% confident you can play at, with sigma being the deviation from said level. Counterintuitively, neither of these are what you are shown in the client as "your rating."

Why is this? Well long story short it's a way to give a leaderboard that doesnt immediately place new players well above their actual level as they often start with a large mu but also have a large sigma in turn which allows them to match with a large variety of the game playerbase but also their initial game results are immensely helpful in placing them at their actual skill level.

Think of it as meeting a person for the first time. The first 5 minutes of conversation with him are often going to shape your impression of them much more than the 500-505th minute of conversation (this is the high sigma), but you have no idea if the guy is going to be chaotic evil or lawful good, so you start at total neutrality (assuming neutrality is the most common type of person, this is mu).

Anyway, back to the Matchmaker. The FAF Matchmaker is divided into a few segments for maps, <500, 500-1000, 1000-1500, 1500-2000, and 2000+. These rating divisions are based upon your mu, not your actual shown rating which is mu-3*sigma. There is currently no easy way to find your individual mu, however, we are working towards removing the shown rating element for the matchmaker and will instead present an individual player with their mu rating.

If you would like a simple way to gauge your current mu, players typically settle in with around a 100 sigma on FAF due to the specific way our implementation works. So just imagine adding 300 rating to your current shown rating, and you have a general estimation of your mu value. Do note this is only really going to be an accurate estimation after a dozen or two games.

## Why was game X not rated?

There are plenty of reasons, why a game was not rated. Here is the official list in technical order:

- game had too many desyncs
- game had wrong victory condition (e.g. sandbox)
- fog of war was disabled
- cheats were enabled
- prebuild was enabled
- norush was enabled
- unit restrictions were active
- map was unrated
- game was too short
- mod was unrated
- game was coop
- game ended with mutual draw
- single player game
- game mode was free for all
- teams were uneven
- unknown results (as in "there was an issue with the server receiving all game results)
- teams were unlocked
- game had more than 2 teams
- game had AI players
- civilians were revealed
- wrong difficulty (hu, I have no clue what that is)
- expansion was disabled (same here)
- spawn positition wasn't fixed
- other

In particular the reason "unknown results" is an ongoing issue with FAF as we seem to have problems to get game results sent to and parsed by the lobby server

## How to fix website registration/steam link error "Access token expired"

**The problem**
If you are on the website and try to

- confirm your registration
- reset your password
- link to Steam

In rare cases an error message "Access token expired" can occur.

**The cause**
1. Known cause: The URL you get has a limited lifetime. For registration and password reset, it's 1 week. For link to Steam it's 6 hours. If you do not click on the link within the lifetime, the error occurs.

2. The unknown cause (only Steam link): A lot of people claim the get the error even within the lifetime of the token. We believe that, unfortunately we cannot reproduce it and therefore don't know the reason.

**The solution**
In case 1) just retry: Re-register, re-request a password reset or restart the Steam linking process.

In case 2) in many cases it helps to logout and relogin to the website.

