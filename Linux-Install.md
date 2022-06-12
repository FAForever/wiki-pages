---
title: Linux Instalation
description: 
published: true
date: 2022-06-12T23:44:53.506Z
tags: 
editor: markdown
dateCreated: 2022-06-12T23:43:33.098Z
---

# Linux (Semi-Official Support )
**Please note that FAF does not officially support the Linux version**

## Ubuntu Quickstart
This quickstart guide shows you the commands you need for getting FAF installed with minimal explanation.

### Step 1 - Install the FAF client
Download the latest stable version of the client from the [GitHub](https://github.com/FAForever/downlords-faf-client/releases).
```
curl -L -O https://github.com/FAForever/downlords-faf-client/releases/download/v2022.4.1/faf_unix_2022_4_1.tar.gz
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

Install a compatible Java Runtime Environment. If none is available through apt you can download and manually install a compatible version from [Adoptium](https://adoptium.net/temurin/releases)
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

### Step 2 - Install Supreme Commander: Forged Alliance from Steam
1. Start by enabling SteamPlay in the Steam settings. Reboot Steam for the changes to take effect. The option is found at `Steam -> Settings -> Steam Play -> under Advanced -> "Enable Steam Play for all other titles"`

2. Install Supreme Commander: Forged Alliance

3. Set the following launch options to the steam settings for Forged Alliance under `Properties -> Set Launch Options`:
```
PROTON_USE_WINED3D=1 PROTON_NO_ESYNC=1 PROTON_DUMP_DEBUG_COMMANDS=1 %command%
```

4. Install video and audo libraries for Forged Alliance using protontricks:
Install python and pipx
```
sudo apt install python3-pip python3-setuptools python3-venv pipx
```
Then install protontricks
```
pipx install protontricks
```
Then install the libraries
```
~/.local/bin/protontricks 9420 dlls d3dx9
```
```
~/.local/bin/protontricks 9420 dlls xact
```
5. Run Forged Alliance, create a profile and exit

6. Copy the generated run file to your faf client install directory
```
cp /tmp/proton_$USER/run ~/faf/
```
7. Open the FAF client settings and set the command line executable format to:
```
~/faf/run "%s"
```

## Other Distros
There is also this [Video](https://www.youtube.com/watch?v=Rv3ZXA4FNFk) if you need a visial aid.

You will need to adapt some of the steps. If you are unsure please ask on the FAF Discord in #linux-support