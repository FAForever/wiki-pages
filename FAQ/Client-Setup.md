---
title: Setting up the Client on Windows & Linux
description: 
published: true
date: 2022-05-29T18:58:52.824Z
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

## What is Steam link/GOG link, why is it required, and how do I do it?

Steam link/GOG link can be thought of as a one-time verification tool that allows us to make sure you own a legal copy of the game Supreme Commander: Forged Alliance.  Verification using either Steam link or GOG link is required to demonstrate proof of ownership ([for legal reasons](https://forum.faforever.com/topic/252/why-do-i-need-to-link-my-account-to-steam), as well as to reduce smurfing).  However, if you own a retail version of the game, but don't have it on Steam or GOG, you should be able to [use your CD key to redeem a licence on Steam for free](https://help.steampowered.com/en/faqs/view/0e71-0971-324a-1161).  Alternatively, if you don't own the game or need a new copy, you can [purchase it via Steam](https://store.steampowered.com/app/9420) or [GOG](https://www.gog.com/en/game/supreme_commander_gold_edition) to play on FAF.  If you own the GOG version of the game, you can [follow these linked instructions](https://www.faforever.com/account/linkGog).  Alternatively, once you have the game (Supreme Commander: Forged Alliance) in your Steam library, you can [link your account to Steam](https://www.faforever.com/account/link) (your Steam profile and games list will temporarily need to be [set to public](https://help.steampowered.com/en/faqs/view/588C-C67D-0251-C276) for this to work, but you can hide them again afterwards).  If you have concerns about this process, you can read [the technical explanation of why it's safe](https://forum.faforever.com/topic/279/the-steam-login-is-suspicious-are-you-stealing-my-account), and you can also note that FAF has an active community that can answer questions, FAF has existed for over a decade, FAF has had hundreds of thousands of users, and the FAF Association is a non-profit organization.

Common solutions to problems setting up Steam link:

* Double check that you used the correct Steam account that owns the game (and that you didn't automatically log in to the wrong account)

* Double check that you set both the Steam profile and its games list to public (make sure you check both)

* Double check that the game Supreme Commander: Forged Alliance (it must include Forged Alliance in the game name) is in the correct Steam library and owned by the correct Steam account

* Log out and then log back in with both your FAF account and your Steam account

*  If you already completed the Steam link process, make sure that you log in to the FAF account that you made the Steam link with (and not a different one that you made but didn't make the Steam link with)

If you experience issues setting up Steam link, you can ask for help in the  [#technical-help channel in the FAF Discord](https://discord.gg/rvfaGTpNbK) and or in the [help section of the forums](https://forum.faforever.com/category/4/i-need-help).

[Setting your Steam profile and games list to public:
![set_to_public.png](/images/set_to_public.png)](https://help.steampowered.com/en/faqs/view/588C-C67D-0251-C276)

## Installing Mods

Some popular mods, like [GAZ_UI](/Mods/GAZ_UI) and Hotbuild, are already [integrated](/Game-Modifications-(Mods)#Integrated-Mods) and require no installation - simply enable their features in-game.

All other mods can be found in the [mod vault](/Map-&-Mod-Vault#mod-vault), and can be used according to preference.

# Linux (Un-Official Support )
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

Install a compatible Java Runtime Environment. If none is available through apt you can download and manually install a compatible [AdoptOpenJDK one](https://adoptopenjdk.net/archive.html?jvmVariant=hotspot)
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
