---
title: Game team statutes
description: Represents the statutes of the game team
published: true
date: 2024-06-27T18:50:07.702Z
tags: game, game team, team, governance, statutes, game team statutes
editor: markdown
dateCreated: 2024-06-27T18:50:07.702Z
---

# Team lead:

- Jip ([Garanas on Github](https://github.com/Garanas))

# Team Members:

- [Madmax](https://github.com/MadMaxFAF)
- [Hdt80bro](https://github.com/Hdt80bro)
- [4z0t](https://github.com/4z0t)
- [BlackYps](https://github.com/BlackYps)
- [Cheeseberry](https://github.com/ChessBerry)
- [Clyf](https://github.com/clyfordv)
- [Relent0r](https://github.com/relent0r)
- Nomander ([lL1l1 on Github](https://github.com/lL1l1))
- Jip ([Garanas on Github](https://github.com/Garanas))

# Policies:
Every team in the FAF community is required to have a mission statement. This was made mandatory at the general meeting of the 6th of March, 2022 when the `Governance structure` proposal was accepted. The mission statement the game development team describes:
 - The roles of the team
 - How someone can attain a role
 - How the team operates
 - What the responsibilities of each role is
 - How the administrator is chosen

It is important to understand that all game team members and contributors are expected to act in accordance with the [Code of Conduct](https://forum.faforever.com/topic/2051/faf-code-of-conduct/1) of our community. This includes, but is not limited to:
 - Be open
 - Be empathetic, welcoming, friendly, and patient
 - Be collaborative
 - Be inquisitive
 - Be careful in the words that we choose
 - Be concise
 - Step down considerately

# Roles and attaining them

The game development team consists of the following roles:
 - Administrator
 - Maintainer
 - Associate 
 - Tester

In the game repository there is a clear distinction between UI and simulation related code. They both require a different approach and are, from a code-perspective, unrelated to each other. It is important to understand that a contributor may not be equally equipped to solve each type of problem. We use the tags `area: sim` and `area: ui` to make this distinction for issues and pull requests. 

The roles are tightly coupled with the interactions and permissions in the repository:
 - Administrator `->` Admin role on Github
 - Maintainer `->` Maintain role on Github
 - Associate `->` Write or Triage role on Github, part of the [contributors list](https://github.com/FAForever/fa/graphs/contributors)
 - Tester `->`Triage role on Github

We'll now discuss each role and describe how someone can attain a role.

## Administrator

In addition to the responsibilities of a maintainer, the administrator is also responsible for the repository and the game development team as a whole:
 - **(1)** Create and manage the work surrounding a release
 - **(2)** Create and manage the projects that help guide contributors on what they can work
 - **(3)** Be pro-active towards contributors to discuss their contributions
 - **(4)** Be accessible towards other teams

**(1)** The administrator understands how Git and Github works, how we distribute the files to our users and what the consequences are of a release that is unstable. Unstable means anything that breaks the game or the immersion of the game towards the user. The administrator will do his best efforts to guarantee a stable release. An unstable release can damage the project.

**(2)** The administrator provides a clear vision to guide the contributions of the project. All projects requires some form of guidance - a common goal that we are trying to achieve. It allows for  This creates a more stable development environment and allows for productive discussions. 

**(3)** The administrator pro-actively responses to issues, pull requests and general questions of both contributors and the community in general. This is important to create an open and interactive development environment. There is nothing worse for a contributor than seeing his or her contribution being ignored for weeks on end.

**(4)** This is relevant for all teams, but the interactions between the Balance team and the Game development team is particularly critical. We share the same repository. The administrator is responsible to create and manage the work surrounding their release too. 

And last but not least: the administrator has the ultimate veto pull requests and membership of the team.

Due to the required mindset, skillset and the burden of responsibilities the administrator is not elected in a democratic vote of the whole team, nor is its position restricted to a limited period of time. The administrator can be replaced with a constructive vote of no confidence. This requires:
 - An appointed successor by the person who initiated the vote of no confidence
 - Approval of 1/2 of the maintainers, including the administrator

Should the administrator resign then it is expected to be accompanied by a proposal for a new administrator. This can only be overruled by the same rules as a constructive vote of no confidence.

Should there be no successor the maintainers have to elect one from themselves with an absolute majority. If an absolute majority is not achieved in the first ballot, a run-off election is held.

## Maintainer

In addition to the responsibilities of an associate, a maintainer has sufficient experience with Lua and the code base to have informed discussions and make informed decisions about a pull request. In particular, the following aspects need to be taken into account: 
 - **(1)** Backwards compatibility with (legacy or featured) mods and co-op
 - **(2)** Documentation
 - **(3)** Testability
 - **(4)** Maintainability
 - **(5)** Code performance

**(1)** At FAF we have the luxury of a vast amount of content that has to work with our repository. These include featured or unmaintained mods such as `Nomads` or `BlackOps`, maps that apply extensive scripting such as `DDDX Survival` or `Genesis of the Order Survival` and of course all of the co-op maps. These should not be broken unless there's a (very, very) good reason for it.

**(2)** Proper documentation is critical in weakly typed languages to understand what the arguments of a function and its return type means. We're dealing with programmers of varying technical backgrounds with varying experience. And as with any open source project, contributors can come and go - the documentation should be sufficiently detailed, yet concise to help the wide range of programmers understand and work with the code base.

**(3)** When possible, code should be written so that it can be tested. We do not have an extensive test suite because it is difficult if not impossible to mock the engine. We should however strive towards writing functions that are pure to their arguments. This allows the function in question to be more easily tested and, if applicable, re-used accordingly.

**(4)** This aspect is tightly coupled with documentation and testability, as they both increase maintainability. We mention it here specifically because it is important to write solutions that are both simple, yet complicated enough to solve the problem in question. Sometimes this may require some refactoring. This is a delicate balance as we're dealing with a lot of legacy code.

**(5)** This is more relevant for code related to the simulation then it is for code related to the UI. Any change we make needs to be weighted accordingly: is this change worth the cost to performance? 

One burden of a maintainer is to make a decision that may be unpopular at times. As an example, when a pull request implements a widely requested feature but it is poorly implemented, untestable and undocumented then you may have to vote against it until the contributor responsible for the pull requests makes the required changes.

For an associate to become a maintainer he or she needs to be appointed by one of the team members. The associate is accepted with an approval of 1/2 of the maintainers, including the administrator. 

## Associate

An associate has no responsibilities. They likely either:
 - Participate in discussions surrounding the game
 - Contribute by making pull requests on Github
 - Contribute by making issues on Github

An associate has access to the development channels on [Discord](https://discord.gg/mXahVSKGVb), if you do not have access you can ask access by contacting the administrator.

An associate is not a member of the game team.

## Tester

With this role you'll help the community by providing insights on, and guarding the quality of what we develop. You'll have access to the Discord channels that are usually read-only for the rest of the community. There you can share your thoughts on bugs or features and participate in discussions with the game developers.

## What your profile is

- You have a general interest in game development
- You have an interest in understanding the magic behind the game and the development of a game

### What you'll learn

- How to navigate and contribute on [Github](https://github.com/FAForever/fa)
- How to setup and use the [development environment](https://github.com/FAForever/fa/blob/deploy/fafdevelop/setup/setup-english.md)

### What you can aspire towards to

- How to debug the game and make sense of what happened when you encounter a bug
- About development in general and may even start contributing yourself

# Team operation

The team discussions happen on our official [Discord](https://discord.gg/mXahVSKGVb) channel, in particularly:
 - **(1)** `#game-bug-reporting`
 - **(2)** `#game-repository`

**(1)** This channel is accessible to anyone. It allows people to report issues to the game team without the requirement of having a Github account. Game team members can then make issues or pull requests accordingly.

**(2)** This channel can be read by everyone, but only written to by people associated with the game team. It allows us to have informed discussions without being interrupted.

A pull request should always be squashed. This makes it easier to trace back the reasoning behind the changes. All squashed pull requests should adhere to decent a commit-convention, as described for example on:
 - https://www.freecodecamp.org/news/how-to-write-better-git-commit-messages/
 - https://www.gitkraken.com/learn/git/best-practices/git-commit-message

Do not take these guidelines too literally, you can take any commit on `deploy/fafdevelop` as a source of inspiration.