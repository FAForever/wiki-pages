---
title: Setting up the Client on Windows & Linux
description: 
published: true
date: 2022-01-23T23:21:58.037Z
tags: 
editor: markdown
dateCreated: 2021-11-02T17:53:26.781Z
---

# Windows
Setting up the FAF client is very easy and FAF itself requires almost no setup after it has been installed.

**As a general rule, you do not need any external links to mods or enhancements!** The reason for this is: **The FAF client automatically manages all mods and maps for you!** So you simply need to consult the [Map & Mod Vault](/Map-&-Mod-Vault).

There are also some mods integrated directly into FAF, which can be found [here](/Game-Modifications-(Mods)).

## Installing The Client and Forged Alliance
- (OPTIONAL) : If you own a physical box copy of EITHER Supreme Commander (base game) or Forged Alliance (expansion), EITHER code activates both titles on steam. This means that if you own both Supcom & FA boxes, you can actually give one of these codes to a friend and they'll also get the Supcom Gold game (with the FA expansion) unlocked on steam.
- If you do not already own it, Supreme Commander: Forged Alliance can be found on the [Steam store](http://store.steampowered.com/app/9420/) or other places.
- To install the FAF client, download it from [here](https://www.faforever.com/client) and run the installer. 
- Once the game and client are installed, run Forged Alliance once to create a profile in it, then close it.
- Start the FAF client and go to the Play tab, then [host a game](/Host-and-join-games). This will start the patching process and once the host game dialog appears, you can host a game, or close it to join another game.
	- It patches the game separately from your current installation. That means that you can continue to use your original game and FAF concurrently – they do not “overwrite” each other.
	- FAF might ask you to specify the Forged Alliance folder so just simply direct it to your *Supreme Commander: Forged Alliance* folder on your hard drive. If you bought Supreme Commander: Forged Alliance on Steam, the game is located in your Steam Library folder. To find that folder, start Steam, go to Steam - Settings, click Downloads, and click the STEAM LIBRARY FOLDERS button. The Steam Library folder has a folder steamapps\\common, there you should find your Supreme Commander Forged Alliance folder.
- Your setup is now completed, but you may wish to add more to your experience by downloading [Map & Mod Vault](/Map-&-Mod-Vault), but normally, any game you join, the mods and maps will be downloaded automatically, so you don't need to do anything else.

## Linking to Steam

The FAF client includes a feature to link your account to your Steam account. This feature enables you to swap two Steam linked accounts on the same computer, to bypass the anti-smurf protection. For this to work you are required to have Supreme Commander: Forged Alliance in your Steam library. You can link your account to Steam [here.](https://www.faforever.com/account/link)

## Installing Mods

Some popular mods, like [GAZ_UI](/Mods/GAZ_UI) and Hotbuild, are already [integrated](/Game-Modifications-(Mods)#Integrated-Mods) and require no installation - simply enable their features in-game.

All other mods can be found in the [mod vault](/Map-&-Mod-Vault#mod-vault), and can be used according to preference.

# Linux (Un-Official Support )
**Please note that FAF dose not Officaly support the Linux version**

## Ubuntu

### Step 1

```
sudo apt install python3-pip python3-setuptools python3-venv pipx
```

### Step 2
```
pipx install protontricks
```

### Step 3
Enable Steam Play (Reboot Steam)

### Step 4
Install Supreme Commander:Forged Alliance

### Step 5
Run :
```
cd ~/.local/pipx/venvs/protontricks
```
and
```
./protontricks 9420 dlls d3dx9
```
and
```
./protontricks 9420 dlls xact
```

### Step 6
Add these runs args to the settings in steam's FA :
```
PROTON_USE_WINED3D=1 PROTON_NO_ESYNC=1 PROTON_DUMP_DEBUG_COMMANDS=1 %command%
```

### Step 7
Run Forged Alliance, create config, close.

### Step 8
Create a "FAF" folder in which you want to extract FAF Client , [JRE 15](https://adoptopenjdk.net/archive.html?variant=openjdk15&jvmVariant=hotspot) and the run file you just generated located at /tmp/proton_$USER/ (in which you edit out steam.exe)

### Step 9
Create a desktop run file:
```
#!/usr/bin/env xdg-open
[Desktop Entry]
Version=v2021.11.0
Type=Application
Exec=bash -c "cd ~/faf; export INSTALL4J_JAVA_HOME=~/faf/jre-15/; ./faf-client"
Name=FAF
Comment=Forged Alliance Forever Client
Icon=~/.local/share/icons/faf.png
```
mark it as executable and place it in ~/.local/share/applications

### Step 10
hit start search for faf and run

### Step 11
in the settings, FAF tab add 
```
~/faf/run "%s"
```
 to the command line executable format input. 

## Any other Distro's
Their is also this Video if you need a visial aid.
<iframe src="https://www.youtube.com/watch?v=Rv3ZXA4FNFk" title="Tasu FAF Linux Install Guide"></iframe>

You will need to adapt Step 1 & Step 9 if you are unsure please ask on the FAF Discord in #Technical-Help
