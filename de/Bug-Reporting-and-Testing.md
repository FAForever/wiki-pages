---
title: Bug Reporting & Testing
description: 
published: true
date: 2021-12-29T23:59:34.451Z
tags: development
editor: markdown
dateCreated: 2021-08-31T09:42:21.423Z
---

## Where to submit bug reports

In general, all bug reports should be submitted as an issue on [github](https://github.com/FAForever). You need to register once with an email adress, which will be used to notify you about news on your bug report. There are lots of projects on [github](https://github.com/FAForever). The following guidelines should help you choosing the right project:
- Bugs on the website go to the [website issues](https://github.com/FAForever/website/issues)
	- i.e. broken or dead links
	- i.e. layout issues
- Bugs regarding ingame behavior go to the [fa issues](https://github.com/FAForever/fa/issues).
	- i.e. units nots firing
	- i.e. graphical glitches on menus or lobby
	- i.e. problems in the ingame lobby
	- For bug reports on mods other than FAF and FAF Beta please use the corresponding project or contact the original author.
		- [FAF coop issues](https://github.com/FAForever/fa-coop/issues)
		- [Phantom-X issues](https://github.com/FAForever/faf-phantomx/issues) 
- Bugs regarding the (Legacy) client go to the [client issues](https://github.com/FAForever/client/issues)
	- i.e. crashes of the client
	- i.e. problems downloading maps or mods
	- i.e. problems on joining games
- Bugs in Offical Client (Java) client go [here](https://github.com/FAForever/Downlords-faf-client/issues)
	- if you don't know which client you are using, it's probably the Offical client!
- Bugs on the server go to [server issues](https://github.com/FAForever/server/issues)
	- i.e. rating issues (unless it's a display issue of the client)
	- i.e. replays missing
	- i.e. login issues
- Bugs on the api go to [api issues](https://github.com/FAForever/api/issues)
	- *probably relevant for developers only*

If you don't know whether your bug needs to go to server, api or client, just post it in the client. The developers will close & reopen it in the right list.

## Guidelines for a good bug report

To fix a bug it is necessary to be able to reproduce the bug and to understand what is actually wrong.

To write a good bug report, please try to follow these questions:
1. In which version does the bug occur?
	- if ingame bug: are you using FAF Beta vs. standard FAF mod
	- if client bug: are you using the latest official release or a developer build (for developer builds please add the used branch and latest commit)
	- if server bug: which branch/commit are you using?
2. How can anybody reproduce the bug?
	- example: build a nuke and launch a missile
3. What behaviour have you observered?
	- example: there was no voice notification of the launch
4. What behaviour did you actually expect?
	- example: After launching the nuke, the game should play the sound "Nuke Launch detected"
5. *optional:* Elaborate a possible cause
	- example: the nuke launch is referenced with the wrong sound file
6. *optional:* Offer a possible solution
	- example: go to lua-file xxx and append the code yyy to the function zzz

## Testing bugfixes

### Testing website changes
- Ask a dev in slack to checkout a certain pull request on the test server
- Open [test.faforever.com](http://test.faforever.com) in your browser
- Check the change
- Give feedback in the pull request and/or on Slack

### Testing game mod changes

#### Setting up the dev init file

To test Pull Requests for the game code you will first need to set up a dev init file.

Navigate here: ```\`C:\\ProgramData\\FAForever\\bin\` ```

Create a new lua file called:``` \`init_faf_dev.lua\` ```

Open it and put inside [this code](http://pastebin.com/zt2x1gC6)

Change line 177 to fit your patch to ``` \`fa\` ```repository on your PC, for example `C:\\Users\\Admin\\Documents\\GitHub\\fa`

Create a desktop shortcut of ForgedAlliance.exe from ``` \`C:\\ProgramData\\FAForever\\bin\` ```

Right click the shortcut, go into Properties

In ``` \`Destination\` ``` add ``` \` /init init_faf_dev.lua\` ``` - or whatever youcalled that file

It should look like this: ``` \`C:\\ProgramData\\FAForever\\bin\\ForgedAlliance.exe /init init_coop.lua\` ```

Make sure you have a space in front of the \`/\`

In addition you can add \`/showlog\` to open a log at the beginning, or other things, more here: [Command Line Switches](/Command-Line-Switches)

#### Using git to test Pulls Requests

Once you have this done you are almost ready to begin testing PRs. You will need to [fork](https://help.github.com/articles/fork-a-repo/) the [FaForever fa repository.](https://github.com/FAForever/fa) Then you will need to configure your fork to [pull changes from the upstream.](https://help.github.com/articles/fork-a-repo/#step-3-configure-git-to-sync-your-fork-with-the-original-spoon-knife-repository)

When this is done you can test pull requests submitted to the fa repo using the following commands: \`git fetch upstream pull/PRID/head:*testBranch*\` - PRID is the number of the PR, *testBranch* is your very own name you choose for the branch that it will create.

'git checkout *testBranch*' - this will open the branch you just created with the PR you want to test. Run the game via the shortcut you made earlier and test the behaviour of the PR. 

Use 'git checkout *branchName*' to return to whatever branch you want, e.g. 'develop'

'git branch -D *testBranch*' will delete your test branch.

### Testing classic client
- Download the .msi-installer for a pull request from [appveyor](https://ci.appveyor.com/project/Sheeo/client/history)
	- Every pull request is built on appveyor. You will find it by looking for the commit-id (7 characters, like 'c9df39a').
- Login with the client
- Follow the reproduce-steps of the original issue and check whether it has been solved
- Give feedback in the pull request and/or on Slack

Some client changes require a corresponding change on server side.

### Testing server changes
- Ask a dev in slack to checkout a certain pull request on the test server
- Login with the client on the test server
	- download [1](https://pastebin.com/BeSCVczA) this paste as and remove the ".txt" file extention
	- run the file and choose the test server
- Follow the reproduce-steps of the original issue and check whether it has been solved
- Depending on the actual issue, multiple players may be required for testing
- Sandbox mode and cheating are recommended to reduce the time to setup the correct test case

## What can be tested?
- Every pull request in any of the github projects is a good candidate for testing.
	- Please read through the conversation of the pull request. This will give you an impression, whether the pull request is still in progress or ready for testing.
	- If unsure, ask the author of the pull request. 
- The changelog of projects offer topics for testing. 
	- Please ask in Slack chat about the progress of tests. 
	- **ToDo**: Provide links to the changelogs.
- The FAF beta mod is always open for testing. Just play it and open issues for new bugs.