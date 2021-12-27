---
title: Reporting Technical Issues
description: 
published: true
date: 2021-12-27T08:25:43.942Z
tags: 
editor: markdown
dateCreated: 2021-12-27T08:25:43.942Z
---

# Reporting Technical Issues

## Where to find things that need testing?
The best place is probably the [Discord](https://discord.gg/DhVGHzhcjF) channels related to testing. You can also subscribe to the Tester role by typing "!subscribe Tester" anywhere on the FAF Discord. You will then be notified for things that need testing in the #faf-testing-announcement channel.
Before starting

- Locating the log folder:
	- Open your File Explorer -> Open the "View" tab -> Make sure the Tick Boxes for "Hidden items" and "File name extensions" are enabled
	- Navigate to `C:\ProgramData\FAForever\logs\`
- You need to post at least two logs :
	- downlords-faf-client.log
		- forever.log (in case you use the legacy client)
	- game.log (the log from FA - rewritten after each game, so post just after having a problem !)
		- replay.log is the log outputted after watching a replay. Can eventually replace game.log if a replay replicate a problem.
- Don't copy paste the content of your log files into the text field of a Forum Post -> use the Upload Attachment feature instead
	- Alternatively you can also upload your log files to Pastebin and post a link to your paste.

## In-game problems
- Try disabling all mods to see if any mod is causing the issue.
- If it's a bug/glitch, post a SHORT SANDBOX game replay replicating it, your logs, and how to replicate it.
- Check who has the problem in game (ren_shownetworkstats in the console), look at the bottleneck if the game is freezing.
- Ask these persons to check for a local replay (if it's an in-game problem).
- Post names and replays (yours, and the person who has problems) here.

In case of the replay is not available, post a game id (the number on the livereplay/replay link).

## Replay problems
- Enable the logs.
- Post the replay.log file (see previous sections).
- Post the replays.

In case of the replay is not available, post a game id (the number on the livereplay/replay link). You can attach your replay in the forum (attachment option when posting). The replay is located in the replay vault, local replay, right click on it, show in explorer.

## Problems with The Client
Make a detailed report with a log file on GitHub, the forums or discords technical help channel.
- [Discord](https://discord.gg/DhVGHzhcjF)
- [GitHub](https://github.com/FAForever/downlords-faf-client)
- [Forum](https://forum.faforever.com/)

Reporting issues correctly is very important! Without all that, We can't debug and solve any problems!