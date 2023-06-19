---
title: FAF Development
description: 
published: true
date: 2023-06-19T10:13:32.570Z
tags: development
editor: markdown
dateCreated: 2021-08-31T09:43:14.286Z
---

This document only covers development of the FAF.
- For information about mapping, please look at [GPG Map Editor](/Development/Mapping/GPG-Map-Editor) or the [FAF Map Editor](/Development/Mapping/FA-Forever-Map-Editor).
- For information about modding, please look [here](/Development/Modding)


https://github.com/FAForever/fa/blob/deploy/fafdevelop/setup/setup-english.md
## Source code & version control

Forged Alliance Forever is an open source project. You can find all sourcecode on [Github](https://github.com/FAForever). As the name indicates, Github uses **git** as version control system. If you want to participate in development, you have to use git and create a Github account (it's free). You can find a small introduction into how to develop for the client on our [FAF Dev Playlist](https://youtube.com/playlist?list=PL0nxuIUIjpFv6cjiaEwwVYpn3utdVUshc) or you can check out the [Game Dev](https://youtube.com/playlist?list=PL0nxuIUIjpFvqJ5i1HfPwoA8FnBCtGLWn) Playlist on how to tackle developing for the game.

We strongly recommend to use git on the command line at the beginning.
Please do not use the git tools inside your IDE before you have understood the basics of git.

## Communication

All developer communication takes place on Zulip or Corrisponding [Discord](https://discord.gg/2u36D9V) Channels.

If you want to join us, please contact an administrator/moderator on the forums or in our in-client chat (white names at the top) so that we can invite you to our Zulip project. 


## Infrastructure overview

If you have looked up our [Github page](https://github.com/FAForever),you may have noticed lots of sub-projects.

FAF consists of 5 important projects, which reflect the basic architecture:
- [Game](https://github.com/FAForever/fa): Forged Alliance gameplay files (lua)
	- This is the official featured FAF mod
	- This is the right place to work on balancing changes, game-lobby changes, unit behavior fixes/enhancements
	- The game communicates with the client using GPGNet-protocol
- [Client](https://github.com/FAForever/downlords-faf-client): FAF lobby client (java)
	- This is the FAF client featured on the website and the main user interface.
	- Instructions how to set up the client dev environment can be found on [Youtube](https://youtu.be/6gsHnt02I_Y?list=PL0nxuIUIjpFv6cjiaEwwVYpn3utdVUshc)
- [Server](https://github.com/FAForever/server): FAF lobby server (python)
	- The server is responsible for game hosting, rating calculation and ladder-matchmaking
- [JavaAPI](https://github.com/FAForever/faf-java-api): FAF restful Web-api server (java)
	- The api servers offers servers to authenticated users (via OAuth2)
	- Services are i.e. achievements, map upload, bug reports. 
	- As it's open for everybody, the service itself is not restricted to any client.You can find the ToS for the API [here](https://content.faforever.com/tos/api-tos.html)
- [Database](https://github.com/FAForever/db): FAF sql database (sql)
	- The database is the backend for server and api.
	- Instructions how to set up the db can be found on [Youtube](https://www.youtube.com/watch?v=3vsRs71vMII)

**All these projects have a readme which contains information how to use
it.** For further questions please ask for help in our Zulip chat.

## Developer tools

The following tools are strongly recommended for development (regardless of your operating system):
- [git](https://www.git-scm.com) 
	- Please follow our branching scheme.
	- Linux client should be available in your package manager
	- [Windows client](https://git-scm.com/download/win)
- [docker](https://www.docker.com/)
- a good IDE:
	- Python: [PyCharm](https://www.jetbrains.com/pycharm/) (free community edition)
	- Java: [IntelliJ IDEA](https://www.jetbrains.com/idea/) (free community edition)
  - Visual Studio Code

## Where to begin?

There are lots of starting points for new developers:
- Pick an issue from any of the [git projects](https://github.com/FAForever) and start working on it.
	- We recommend to check that the issue isn't solved already. If someone worked on it, you can usually see referenced commits in  the issue history.
	- If the situation is unclear, ask in Zulip.
- Bring up any topic in Zulip and offer to work on that.
	- The devs will give useful hints about your approach and tell you about possible conflicts.

## Lessons
- [Sources for FAF (Git and GitHub)](/FAF-Dev-School-Git)

## Other

Resources for working on FA modding (the game code):
- [Modding hints](/Modding)

- [AI Modding](/AI-Modding)

- [LUA-Docs](/Modding/LUADOC)

## First Time Guide

If you've not done any coding before, or have no idea where to start then this is the guide for you!

The most important thing to do if we want to play with the FAF code is get a GitHub account, see the lesson on that: [Github for FAF](/FAF-Dev-School-Git)

Once you've got a GitHub account set up, the next thing to do is to choose what FAF code you want to take a look at.