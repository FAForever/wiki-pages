# Lesson 1

This lesson is focussed on setting up a development environment to run
the **FAF Client** code in.

**NOTE: This guide is valid for the codebase as of 25/10/2015, so might
not be perfect for the current codebase!**

## Step 1: Getting a Dev Environment

This is all about using Vagrant to set up your dev environment inside a
virtual machine. If you don't want to do dev on a virtual machine then
you'll have to install the libraries on your main computer.

So first off we want to set up our dev environment, so we can run the
code and make changes. Theres a few things we'll need:

`   1) Github Account - `[`https://github.com/`](https://github.com/)
`   2) Our own fork of the repository - `[`https://github.com/FAForever/client`](https://github.com/FAForever/client)
`   3) Vagrant - `[`https://www.vagrantup.com/`](https://www.vagrantup.com/)
`   4) VirtualBox - `[`https://www.virtualbox.org/`](https://www.virtualbox.org/)

I also recommend getting the GitHub client, its a super handy tool for
managing your changes to the code with a pretty UI :) -
<https://desktop.github.com/>

Once you've forked the code online, you can download it locally from the
GitHub desktop client. In the top left there is a + symbol, select it
and then click clone. From there select the client repository to
download it.

Next we open up a git shell (to do this from desktop client, right click
the client repository, it should appear on the left, and select open in
git shell), and type the command: vagrant up This runs a virtual machine
where we can run the code in the same environment as everyone else. That
should mean we don't have any problems :)

If you have a problem running this command, make sure you're in the
right directory, you should be in the "client" folder.

Once the virtual machine is up and running, we just need to do 2 things:

`   1) Install sip`
`   2) Run the code`

For some reason sip doesn't come as standard in the VM, but we can
easily fix that ourselves. From the VM download
<https://riverbankcomputing.com/software/sip/download> and unzip it.
Then double click on the configure.py inside it to set it up (you may
have to double click twice).

To run the code, open up a powershell; you should see the icon for this
on the taskbar. Then run these two commands:

`   cd C:\vagrant`
`   C:\Python27\python.exe src`

The code *should* run and we're away :)

PS if its not working (and it probably won't be for weird reasons):

To fix run the commands:

`   cd C:\vagrant`
`   C:\Python27\python.exe C:\Python27\lib\site-packages\pip uninstall enum`
`   C:\Python27\python.exe C:\Python27\lib\site-packages\pip install requirements.txt`

Install: <http://www.microsoft.com/en-gb/download/details.aspx?id=5555>

Edit the return line (line 100 at last check) of the get_git_version()
in src/config/version.py to: return "0.11.3" instead of: return version

Comment out lines 1 and 15 to 20 in file src/fa/init_file.py

Try running again with the command: C:\\Python27\\python.exe src

------------------------------------------------------------------------

## Step 2: Git is our friend

This step is all about the basic git commands we'll use to make our
changes in a controlled way. This helps lots of people work together at
the same time without getting in each others way.

We're going to do an example run through of how to make changes to the
code and get them into the main repository. At this point, I'm assuming
you have a git account and git gui as described in step 1. Also you''ll
need your dev environment working so that you can check your changes
work, and you don't have any typos or so forth.

First step: open up a git shell in the client code directory. You can do
this easily from the git gui by right clicking "client" on the left and
selecting "open in git shell"

This is the shell from which we can now run all our other git commands.

### Making Changes

To get started, we'll now want to open a new branch. A branch is like a
fresh copy of the code that you can safely make changes onto without
spoiling the original. Even if everything goes horribly wrong, you can
switch back to the original branch and everything will be working again
:)

To do this run:

`   git branch `<branch_name>

from your git shell.

Replace <branch_name> with the whatever name you would like your branch
to have. In general this should be a description of the kind of changes
you want to make. For the rest of this step, we'll assume we called it
example_branch;

`   git branch example_branch`

Now we need to move over onto our new branch, to do that run the
command:

`   git checkout example_branch`

Now we can edit stuff to our hearts content! Open up the source code
with your favourite editor, and make the changes you want. We'll cover
what different source files do in the next step, for now we're going to
move on to how we save the changes once we've got them.

### Saving Changes

Once we've made changes we need to commit them to the branch. First we
add the files we want to commit using the git add command. For example
if I had edited src/client/_clientwindow.py I would run the command:

`   git add src/client/_clientwindow.py`

Do this for each source file that you want to save the changes for.

Now we're ready to make the commit, and you can do this using the
command:

`   git commit -m `<commit_message>

This makes a save of all the changes you added, and records the commit
message that (hopefully) can let others know what you were trying to do
with the changes. This makes it much easier later when you're trying to
get your code reviewed by others.

Alternatively, you can do all this in the git gui; when you open it open
there should be a list of files that you've changed and a panel to show
what changes you've made. Select the tick box next to each file that you
intend to commit, fill in the commit info on the bottom left, and then
hit the Commit button to commit. I'd recommend this method as its easier
to see what changes you've made, and its a bit prettier too :)

Repeat the process of committing to your branch each time you make some
changes (you only need to make a new branch the first time) until you're
happy that you've completed all the changes you want to upload to
GitHub.

### Uploading Changes

First thing to check is whether anyone else has made changes to the main
repo while we were. To do this run the command:

`   git rebase FAForever/develop`

Hopefully there won't be any problems, and it will update to the latest
version nicely. If there have been some conflicting changes, then it
will walk you through how to sort it out.

Now we want to put our code online. To do this, run:

`   git push`

If you've not pushed this branch before then it'll tell you there isn't
any upstream branch set. In this case, use the command it suggests,
which is:

`   git push --set-upstream origin example_branch`

You'll only have to do this the first time.

We can also use the git gui instead of the git push command, once you've
committed and rebased your changes then you can use the Publish/Sync
button in the top right (Publish button if you've not pushed it yet,
Sync if you have already pushed or published it).

### When things go wrong

Things might go wrong when you're using git, it happens to everyone.
Here's some handy hints for what to do:

Step 1) Don't panic, its (probably) not the end of the world. GitHub has
evolved loads since it was first created, and in that time there's been
loads of things done to make sure you don't lose your work even when the
unthinkable happens.

Step 2) If you're not sure what to do, ask someone. There's lots of
friendly people around who can help, a good place to start is our
dedicated chat channel in FAF.

Some other quick commands to fix little things:

`   git reset HEAD~1`

This command undoes the last commit you made. It keeps all of your
changes, but removes the commit so you can tweak things to be nicer
before you re-commit them. You can increase the number of commits you
roll back by changing the 1 to whatever number you like.

`   git reset --hard HEAD~1`

This command undoes the last commit you made AND discards all the
changes you made in the commit, as well as any uncommitted changes.
Careful when using this as you could lose your work permanently.

`   git status`

This prints out in the command line a list of files that have changed,
as well as other useful info. I highly recommend using this command
regularly, its really handy to check how things are going.

### Making a Pull Request

A Pull Request is the means by which your code gets into the main FAF
repository. To make the PR (Pull Request), log into your GitHub account
online and navigate to the branch you want to add. Then, click the
"Compare & pull request" button.

It'll open up a page asking for a title and message to go with you PR.
Use these to explain what your code does, and how it does it. These are
what people will look at first when reviewing your changes so they know
what you're trying to achieve. When you're happy you're done, click the
"Create pull request" button.

At this point you just have to wait a bit for someone to check your
code. They'll probably add some comments on the pull request and discuss
the changes you've made, so make sure to keep checking its progress.
They'll help spot any bugs you might have missed, or suggest ways to
improve the code you've added.

Once they're happy your code is up to scratch it will get added to the
repository. Well done on a successful contribution!

------------------------------------------------------------------------

## Step 3: Finding your way around the code

In Step 3 we'll go over what different files in the FAForever
repositories do. This is just a brief guide as things could move about
at any time - there's plenty of stuff in the wrong place until someone
gets around to finding it a new home.

### Client

This repository is what we've worked with in the first two steps, and
holds all the code to run the main FAF client. Its job is to integrate
all of the other FAF modules, from the website in the "What's new?" tab
to chat, leaderboards, and the managing of hosting and joining of games.