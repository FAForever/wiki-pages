This wiki article details the installation of the **Supreme Commander:
Forged Alliance game** and the **Forged Alliance Forever (FAF) clients**
on Linux.

## Contact

If you have questions please contact the community:

[FAF forum Linux support
thread](https://forum.faforever.com/topic/12/linux-support)
[The official FAF Discord Channel:
#technical-help](https://discordapp.com/channels/197033481883222026/202928463076786176)
- [Discord invite](https://discordapp.com/invite/hgvj6Af)

## About the game

Supreme Commander: Forged Alliance game runs under Linux using
[wine](https://www.winehq.org/).

`sudo apt install wine`

You only need the Supreme Commander: Forged Alliance game and the [#Java
Downlord's Client](#Java_Downlord's_Client "wikilink") to be able to
play in the FAF community. [The game is available on
Steam](https://store.steampowered.com/app/9420/Supreme_Commander_Forged_Alliance/).

## Install Supreme Commander: Forged Alliance

You can install the game with the following methods:

Using Linux Steam (RECOMMENDED For the Java client) [#Install using native Steam](#Install_using_native_Steam "wikilink")
Native Linux Steam can install the game and the necessary Windows DLLs,
libraries for running it.

Steam's compatibility tool (Proton/Wine) will be able to run the game.

Using Windows Steam via Wine
Windows Steam can install the game and the necessary Windows DLLs,
libraries for running it.

The disadvantage of this method is that you have to deal with Windows
Steam that has certain known bugs with Wine (logging in, downloading
games). You can manage to do it but it's a hassle.

Using Linux SteamCMD
It's basically the same as the first one but you have to install
[SteamCMD](https://developer.valvesoftware.com/wiki/SteamCMD) and know
SteamCMD commands.

Not recommended since native Linux Steam is much more convenient.

Using Windows SteamCMD via Wine
It's basically the same as the second one but you have to install
[SteamCMD](https://developer.valvesoftware.com/wiki/SteamCMD) and know
SteamCMD commands.

It can be less a hassle but certain Windows Steam bugs might still
appear.

Using Lutris
[Lutris](https://lutris.net/games/supreme-commander-forged-alliance/)
has a UI and uses SteamCMD (and your Steam account) to install Steam
games in a Wine environment.

Using retail copy of the game ISO, DVD via Wine
Just launch the install of the DVD in a Wine environment. You will have
to add the necessary Windows DLLs and libraries manually in Wine.

NOTE: When using the FAF clients, the clients will prompt you to link
your Steam account to FAF to prevent duplicated accounts and malicious
users joining the FAF community.

You will have to register the serial number of your game in Steam. This
means that illegal copies of the ISO will not work, in this case [buy
the game on
Steam](https://store.steampowered.com/app/9420/Supreme_Commander_Forged_Alliance/),
it's cheap.

------------------------------------------------------------------------

### Install using native Steam

#### Set your Steam client

Steam -> Settings -> Steam Play -> under Advanced -> "Enable Steam Play
for all other titles"

#### Install the game, set launch options

Set the following launch options, then start the game from Steam

Properties -> Set Launch Options -> set this:

`PROTON_NO_ESYNC=1 PROTON_DUMP_DEBUG_COMMANDS=1 %command%`

PROTON_NO_ESYNC will solve slow video playback problems in the main menu
and other places.
PROTON_DUMP_DEBUG_COMMANDS will generate a RUN script for your game that
you will be able to use later.


Properties -> Force the use of a specific Steam Play compatibility tool:

`Proton 5.0-9 (recommended)`
`Proton 4.11-9 `
`Proton 3.16-9 `
`Proton 3.7-8`

Proton 4.2-9 causes desync issues during playing the game.


Proceed with the installation of the Java Client after this. [#Java
Downlord's Client](#Java_Downlord's_Client "wikilink")

#### File Locations

Game directory:

`~/.steam/steam/steamapps/common/Supreme Commander Forged Alliance/`

Game perf file:

`~/.steam/steam/steamapps/compatdata/9420/pfx/drive_c/users/steamuser/Local Settings/Application Data/Gas Powered Games/Supreme Commander Forged Alliance/Game.prefs`

WINEPREFIX:

`~/.steam/steam/steamapps/compatdata/9420/pfx`

------------------------------------------------------------------------

### Install using SteamCMD

You can download FA using a steam installation in wine. The following
steps describe how to download FA using
[steamcmd](https://developer.valvesoftware.com/wiki/SteamCMD) on Arch
Linux:

Install steamcmd:

`yaourt -S steamcmd`

Now you need to run steamcmd once as root to let it install its updates:

`sudo steamcmd`

now run steamcmd as your normal user to download your copy of FA and run
the following commands in its shell:

`login [my_steam_username]`
`@sSteamCmdForcePlatformType windows`
`force_install_dir [my/desired/installlocation]`
`app_update 9420 validate`

------------------------------------------------------------------------

### Install using the retail ISO

Just launch the setup from the CD (ISO).

#### After installation

Run

`winecfg`

and enable "emulate virtual screen" option in graphics tab and enter you
display resolution.

After installation run the game without the client, setup graphics and
make sure everything works like sound etc. The bloom renderer graphics
setting may not work. If the game does not start again, delete the
[#Game.prefs](#Game.prefs "wikilink")

If the game crashs with the following error:

`CD3DDeviceResources::DevResInitResources: Unable to load effect file /effects/cartographic.fx`

install d3dx9 using winetricks:

`winetricks dlls d3dx9`

If you have no sound install xact audio:

`winetricks dlls xact`

#### File Locations

##### Game.prefs

Your game.prefs contains all game settings, like graphics settings,
keybindings and active UI mods. It is located at

`~/.wine/drive_c/users/USER/Local Settings/Application Data/Gas Powered Games/Supreme Commander Forged Alliance/Game.prefs`

but this path depends on your WINEPREFIX and probably on the Windows
version you set up in wine.

## Java Downlord's Client

Please [#Contact](#Contact "wikilink") the community for more
information.

### Script Installation

You can find a FAF Installer in
[Lutris](https://lutris.net/games/forged-alliance-forever/).
Informations are available in our
[forum](https://forum.faforever.com/topic/1657/linux-install-script-lutris).

There is also a bash script for installing everything you need
(including the game itself). It works on Ubuntu and other distributions
as well: [installFAFscript](https://github.com/tatsujb/installFAFscript)

Nowadays the script is rarely updated so the manual install method is
recommended instead (just a few steps).

*Note: that this script upgrades your Ubuntu distribution (ex: 18.10 ->
19.04).*

### Manual Installation

The followings are a step by step example installation on Ubuntu 20.xx,
it's built upon a native Steam installation of the game.

#### Download the Java FAF client

Download the latest Java FAF client
**URL:** <https://github.com/FAForever/downlords-faf-client/releases>
**File name:** dfc_unix_1_3_0.tar.gz
Extract it to \~/Games

#### Install JAVA 15

Install Java 15 Runtime Environment (JRE) or Development Kit (JDK)

`sudo apt install oracle-java15-installer`

*Note: Java installs to: /usr/lib/jvm/java-15-oracle (we will use this
path later)
*Note: The client doesn't work with other Java versions.''

#### Set execute flags

Open a terminal and set execute flags for the following files (if they
don't have already).

`cd ~/Games/downlords-faf-client-1.3.0/`
`sudo chmod +x downlords-faf-client`
`sudo chmod +x ./natives/faf-uid`

#### Set INSTALL4J_JAVA_HOME

In the same terminal, set the INSTALL4J_JAVA_HOME environment variable

`export INSTALL4J_JAVA_HOME=/usr/lib/jvm/java-15-oracle`

At this point you should be able to run the FAF client. Please test
this:

`./downlords-faf-client`

''Note: You will need to set the INSTALL4J_JAVA_HOME environment
variable every time you open a new terminal. It is possible to create
your own bash script for starting the client or to append the export
command to your
[.bashrc](https://unix.stackexchange.com/questions/129143/what-is-the-purpose-of-bashrc-and-how-does-it-work)
file. Alternatively, you can edit the 'downlords-faf-client' shell
script and add the 'export
INSTALL4J_JAVA_HOME=/usr/lib/jvm/java-15-oracle' command at the top of
the file.

#### Copy the Steam RUN script

If you ran the game from Steam you should have a file called "run" in
/tmp/proton_your_linux_username. The tmp directory is only temporary so
copy this file to somewhere nice.

`cp /tmp/proton_your_linux_username/run ~/Games/downlords-faf-client-1.3.0/`

If you cannot find the run file, please check your Steam settings again.
[#Install the game, set launch
options](#Install_the_game,_set_launch_options "wikilink")

*Note: This file contains the environment variables for Proton that are
necessary to launch the game in a Proton/Wine environment. It also
contains the version of Proton that you have selected previously in
Steam. The FAF client will use this file to launch the game after we set
it.*

### Client Setup

Launch the FAF client

`./downlords-faf-client`

#### Settings

##### Set File Locations

Client: Settings / Forged Alliance Forever /

Game location:

`/home/your_linux_username/.steam/steam/steamapps/common/Supreme Commander Forged Alliance`

Advanced, Command line format for executable:

`/home/your_linux_username/Games/downlords-faf-client-1.3.0/run "%s"`

*Note: The run file mentioned here is the run file you copied earlier
from the Steam temporary directory.*

Execution directory:

`Leave this empty`

##### Use fallback vault location

<small>(obsolete for version 1.3.0?)</small>
Set "Use fallback vault location" in the client settings.

Without it, your custom downloaded maps and mods won't show up in the
client and the game.

`General / Use Fallback vault location`

##### Create a game

Try to create a game and wait for the client to patch the FAF
executable. At this point everything should work.



### File Locations

Configuration directory for the client
It contains logs, *client.prefs* the configuration file of the client,
etc...

`~/.faforever`

*Note: The client.prefs file contains your username and password.*

Location of mods and maps downloaded by the client
Use [#Use fallback vault
location](#Use_fallback_vault_location "wikilink")!

`~/.faforever/user/My Games/Gas Powered Games/Supreme Commander Forged Alliance`

The script that launches the client: *downlords-faf-client*

`~/Games/downlords-faf-client-1.3.0/downlords-faf-client`

## Issues with the game

### The FAF client doesn't launch the game

When you double click on lobbies in the Java FAF client, the game
doesn't start. If you installed the game using Steam then you need to
have Steam running in the background. Just open Steam and try again.

When Steam is not running then you get this error in the terminal:

`[S_API] SteamAPI_Init(): SteamAPI_IsSteamRunning() did not locate a running instance of Steam.`
`[S_API FAIL] SteamAPI_Init() failed`

### No sound when the game is minimized

No sound when the game is minimized or running in the background.

Solution:
Run winecfg and configure your Proton/wine or vanilla Wine.

`export WINEPREFIX="/home/your_linux_user_name/.local/share/Steam/steamapps/compatdata/9420/pfx/"`
`winecfg`


Graphics -> "Emulate a virtual desktop" -> Desktop Size: your native
resolution

### Mouse cursor flickering

The mouse cursor flickers/disappears.

Solution:

-   Enable vertical sync (on/off) in the game's settings
-   Run the game, open the game's console and issue command:
    d3d_WindowsCursor. This command has to be executed every time you
    start a game. You can automate this with the "console++ 1.01" mod.

You don't have to do every of these, just try, see what is working for
you.

### Performance issues

Low FPS and 45+ min crashes.

Solution 1

Use Proton 5.xx. It has Directx9 -> Vulkan translation enabled by
default. If you have no Vulkan support, it will revert back to Directx9
-> opengl translation which is slow.

*Note: Your Linux graphics drivers need to have Vulkan support for this
one. This link will help you to install (and test it):
<https://linuxconfig.org/install-and-test-vulkan-on-linux>*

''You can use DXVK_HUD=1 option to see whether the Vulkan translation is
working or not for Proton 5.xx too. See below.

Solution 2

Proton 4.11 has D9VK built in so you can use that as well if for some
reason Proton 5.xx doesn't work for you. To enable D9VK set Launch
options in Steam to:

`PROTON_USE_D9VK=1 DXVK_HUD=1 PROTON_NO_ESYNC=1 PROTON_DUMP_DEBUG_COMMANDS=1 PROTON_LOG=1 %command%`

Start the game from Steam, copy the Run file then start the client with
the following terminal commands:

`export DXVK_HUD=devinfo,fps`
`export PROTON_USE_D9VK=1`
`export INSTALL4J_JAVA_HOME=/usr/lib/jvm/java-14-openjdk-amd64`
`./downlords-faf-client`

*Note: DXVK_HUD will display FPS numbers in the upper left corner of the
screen in lobbies and in games. You can remove that if you want. It only
works when D9VK is active.*

### The game crashes at \~45min in game time

The game crashes at \~45min in game time.

Solution:

-   Turn off the minimap and don't use split view.
-   Use Proton 5.xx
-   Use the the Vulkan translation layer (Directx9 to Vulkan) for
    Proton/Wine or vanilla Wine (see the previous one, Solution 1 and
    Solution 2).

### Desync issues

The desync window appears during gameplay.

Solution:
Turn off mods and use appropriate Proton/Wine and vanilla Wine versions.
See:

[#Install the game, set launch
options](#Install_the_game,_set_launch_options "wikilink")

*Note: Don't forget to create and copy your Steam RUN file again if you
change the version of Proton.*

### Game starts but the screen is black

The game starts, sound ok, but the screen is black.

Solution:
Use appropriate Proton/Wine and vanilla Wine versions. See:

[#Install the game, set launch
options](#Install_the_game,_set_launch_options "wikilink")

Reported with using AMD Vega cards and Proton 4.2:
<https://github.com/ValveSoftware/Proton/issues/688#issuecomment-491610215>

### Java Downlord's client freezes

The java Downlord's client consumes insane amount of CPU, memory or
freezes.

Solution:
Try to restrict java to use the software renderer instead of graphics
card acceleration.

Add this to the downlords-faf-client.vmoptions file: -Dprism.order=sw