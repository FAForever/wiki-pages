---
title: Linux Installation
description: 
published: true
date: 2023-06-24T20:38:50.850Z
tags: 
editor: markdown
dateCreated: 2022-06-12T23:43:33.098Z
---

# Linux Installation

## Automated install

[FAForever/faf-linux](https://github.com/FAForever/faf-linux) provides a set of scripts to automate the installation of FAF on Linux. Please follow the instructions [here](https://github.com/FAForever/faf-linux/blob/master/README.md#setup-instructions).

It is recommended to use this over manual installation. The scripts set up a reproducible environment, allowing much easier troubleshooting.

## Manual install

**Warning**: The following guide is outdated. If you experience issues, please try installation with [faf-linux](https://github.com/FAForever/faf-linux). 

This guide is created with Ubuntu users in mind. However, with minor modifications, the instructions can be used for other distros. If you run into any undocumented issues or have any questions please join us on the FAF discord in #linux-support.

### Install the FAF client

Download the latest stable version of the client from [GitHub](https://github.com/FAForever/downlords-faf-client/releases).
```
curl -L -O https://github.com/FAForever/downlords-faf-client/releases/download/v2022.4.1/faf_unix_2022_4_1.tar.gz>
```

Extract it to a folder
```
mkdir -p ~/faf
```
```
tar -xf faf_unix_2022_4_1.tar.gz -C ~/faf/
```

Try to run the client
```
~/faf/faf-client-2022.4.1/faf-client
```

Note the minimum required JVM version in the error message. This may be different depending on the client version you are installing.
```
No suitable Java Virtual Machine could be found on your system.
The version of the JVM must be at least 17.
Please define INSTALL4J_JAVA_HOME to point to a suitable JVM.
```

Install a compatible Java Runtime Environment. If needed you can download and manually install a compatible version from [Adoptium](https://adoptium.net/temurin/releases)
```
sudo apt install openjdk-17-jre
```

Create a desktop run file:
```
vim ~/.local/share/applications/faf-client.desktop
```
```
[Desktop Entry]
Name=FAF
Version=v2022.4.1
Type=Application
Exec=bash -c "cd ~/faf/faf-client-2022.4.1; INSTALL4J_JAVA_HOME=/usr/lib/jvm/java-17-openjdk-amd64 ./faf-client"
Comment=Forged Alliance Forever Client
Icon=~/.local/share/icons/faf.png
```

Search for "FAF" in the applications menu, you should be able to run the client from there.

***
### Install Supreme Commander: Forged Alliance from Steam


#### **Make sure steam is installed**
 (```sudo apt install Steam``` to install if needed)

#### **Install and configure Supreme Commander Forged Alliance on Steam**

1. Start by enabling SteamPlay in the Steam settings. Reboot Steam for the changes to take effect. The option is found at `Steam -> Settings -> Steam Play -> under Advanced -> "Enable Steam Play for all other titles"`

2. Install Supreme Commander: Forged Alliance

3. Set the following launch options to the steam settings for Forged Alliance under `Properties -> Set Launch Options:
```
WINEDLLOVERRIDES="d3d9=n" PROTON_NO_ESYNC=1 PROTON_DUMP_DEBUG_COMMANDS=1 %command%
```

#### **Install video and audio libraries for Forged Alliance using protontricks:**

Install protontricks
```
sudo apt install protontricks
```

Then install the libraries
```
protontricks 9420 dlls d3dx9 xact
```

#### **Run Forged Alliance from Steam. The game will not open, this is expected.**
This Creates the run script used in the next step.
 <br>


#### **Copy the generated run file to your faf client install directory**
```
cp /tmp/proton_$USER/run ~/faf/
```
#### **Open the FAF client settings and set the command line executable format to:**
```
/home/<your_username>/faf/run "%s"
```

![here](https://i.imgur.com/ZlApelO.png)

#### **Download and use DGVoodoo's D3D9.dll**

Download
```
curl -L -O http://dege.freeweb.hu/dgVoodoo2/bin/dgVoodoo2_79_1.zip
```
Extract
```
unzip dgVoodoo2_79_1.zip
```
Move to FAF bin
```
cp dgVoodoo2_79_1/MS/x64/D3D9.dll /home/$USER/.faforever/bin/
```
Optional: Remove the DGVoodoo watermark
```
wine /home/$USER/Downloads/dgVoodoo2_79_1/dgVoodooCpl.exe
```
After the GUI opens, set the Running Instance to your faf bin 

![faf bin location](https://i.imgur.com/akLHAsa.png)

Next, select the DirectX tab and uncheck the `dgVoodoo Watermark` button

![settings](https://i.imgur.com/AVToHre.png)


If you would like to be able to run the game from Steam directly you must also copy the `D3D9.dll` into your Steam bin directory. If you chose not to, running the game from Steam will continue to crash due to the lack of the dll.




***

### Potential Solutions to Issues
#### Stuttering when launching the game, viewing the scoreboard, or watching coop dialogue
- Add `/nomovie` launch option to your command line executable. If you have Fsync in your launch options you do not need this. It should look like this:
```
/home/<your_username>/faf/run "%s" /nomovie
```
- Add `PROTON_NO_FSYNC=1` to your steam launch options, rerun FA from Steam, and then recopy your run script. **This is not recommended as some have reported this causing the game to not display any graphics**. If you have /nomovies in your executable you do not need this. Your launch options would look like this:
```
WINEDLLOVERRIDES="d3d9=n" PROTON_NO_ESYNC=1 PROTON_NO_FSYNC=1 PROTON_DUMP_DEBUG_COMMANDS=1 %command%
```

#### Black Screen when attempting to launch a game from FAF

- If you are Arch you need to install the `bubblewrap-suid` package **and** run ProtonGE through AUR package `proton-ge-custom-bin` or with the instructions below.
- Try using ProtonGE. Instructions can be found [here](https://github.com/GloriousEggroll/proton-ge-custom#installation). Once it is installed, rerun FA from Steam, then recopy your run script.
- Confirm your DGVoodoo version is greater than 2.79.1
