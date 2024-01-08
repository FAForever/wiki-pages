---
title: Tech-Support
description: Collection of Common Issuse
published: true
date: 2024-01-08T10:06:28.282Z
tags: 
editor: markdown
dateCreated: 2024-01-08T09:51:44.018Z
---

# Common Technical Support Issuse

## How to Report an Issue

Please do not ping Administrators, Moderators, or any other roles regarding your issue.

1. Provide specific details about the issue and how to reproduce it. Also, which steps you have already tried to resolve it.
2. If related to a crash, attach a log file or include the whole log folder as .zip (Logs contain no personal data)
3. When possible, capture the error message or any other helpful information with a screenshot.


## FAQ on Common Issues

### Where are the logs and the 'Game.prefs' located?

You can navigate to the folders via the FAF client itself or via Windows Explorer (see attached image)

_**Overview:**_

**client.log :** Contains information about the FAF client itself. This log is crucial when the FAF client crashes or encounters connection issues.

**game_replay_id.log :** Contains information about a specific game played. This log becomes vital in diagnosing issues when a game crashes.

**iceAdapterLogs :** These logs contain a multitude of messages related to network connections to other players and changes in the game's state.

**ircLogs :** Provides information about IRC user data and nicknames.

**mapGeneratorLogs :** This log records the output of the map generator, providing comprehensive details about the last generated maps.

**Game.prefs :** This JSON configuration file stores various game settings, including the installation path, preferences, hotkeys, notes, enabled mods, mod and map directories, chat and notification settings, window size and position, as well as the last game type/title.


_**Default log location:**_

On Windows: `C:\Users\%username%\AppData\Roaming\Forged Alliance Forever\logs`

On Linux: `~/.faforever/logs`


_**client.prefs location: **_

On Windows: `C:\Users\%username%\AppData\Roaming\Forged Alliance Forever`

On Linux: `~/.faforever`

![logfolder.png](/technical-support/logfolder.png)
![logfiles.png](/technical-support/logfiles.png)

### Connection Issues / Failed Matchmaking
**If you have connection issues to FAF or having issues to establish connections for the matchmaking, try these possible solutions first:**

Note: Failing to establish a connection in matchmaking will never result in a permanent ban. The first failed connection is a warning, the second time results in a 10-minute timeout, and the third time results in a 30-minute timeout.

1. Try Disabling IPv6 (see attached image):

2. Try a VPN software and connect to FAF from a different country.

3. Changing Coturn server in FAF client in case you can connect to the client, but not to games. (see attached image)

4. For testing purpose, disable security software/firewall.

5. If it still doesn't work, unfortunately there is no easy way to solve the problem, as each user's network environment is different. You can ask a tech-savvy friend, start a thread, or try searching on Google & Co. for help.
 
![networkconnection.png](/technical-support/networkconnection.png)
![clientcoturn.png](/technical-support/clientcoturn.png)

### Game Crashes
**What to do when the game crashes frequently?**

- Make sure it is not mod related. Disable all mods, if it works, then enable them one by one until it crash again.
- Check for any recent client updates. Also, you can try the latest 'Alpha Client', if available → https://github.com/FAForever/downlords-faf-client/releases
- Enable the FAF Debugger for providing more details about the crash. (See attached screenshot)

To enable the FAF Debugger, do the following: Navigate to Bar menu in `FAF client` → `Settings` → `Forged Alliance Forever` → Use FAF Debugger when starting Forged Alliance

Then reproduce the crash and follow the guide in the Read Me First about 'How to Report a Crash'. 

![fafdebug.png](/technical-support/fafdebug.png)

### Audio Issues

#### 1 Fixing Disappearing Sound:
If your sound, goes silent after a certain time or early in the game - Make sure you have the following sound settings (without applying any filter/sound enhancements to "make it sound better"):

Stereo - 16bit - 44100 Hz

**Following software are known to cause conflicts with Supreme Commander:**

- Steel Series GG software suite
---
To apply the changes to the game, you will need to delete your Game.prefs file located at:

