---
title: Frequently Asked Questions
description: 
published: true
date: 2021-09-29T11:00:10.001Z
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