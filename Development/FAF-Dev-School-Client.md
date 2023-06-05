---
title: FAF Dev School Client
description: 
published: true
date: 2023-06-05T12:05:28.864Z
tags: 
editor: markdown
dateCreated: 2021-08-31T09:43:02.150Z
---

# FAF-Dev-School-Legacy-Client
This lesson is all about the Git - a version control system that FAF uses to manage it's codebase.

We're going to cover how to run the code once we've downloaded it, and do a quick overview of what different parts of the code do. 

## The Easy Way

First thing to do is to make sure you've got yourself a GitHub account, and a local copy of the code at <https://github.com/FAForever/client>

For a guide to doing this, see the [lesson on GitHub](/FAF-Dev-School-Git)

We'll also need an install of python 2.7 **(32 Bit version)**, 'python' and 'pip' added to the system path, as well as PyQT **(version 4, 32 Bit)** installed from <https://riverbankcomputing.com/software/pyqt/download>

------------------------------------------------------------------------

At this point, I'm assuming you've got the GitHub Desktop client open and have successfully loaded the FAForever/client repository into it. 

Right click on the client fork (on the left side) and select "Open in Git Shell"

Before we do the next step we might want to edit the client/requirements.txt file, removing the line "lupa". This isn't actually needed in the code, and can save us some trouble trying to install it.

Now type the following command into the open shell window:

`   pip install -r requirements.txt`

This installs all the extra stuff we need to run the client. If you get an error that the pip command is missing, try installing pip via this python script: <https://pip.pypa.io/en/latest/installing/> and try the command metioned above again after installing pip.

To run the dev client, all we need to do now is run the command:

`   python src`

Now we've got the client running, we can start making changes and testing them to see what happens.

## Client Code Overview

appveyor/ - some fun stuff for turning the code into an executable (but not something we need to worry about)

lib/ - some external bits of code that FAF requires to run, again something we don't need to worry about.

res/ - this folder contains all the non-code materials that FAF uses. For example, the exact layout of the client window as well as things like colours and stylings are set in here. Everything in this folder is moddable using themes.

src/ - contains all the python code that FAF needs to run.

res/ and src/ are the two main areas of interest, each of these contain subfolders that contain files whose purpose matches the folder name. For example, the chat folder contains stuff relevant to the "Chat Lobby" tab.

More detail on the code to be added soon!

### Short Introduction to PyQt

The UI of the client is made with PyQt, the python bindings of the Qt toolkit. You will encounter PyQt in many places within the Code - be it the Definition of the UI itself, (Sub-)Classes related to PyQt or the way signals are used within the code. 

#### How does the FAF client UI work ?

First of: There is a WYSIWYG-editor called *Qt-Designer* for (Py-)Qt, it should be installed by default if you have PyQt installed. Secondly there are 2 main kinds of files that are used to create the UI, Files that end with *.ui* and stylesheet Files that end on *.css*. The *\*.ui* files define the general layout, for example whether there is a button in a certain window or not. There is one file that is responsible for the main window ( *res/client/client.ui*) and one *.ui* file for each of the main tabs, for example for the chat tab ( *res/chat/chat.ui*, this file defines a Widget which is then place in that tab to be more detailed), and several others for example for pop-ups etc. The *.ui* files use a some kind of xml derivate, so you can definately manually finetune them for example if Qt-Designer doesnt quite place UI-elements where you want them to be.

If you look at some of those *.ui* files with the Qt-Designer you will notice that while the general layout looks similar these files seem to be using some default windows skin for everything. This is where the stylesheet *.css* file(s) make a difference. With these file(s) you can customize the looks of UI-elements.

Btw, theming in FAF works by overiding the *.ui* or *.css* file which has the same relative path as the respective file of the theme. 

#### PyQt-Signals

There a quite a few signals used by the client, most of them are defined early on in the *ClientWindow* Class. These are created for example by *ourSignal = QtCore.pyqtSignal()*. There are 2 main interactions with a signal, you can connect a function to it by *ourSignal.connect(function1)*, and you can trigger the signal with *ourSignal.emit()*. Now if *ourSignal* gets triggered *function1* will be called. You can connect multiple functions to the same signal and also add Parameters when triggering that all connected functions then will get called with.

These signals are for example commonly used when the server sends a new message, all modules that are interested in said message connected one of "their" functions to this signal will now get the information the server just sent. This is what happens in most of the *handle_<commandname>* functions in the *_clientwindow.py* file. 

## The Hard Way

*This guide is an alternative method, and you don't have to do this is you were following the steps above.*

The hard way to run the client code is inside a separate VM managed by Vagrant, a tool for standardising the dev environments of different developers. In theory this should be the easy way; it should be pretty plug and play, and with everyone using it you all have the same problems and can help each other to solutions.

In practice, nobody seems to run the client code this way and there are some unresolved issues with the Vagrant setup (that can be worked around).

Here's a lesson I wrote in November 2015 for setting up the Vagrant environment:

## Step 1: Getting a Dev Environment

This is all about using Vagrant to set up your dev environment inside a virtual machine. If you don't want to do dev on a virtual machine then you'll have to install the libraries on your main computer. 

So first off we want to set up our dev environment, so we can run the code and make changes. Theres a few things we'll need:
`   1) Github Account - `[`https://github.com/`](https://github.com/)
`   2) Our own fork of the repository - `[`https://github.com/FAForever/client`](https://github.com/FAForever/client)
`   3) Vagrant - `[`https://www.vagrantup.com/`](https://www.vagrantup.com/)
`   4) VirtualBox - `[`https://www.virtualbox.org/`](https://www.virtualbox.org/)

I also recommend getting the GitHub client, its a super handy tool for managing your changes to the code with a pretty UI :) - <https://desktop.github.com/>

Once you've forked the code online, you can download it locally from the GitHub desktop client. In the top left there is a + symbol, select it and then click clone. From there select the client repository to download it.

Next we open up a git shell (to do this from desktop client, right click the client repository, it should appear on the left, and select open in git shell), and type the command: vagrant up This runs a virtual machine where we can run the code in the same environment as everyone else. That should mean we don't have any problems :)

If you have a problem running this command, make sure you're in the right directory, you should be in the "client" folder.

Once the virtual machine is up and running, we just need to do 2 things:

`   1) Install sip`
`   2) Run the code`

For some reason sip doesn't come as standard in the VM, but we can easily fix that ourselves. From the VM download <https://riverbankcomputing.com/software/sip/download> and unzip it. Then double click on the configure.py inside it to set it up (you may have to double click twice).

To run the code, open up a powershell; you should see the icon for this on the taskbar. Then run these two commands:

`   cd C:\vagrant`
`   C:\Python27\python.exe src`

The code *should* run and we're away :)

PS if its not working (and it probably won't be for weird reasons):

To fix run the commands:

`   cd C:\vagrant`
`   C:\Python27\python.exe C:\Python27\lib\site-packages\pip uninstall enum`
`   C:\Python27\python.exe C:\Python27\lib\site-packages\pip install requirements.txt`

Install: <http://www.microsoft.com/en-gb/download/details.aspx?id=5555>

If the client is telling you t upgrade, there may be a problem with the version number being returned. To fix, try editing the return line (line 100 at last check) of the get_git_version() in src/config/version.py to something else, for example "0.11.58".

Comment out lines 1 and 15 to 20 in file src/fa/init_file.py

Try running again with the command: C:\\Python27\\python.exe src