`%LOCALAPPDATA%\Gas Powered Games\Supreme Commander Forged Alliance\Game.prefs`

Please be aware that this will also erase your user configuration, including any enabled mods, settings, and build templates.

After deleting the file, run Forged Alliance from Steam/GOG to recreate your profile and generate a new Game.prefs file (start a sandbox game once, then exit). With this new file, FA will recognize your stereo environment, and the audio will work correctly.

It's important to note that Forged Alliance was developed before 5.1 or 7.1 surround sound technologies became available, and as such, they are not compatible.

---
**Example to change it:**

![audio1.png](/technical-support/audio1.png)
![audio2.png](/technical-support/audio2.png)
![audio3.png](/technical-support/audio3.png)

#### 2 Fixing Crashes Related to Sound - SND: Error, XACT: Invalid arg, XACT3DApply failed

Verify sound as the root cause, test the game without sound (shouldn't cause crashes), and inspect for UI or SIM mod issues.

---
**How to disable the sound properly:**

`FAF Launcher` ⇾ `Options` ⇾ `Forged Alliance Forever` ⇾ `Command Line Format for Executable` ⇒ add `/nosound` behind the `"%s"` 

![nosound.png](/technical-support/nosound.png)

---
**2.1 Uninstall FAF and Supreme Commander completely and remove any leftover files, so we can begin with a 100% working environment.**

Make sure no leftover files are in: (Path may be different, if you have the GOG version, or you have selected a different installation path.)

`C:\Program Files (x86)\Steam\steamapps\common\Supreme Commander Forged Alliance`

`C:\Users\%username%\Documents\My Games\Gas Powered Games\Supreme Commander Forged Alliance`

`C:\ProgramData\FAForever`

`%LOCALAPPDATA%\Gas Powered Games\Supreme Commander Forged Alliance\`

**2.2 Install the latest client release from FAF:**
[Client Download](https://github.com/FAForever/downlords-faf-client/releases) (Or go to the [Website](https://www.faforever.com/play))

Install Supreme Commander via Steam or GOG

Test for sound issues with a new installation. If problems persist:

- Ensure Windows is updated.
- Configure sound card to stereo mode.
- Set sound card to 44100 Hz / 16 bit; consider 44100 Hz / 24 bit
- Disable sound enhancements for your sound card.
- Deactivate unrelated sound devices (restart PC).

If you have a USB sound card like Focusrite and other devices, disable everything except your primary sound card (e.g., NVIDIA and Waves SoundGrid). If you're not using your onboard sound card, consult Google or your motherboard manual to deactivate it through the BIOS.

Example: In this image NVIDIA and Waves SoundGrid were deactivated:

![deeacivete_audio.png](/technical-support/deeacivete_audio.png)

#### 3 User-Contributed Suggestions

**3.1 Uninstall Sound Software & Try Alternate Speakers for Testing**

Consider using other audio devices, such different pairs of headphones/speakers or audio hardware. Uninstall any additional software that applies filters or effects to your sound and stick to using basic drivers to avoid potential problems. Avoid high frequencies and bit depths (Example: 96000+ Hz / 32 bit).

**3.2 Delete Sound Files Responsible for Crash**

Head into your steam folder for SupCom:FA and delete both music files (The .xwb and the .xsb)

`C:\Program Files (x86)\Steam\steamapps\common\Supreme Commander Forged Alliance\sounds`

**3.3 Reinstall Everything**

Reinstall Windows do not install any third-party software and try only with FAF and Supreme Commander.

--- 

**Conclusion:**

The cause of the disappearing sound error is unknown (Well, it is a ~20-year-old game engine) and there is no guaranteed solution, even after many years. It may be related to numerous factors, which makes it difficult to determine the root cause, but it is related to the sound card or other software that affects sound in some way.

---
If you need any guidance, please make your own thread here:

https://discord.com/channels/197033481883222026/1083855787518079066
or
https://forum.faforever.com/category/4/i-need-help

---
When you have found any information that could solve the sound issue, which is not listed here, please PM me about it, and I will add it. Thank you in advance.


### Steam account already linked / Regain access to FAF main account

If you previously linked your Steam account but have forgotten your main FAF account, don't worry. You can regain access by resetting the password through this link: [Password Reset]( https://www.faforever.com/account/requestPasswordReset) 

Scroll down to `Reset password via Steam` and follow the instructions there.

### Common error phrases and solutions

Find out what kind of error you have, by searching up your error text from the following list. (Copy the whole phrase.)

**Common errors phrases ❎:**

#### Error 1
RuntimeException: javax.net.ssl.SSLException: Tag mismatch!

#### Error 2
2. SocketException: Connection reset **or** 	WebClientRequestException: Connection timed out

#### Error 3
3. TimeoutException: Did not observe any item or terminal signal within 60000ms in 'sinkOneMulticast'

#### Error 4
4. AccessDeniedException **or** IOException: Cannot run program

#### Error 5
5. java.lang.RuntimeException: Forged Alliance Crashed with exit code 1

#### Error 6
6. Alliance Crashed with exit code -1073741515 **or** Forged Alliance terminated with exit code -1073741515

#### Error 7
7. java.io.FileNotFoundException

#### Error 8
8. Could not extract value with pattern 'code=([^ &]+)

#### Error 9
9. FileSystemException

#### Error 10
10. cartographic.fx reason: unknown error

#### Error 11
11. LoginException: Could not reach server

**Solutions:👨‍🔧🍏 :**

#### Error 1
**Reason**
The client is unable to establish a secure connection to the content server for downloading the game files.
- Disable security software for testing purpose
- Check firewall settings, if it blocks anything related to secure connection/FAF Launcher

#### Error 2
**Reason**
Something is blocking the client to have access to the internet, or you have a very unstable connection.
- Check if your internet connection is stable
- Check if firewall is blocking the access
- Disable security software for testing purpose
- Try a VPN from a different country

#### Error 3
**Reason**
Client can not detect that you are logged in from browser
- Change default web browser.

#### Error 4
**Reason**
Program is blocked or has wrong user rights
- Make sure security software is not blocking the client
- Make sure your windows account has rights to run the software
- Remove `"C:\ProgramData\FAForever"` folder; and reinstall FAF
- For testing purpose, run the client with admin rights.

#### Error 5
**Reason**
Some error caused the crash

- Get the last log from `"C:\ProgramData\FAForever\logs"`
- Create own thread, explain when the error happens and upload the .log https://forum.faforever.com/category/4/i-need-help

#### Error 6
**Reason**
Something is not working with your Supreme Commander.
- Start Supreme Commander via Steam/GOG, to download any missing files or additional needed software, then start a skirmish mission to create a Supreme Commander profile

#### Error 7
**Reason**
Files do not exist.
- Make sure nothing blocks your access to the FAF client or Supreme Commander folder
- Reinstall FAF client and Supreme Commander

#### Error 8
**Reason**
Problem with the current browser to processed certain information
- Change default web browser.
- Install another browser like Firefox, Chrome, etc.

#### Error 9
**Reason**
Another process is blocking the files
- restart the PC

#### Error 10
**Reason**
Unknown, yet.
- Reinstall FAF, supreme commander

#### Error 11
**Reason**
- On your end, something is blocking the internet access from/to the FAF client
- You have no internet
- Login server is down

---
If you need any guidance, please make your own thread [here](https://forum.faforever.com/category/4/i-need-help)

---

Notes TODO:
https://forum.faforever.com/topic/4283/cannot-connect-to-some-of-the-players-solution
add command to undo it:
https://forum.faforever.com/topic/4532/cannot-launch-supcom

### Other Helpful Links
[Forum Tech Support](https://forum.faforever.com/category/4/i-need-help)

[Forum FAQ and Guidelines](https://forum.faforever.com/category/18/frequently-asked-questions)

[FAForever Wiki](https://wiki.faforever.com/en/home)

[Latest stable Client or Alpha Client](https://github.com/FAForever/downlords-faf-client/releases)


