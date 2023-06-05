---
title: FAF Dev School Git
description: 
published: true
date: 2023-06-05T12:05:55.049Z
tags: 
editor: markdown
dateCreated: 2021-08-31T09:43:03.960Z
---

# FAF Dev School Git
This lesson is all about the Git - a version control system that FAF uses to manage it's codebase.

We're going to do an example run through of how to make changes to the code and get them into the main repository.

### What's the point

First things first - what is git, and why do we use it?

This is a good question; the short answer is that Git enables multiple people to work on something at the same time in a sensible way. If you want the long answer there's plenty of people on the internet who can explain in depth the virtues of version control systems better than I can :).

### Setting up GitHub

GitHub is service for using the git version control system (and more), which FAF uses to manage its codebase. To make changes to any of the FAF code we'll need a GitHub account.

To get a GitHub account simply go to their signup page: [1](https://github.com/join)

To install Git, simply follow the instructions on their help pages: [2](https://help.github.com/articles/set-up-git/)

Their help pages will contain all the following information and more, so this guide is just here to help you spend less time worrying about Git so you can spend more time playing with the code.

Another good Git guide: [3](https://www.atlassian.com/git/tutorials/)

### Forking the code

Now we've installed GitHub, we can get to the business of getting our hands on FAF's code.

First we need to make a fork of the code that we want to work on. This fork is like our own version FAF's code that we can make changes to without needing anyone else's permission. To make a fork, go to the relevant webpage on GitHub (e.g. [4](https://github.com/FAForever/client), making sure you're signed in) and hit the fork button. This creates our version of the code, which we can now download.

To download, first launch the GitHub desktop client. Then browse to your GitHub profile and select the repository we just forked, it should appear on a list on the left. At this point we can click the "Save to computer" button (located next to the Download Zip button). This button will download the code and automatically load it into your GitHub desktop client.

We should now be ready to go!

### Making Changes

**IMPORTANT: From this point onwards, the commands will only work if you've got a copy of FAF code on your machine**

To get started, we'll want to open a new branch. A branch is like a fresh copy of the code that you can safely make changes onto without spoiling the original. Even if everything goes horribly wrong, you can switch back to the original branch and everything will be working again :)

To do this run:

`   git branch `<branch_name>

from your git shell.

Replace <branch_name> with the whatever name you would like your branch to have. In general this should be a description of the kind of changes you want to make. For the rest of this step, we'll assume we called it example_branch;

`   git branch example_branch`

Now we need to move over onto our new branch, to do that run the command:

`   git checkout example_branch`

You can do both creation of the branch and moving to the new branch in a single command aswell, by using '-b' (branch):

`   git checkout -b example_branch`

Now we can edit stuff to our hearts content! Open up the source code with your favourite editor, and make the changes you want. An important thing to mention here is that you probably want to be able to run the code you're editing, to make sure you spot any bugs that you accidentally introduce (it happens to everyone).

### Saving Changes

Once we've made changes we need to commit them to the branch. First we add the files we want to commit using the git add command. For example if I had edited *src/client/_clientwindow.py* in the FAForever/client codebase, I would run the command:

`   git add src/client/_clientwindow.py`

Do this for each source file that you want to save the changes for. 

Now we're ready to make the commit, and you can do this using the command:

`   git commit -m `<commit_message>

This makes a save of all the changes you added, and records the commit message that (hopefully) can let others know what you were trying to do with the changes. This makes it much easier when you're trying to get your code reviewed by others.

Sometimes a small commit message won't be enough to cover the entire scope of a commit. You can add a commit body in which you can describe your changes in a longer format.

`   git commit -m `<commit_message>` -m `<commit_body>

Alternatively, you can do all this in the git gui; when you open it open there should be a list of files that you've changed and a panel to show what changes you've made. Select the tick box next to each file that you intend to commit, fill in the commit info on the bottom left, and then hit the Commit button to commit. I'd recommend this method generally as its easier to see what changes you've made, and its a bit prettier too :)

Repeat the process of committing to your branch each time you make some changes (you only need to make a new branch the first time) until you're happy that you've completed all the changes you want to upload to GitHub.

### Uploading Changes

First thing to check is whether anyone else has made changes to the main repo while we were. To do this run the command:

`   git rebase FAForever/develop`

Hopefully there won't be any problems, and it will update to the latest version nicely. If there have been some conflicting changes, then it will walk you through how to sort it out.

Now we want to put our code online. To do this, run:

`   git push`

If you've not pushed this branch before then it'll tell you there isn't any upstream branch set. In this case, use the command it suggests, which is:

`   git push --set-upstream origin example_branch`

You'll only have to do this the first time.

We can also use the git gui instead of the git push command, once you've committed and rebased your changes then you can use the Publish/Sync button in the top right (Publish button if you've not pushed it yet, Sync if you have already pushed or published it).

### When things go wrong

Things might go wrong when you're using git, it happens to everyone. 
Here's some handy hints for what to do:

Step 1) Don't panic, its (probably) not the end of the world. GitHub has evolved loads since it was first created, and in that time there's been loads of things done to make sure you don't lose your work even when the unthinkable happens.

Step 2) If you're not sure what to do, ask someone. There's lots of friendly people around who can help, a good place to start is our dedicated chat channel in FAF.

Some other quick commands to fix little things:

`   git reset HEAD~1`

This command undoes the last commit you made. It keeps all of your changes, but removes the commit so you can tweak things to be nicer before you re-commit them. You can increase the number of commits you roll back by changing the 1 to whatever number you like.

`   git reset --hard HEAD~1`

This command undoes the last commit you made AND discards all the changes you made in the commit, as well as any uncommitted changes. Careful when using this as you could lose your work permanently.

`   git status`

This prints out in the command line a list of files that have changed, as well as other useful info. I highly recommend using this command regularly, its really handy to check how things are going. 

### Making a Pull Request

A Pull Request is the means by which your code gets into the main FAF repository. To make the PR (Pull Request), log into your GitHub account online and navigate to the branch you want to add. Then, click the "Compare & pull request" button.

It'll open up a page asking for a title and message to go with you PR. Use these to explain what your code does, and how it does it. These are what people will look at first when reviewing your changes so they know what you're trying to achieve. When you're happy you're done, click the "Create pull request" button.

At this point you just have to wait a bit for someone to check your code. They'll probably add some comments on the pull request and discuss the changes you've made, so make sure to keep checking its progress. They'll help spot any bugs you might have missed, or suggest ways to improve the code you've added.

Once they're happy your code is up to scratch it will get added to the repository. Well done on a successful contribution!