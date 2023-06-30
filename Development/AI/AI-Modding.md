---
title: AI-Modding
description: 
published: true
date: 2023-06-30T23:34:19.647Z
tags: 
editor: markdown
dateCreated: 2021-08-31T09:41:53.721Z
---

# AI Modding
## Custom AI
FAF has several custom AI - a [separate summary available of the various AI available](https://wiki.faforever.com/en/Development/AI/Custom-AIs) and how to play against them.

The below page is for if you are interested in creating your AI in FAF.

## Detailed guide
An [AI development guide](https://docs.google.com/document/d/1puzW5hKcOBNE7wu7bXj6qXfTJ60r2f93/edit?usp=share_link&ouid=100973959280546778272&rtpof=true&sd=true) that was created alongside a development log for one of the AIs is available, with the below-containing extracts from this and other sources.

See also the [forum post relating to this AI](https://forum.faforever.com/topic/2373/ai-development-guide-and-m27ai-v13-devlog) which includes a link to the devlog.


## Before you start
It is always good to have some knowledge of how you want your AI to play out. So before you create an AI, it is recommended that you have a good idea of how the features of Forged Alliance work, e.g. The Economy, and different unit roles.

You will need a text editor of some kind:

- Sublime Text or Notepad ++ will do.
- IntelliJ IDEA with the EmmyLua plugin works well (some of its useful features include autosaving changes, good search functionality, text highlighting and prompts, error identification, a shortlist of variables and functions in a file, and compatible with the GitHub desktop).

## Setup info

To add an AI to the game we need to load our code in the FA init file, it can't be done through the usual modding means.

Some root folders we'll use when modding:

1) **/lua/** - this houses the main body of the lua code. Files and functions here overwrite previous code, but we can still call functions from the original versions of the file.

2) **/schook/** - this houses code that gets appended to the rest of the moddable files on startup, so **/schook/lua/** will get added to the end of stuff in **/lua/**

## AI Coding Overview: LUA (general)
Lua is used for any AI coding/editing.  Useful more general links to learning Lua are given below.

- Coding in Lua:

Modifying the AI code involves using the Lua language.  There’s useful information on Lua concepts and coding with Lua below:
https://www.lua.org/pil/contents.html

- Stand-alone Lua code testing

If you want to read through this and experiment with Lua coding outside of FAF to understand some concepts, here’s a simple way to get things setup:
- Download both the Windows executables and Windows DLL from the following link: http://luabinaries.sourceforge.net/download.html
- Extract to the same folder as each other
-	Create a test Lua file - create a notepad file, rename the extension from .txt to .lua, and then add your code to it, e.g.:
```lua
print("Hello World")
io.read()
```

Click and drag the Lua file you want to run onto the Windows executable (lua54.exe); if io.read() is at the end of the code then the window will stay open until you press enter.
For example, I made use of this to test multi-dimensional tables to ensure I was referencing them correctly.

- Lua optimisation

The following link also contains some performance tips for Lua:
https://springrts.com/wiki/Lua_Performance
It’s useful not just for performance, but also understanding the code better and how to do some common activities, with the various examples showing different ways to do the same thing.
- Common causes of errors for non-Lua coders

I’ve noted some of the errors I would frequently make in case they’re of help (particularly for people who haven’t coded in Lua before):

-	Table variables – If you set a variable T1 equal to an existing table variable T2, it uses a reference rather than copying the table values.  Therefore, any change made to T1 will also change T2.

-	Multi-dimensional table declarations – Lua supports multi-dimensional arrays via nested tables.  For example, MyTable[1] = {2,3,4} means the 1st value of MyTable is equal to a table containing 2,3,4.  If doing this, then the first time you make use of a subtable, it needs declaring.  So in the above example, I’d first do MyTable[1] = {}, and then MyTable[1] = {2,3,4} (there may be a better way of doing this, but this worked for me).

-	Related to this, care also needs to be taken with table references – e.g. MyTable[1][1] not MyTable[1[1]]

-	Case sensitive references – GetUnitID() will return an error.  However, GetUnitId() will return a unit blueprint ID (if used correctly).  Similarly, MyVar is a different variable to myVar

-	Full stops vs colons – continuing the above example, oUnit.GetUnitId() will return an error, but oUnit:GetUnitId() won’t.  (with thanks to Speed2 – the reason for this is that oUnit:GetUnitId() is syntactic sugar for oUnit.GetUnitId(self). So if you want to use the version with. you have to pass self as the first arg).


## AI Coding Overview: How to create/edit an AI in FAF
The following diagram illustrates the code you might need or want to edit to create an AI:
![forged_alliance_ai_lua_breakdown.jpg](/images/ai/forged_alliance_ai_lua_breakdown.jpg)

Each item corresponds to a file in the Forged Alliance Lua code, with a basic description and file location included.

The items with a bold outline are what we'll need to edit to create a basic AI; other items are only needed for more advanced AI modding which we won't cover here.

Thanks to chp2001 for the following diagrams which also give an overview of how AI works
![howaiworks.png](/howaiworks.png)
![howaiworks-buildsomethign.png](/howaiworks-buildsomethign.png)

## Adding an AI to the lobby

To do that we need to get a little info about our AI into the **aitypes** table in **/lua/ui/lobby/aitypes.lua**

Fortunately for us, this is easy, we just need to add our AI table somewhere in the **/lua/AI/CustomAIs_v2/** folder (all files in this folder with a **.lua** get loaded).

For example, we could create a file **/lua/AI/CustomAIs_v2/EpicAi.lua**, containing:
```lua
 AI = {
   Name = "MyCustomAI",
   Version = "1.0.0",
   AIList = {
     {
       key = 'mycustomai1',
       name = "AI: Custom 1",
     },
     {
       key = 'mycustomai2',
       name = "AI: Custom 2",
     },
   },
   CheatAIList = {
     {
       key = 'mycustomaix',
       name = "AIx: Custom",
     },
   },
 }
```
This is the table that the lobby will load in to give your AI as an option and has subcategories for normal and cheating AIs. We can stick as many AIs as we like here.

Next, we need to create some lobby tooltips for our new AIs, these are the help texts that come up when someone hovers over our AI. To do this we will be adding to the **Tooltips** object in **/lua/ui/help/tooltips.lua**.

Since this is already full of stuff, what we want to do is append to it (rather than have to maintain up-to-date tooltips.lua every time a new FAF patch comes out).

For this we create our shadow file in **schook**: **/schook/lua/ui/help/tooltips.lua**, and our file contents should look something like this:
```lua
Tooltips.aitype_mycustomai1 = { title = "This is the title for Custom AI 1", description = "This AI really is epic!!", }

Tooltips.aitype_mycustomai2 = { title = "AI: Custom 2", description = "This AI is really epic as well!!", }

Tooltips.aitype_mycustomaix = { title = "AIx: Custom", description = "This AI cheats so is marginally less epic :(", }
```
This is all we need to add our AIs to the lobby.

## AI Specification

Please Note! AI **Keys** (Identifiers) are really important for this part. Make sure they are unique!

AI behaviour gets keyed by files in the **/lua/AI/AIBaseTemplates/** folder.

This is where it gets interesting. Once you have configured your **keys**, you can start creating templates for your AI to follow. To do this, you need to create a **BuildTemplate** and a list of **Builders**. You must always keep your **keys** around during this part, as they are what identify an AI individually.

A **BuildTemplate** contains a function that returns your **key** so it knows to use that **BuildTemplate** for the AI that is linked with the specific **keys**. Let's take the **epic1** key as shown above. 

Here is an example that creates a **BuildTemplate** for an AI:
```lua
BaseBuilderTemplate {
   BaseTemplateName = 'MyCustomAITemplate1',
   Builders = {
     -- BuilderGroups go here; these enumerate all the things the AI can build
     -- We'll go into more detail on what these are in the 'AI Builders' section
   },
   NonCheatBuilders = {
   },
   BaseSettings = {
     -- Base settings can go here (which code can access later)
   },
   ExpansionFunction = function(aiBrain, location, markerType)
       return 0
   end,
   FirstBaseFunction = function(aiBrain)
       local per = ScenarioInfo.ArmySetup[aiBrain.Name].AIPersonality
       if not per then return 1 end
       if per == 'mycustomai1' then
           return 150, 'mycustomai1'
       end
       return 1, 'mycustomai1'
   end,
}
```
Feel free to use the example above to help get you started.

## AI Example, and getting started using MicroAI as a starting point

A bare-bones AI implementation is available on [GitHub](https://github.com/HardlySoftly/Forged-Alliance-AI)
- Including MicroAI

The following sets out the steps for including this so you have a starting point that you can edit/add to when creating your own AI (which may be less intimidating than starting completely from scratch)

-	Follow the above GitHub link, click on the “Code” button, and download as a zip file
-	Copy/extract the folder and file groupings into the mods folder of Supreme Commander, creating a folder for your mod name (i.e. the Hook and Lua folders will be subfolders of this folder you create). E.g. `C:\Users\[yourusername]\Documents\My Games\Gas Powered Games\Supreme Commander Forged Alliance\mods\MicroAI` Another location that might be used instead of the above is: `C:\ProgramData\FAForever\user\My Games\Gas Powered Games\Supreme Commander Forged Alliance\mods\MicroAI`
-	Giving the AI mod a name

To avoid conflicts with other AI (which can lead to your and/or their AI not working) it’s important to use a unique reference for your AI mod, and to (wherever possible) preface any names you give with this unique reference.
-	Rename the MicroAI folder and any files within it to replace ‘MicroAI’ with your own chosen reference
-	Open up the renamed MicroAI directory in the Lua editor, and then use the find function to replace any references to “microai” with your chosen reference (i.e. across all files).
-	Update the mod_info.lua file to change the uid to a different unique reference
In addition, whenever using hooks I’d strongly recommend using some sort of unique prefix for all functions and global variables to avoid conflict with other AIs (which can lead to game crashes and AI not functioning at all).

## Other setup and general information
-	Github

Even if you're planning on developing your AI on your own rather than collaboratively, GitHub still has benefits some of which are summarised below 
-	Clearer history – Changes to code can be grouped by what they relate to, so if you're figuring out what you changed with a particular logic it’s easier (Intellij contains a local history option, but this will show all changes vs a particular time point)
-	Potential for online collaboration – if another AI developer comes across a bug it’s possible they might provide a suggested fix via Git Hub.  It also makes it easier to point people towards a particular part of your code if you want to show them how you did something (to help them) or ask for help on why something isn’t working.
-	Backups – Having the code backed up online gives extra protection in the unlikely event of a computer failure
Setup involves creating an online account on Github, installing git, downloading and installing Github Desktop, and then loading Github Desktop and pointing it to the mods directory where your AI folder is.  GitHub Desktop will then automatically track changes made to your code, so whenever you've finished with a change you can open it up, type a few words summarising the change, and then save/publish those changes. See elsewhere for guides on using Github.  For example, I came across the following from a brief search:
- [Git ebook](https://git-scm.com/book/en/v2)
- [Git commit messages](https://chris.beams.io/posts/git-commit/)
- [AI development discord](https://discord.gg/M5zgaWTqH9)

Several AI developers are active on this discord; the Discussion-about-ai support channel can be used either to see discussions developers have among themselves about the best way of doing something (this guide contains several extracts of such conversations) or to ask queries/help for your AI.

- Other AI discord resources
The main FAF discord has a section relating to AI development.  To have these visible, first go to the #Role-selection channel, and in the “What are your game preferences? Part 2” section, click the robot icon that relates to having a preference for AI games.

The ai-faq channel lists some useful information on different AI.  If you want your AI listed here, then contact relent0r with details of your AI/a summary description of it that can be posted to the ai-faq channel.
- Core FAF Lua files

Often it’s necessary to access the core game files to try and understand how something works or what to hook onto when editing code.

The base forged alliance files can be found at: `C:\Program Files (x86)\Steam\steamapps\common\Supreme Commander Forged Alliance\gamedata` Or for the non-steam version: `C:\Program Files (x86)\THQ\Gas Powered Games\Supreme Commander - Forged Alliance\gamedata`

Meanwhile, FAF files can be found: `C:\ProgramData\FAForever\gamedata`. I'd recommend making a copy of the Lua files from these in a separate location so you can view them without accidentally editing them and causing a desync (or just using the main FAF GitHub for searching/viewing code, which has the benefit of being up to date for the latest version).

E.g. for the FAF data, I think the lua.nx2 is the main file used. To access the files, rename the copy’s file extension to.zip, and you should be able to extract their contents.  You can then e.g. open the entire folder in Intellij which will allow you to search every script within that folder (and subfolders) in one go.
- Built-in functions

The below link also appears to give a list of core/global functions that can be used (I’ve not tested these to see if they all work, or even if they’re for FAF rather than SupCom2, but speed2 confirmed they’re for FA): [LUADOC](https://wiki.faforever.com/en/Modding/LUADOC)

With Thanks to speed2 for the link, some FAF functions are also documented in this [link](https://github.com/FAForever/fa/tree/deploy/fafdevelop/engine)

The AI development guide referred to initially also includes an index of built-in functions found to be of use, split by category, at the end of the guide.
-	Unit blueprints

The following website contains key information for each blueprint by analysing the code on GitHub: https://unitdb.faforever.com
Therefore, if you want to see all data available on a unit blueprint, if you load up the building/unit in question, the website then has a hyperlink on the unit blueprint ID which takes you to the underlying code itself.
Note though that the website summarising each blueprint can be out of date, so to be sure you're getting the latest information you'd want to check the underlying blueprint code on Git Hub.

E.g. the following is the code for a [T1 Aeon Engineer](https://github.com/FAForever/fa/blob/develop/units/UAL0105/UAL0105_unit.bp) If you have a blueprint object in your code, you can then reference the information contained in this code.

For example, if you have a function that is passed a variable builder that represents a unit constructing something, the following will access the blueprint data for that unit and set a variable equal to its maximum build range:

```lua
local iBuildDistance = builder.Blueprint.Economy.MaxBuildDistance
```

## Hooking
To give more flexibility over what we change, we want to be able to edit some of the core game code that is used by the AI.  ‘Hooks’ are a way of doing this, where you can append your code to an existing code file.

The following links give more details/examples on hooking:
- https://supcom.fandom.com/wiki/Modding
- https://forums.faforever.com/viewtopic.php?f=41&t=16789

If you're unfamiliar with how hooks work then I'd suggest looking at an existing AI for how they've done hooks.  An example is given below which adds a variable to an ai which will allow you to check (in other code) if the AI chosen is your own (e.g. this is useful for hooks as well to avoid doing anything if you're not dealing with your AI):

Go to the hook\lua folder, and create a new Lua file called aibrain.lua

In this case, we want to hook the AIBrainClass, and specifically the OnCreateAI part of that class.  We hook it in a non-destructive manner with the following (the example given is for an AI called Micro27):
```lua
Micro27AIBrainClass = AIBrain
AIBrain = Class(Micro27AIBrainClass) {
--Hook of the class

    OnCreateAI = function(self, planName)
        Micro27AIBrainClass.OnCreateAI(self, planName) --This means that the original code that would have run is still running (so this is a non-destructive hook)
        
        --The custom code we want to also run on this hook but only for our AI:
        local personality = ScenarioInfo.ArmySetup[self.Name].AIPersonality
        if string.find(personality, 'icro27') then --if the AI name contains icro27 then assume it's ours and set a variable to true so in future we can just check the presence of this variable:
            -- case sensitive
            self.Micro27AI = true
        end
    end,
}
```
If you want to hook other files or functions, then first determine the file name and location of that file (within the core FAF lua files) that it's part of, and follow a similar process to what was done above for the aibrain.lua file.

For example, you can use hooks to create your custom code that will run on certain events (e.g. when a unit takes damage; when a weapon is fired; etc.)

## Debugging
- Console

`'` opens up the console menu, which has some commands (although I’ve not tended to use these): https://supcom.fandom.com/wiki/Console
- Cheats

Alt+F2 opens up the cheat menu (if cheats are enabled in game options before the game is started), allowing you to e.g. create any unit, or switch to the AI view (by double-clicking on the AI player in the cheat menu) to see what they’re doing.
- Log window and error messages

F9 opens up the Log window (you may want to change the game resolution to windowed to more easily access this).
In the game options (when selecting the map) if Uveso is enabled you can also set AI Platoon Names and AI Builder Manager to show for all AIs to help with debugging.
When writing Lua code, you can send messages to the log window using LOG(), e.g.:
```lua
LOG('Hello world’)
```
If there are errors in your code, often it will show up in yellow warning text in the log menu when it attempts to run, which may give useful information to help identify the particular code file and a line item that are causing the error (along with why).

If you’ve hooked onto existing code then the line item where an error is present will be higher than when you view the code.  I solve this by commenting on the top of the hooked code with how many line items are in the core game files, so I can then subtract this to work out the actual line in my code causing the error.  If you have mods enabled then this can also cause the line item to change if they’ve hooked onto the same file.

I often use the log window by putting LOG() statements throughout my code, with a unique reference and then copying the log window output (e.g. into word excel or Notepad) and searching for the unique reference to see if it’s doing what I think it should.

You can also have the log window open when you load the game itself by adding “/showlog” to the end of the shortcut, i.e. `C:\ProgramData\FAForever\bin\ForgedAlliance.exe /showlog`

- Debug window and shortcuts

(with thanks to speed2) there’s a debug window that allows you to view variables/tables in-game and can be accessed by pressing Alt+F9.

Checking the key bindings there are also several related shortcuts which presumably are for use with the debug window.
When I tried accessing this I got an error message, and others have as well, with Jip thinking it happens where the game has been installed via Steam and not the CD meaning it is missing some texture files.

I ended up finding a cheap copy of the FA game disc and the debug menu now loads for me but still gives an error message on one of the files it tries to access and doesn’t do anything, so it's noted here in case it works for other people (but with a warning that there's a good chance it won't).
- Platoon names for debugging

An alternative to using the LOG() option is to rename platoons.  E.g. Uveso’s AI will rename platoons to indicate what they’re doing, which (when coupled with the configuration option that displays platoon names) makes it easier to assess the logic a platoon is following.

If you have a PlatoonHandle variable self, then you can also change platoon names, for example:
```lua
self:RenamePlatoon('MovePath: cancel move, enemies nearby')
```
- Fast speed

The following will cause the game to start at +10 speed (useful for saving a few seconds when debugging things over doing it manually) – don’t forget to comment the ConExecute line out once you’ve finished debugging though:

Create `\hook\lua\ui\game\gamemain.lua`

Put the following code in this:
```lua
local OldOnFirstUpdate = OnFirstUpdate
function OnFirstUpdate()
    OldOnFirstUpdate()
    ConExecute("WLD_GameSpeed 10")
end
```
-	Other shortcuts and game startup options

If you start a game, and make changes to your code while the game is running, use Ctrl+F10 to restart a game quickly, reflecting any changes you’ve just made to the code.

You can also use command line switches to change some settings [here](https://wiki.faforever.com/en/Command-Line-Switches)

Thanks to Uveso and Dragun101, you can enable offline logs using a command switch, which will create a text file of the log that you can access even after closing down the game.  I’d therefore recommend this since if you run into a hard game crash this at least gives you something to go on to figure out what's causing it.

Incorporating the points above, I use the following to test offline, which shows the debug log by default, and creates a log file I can access:

`C:\ProgramData\FAForever\bin\ForgedAlliance.exe /init init_faf.lua /EnableDiskWatch /showlog /log  C:\ProgramData\FAForever\logs\offlineDev.log`

- Hard crashes

Unfortunately, not all errors result in the orange error message text that aborts the script and tells you the precise sequence of functions (and the line item) that caused the error.  Sometimes the game will just do a hard crash.  The most common causes of this that I’ve come across so far are:
-	Infinite loops (fairly obvious one – as a precaution against this I ensure that every ‘do while loop I use has a maximum loop count so it can abort to protect against this)
-	Referencing units/platoons after they’re destroyed – normally this causes the ‘orange’ error message, but occasionally it would hard crash.  This can also happen if trying to reference your ACU after it’s destroyed.  To get around this if I want to reference the ACU as a variable I now use a custom function which will first check the ACU variable isn’t nil and the ACU isn’t dead before proceeding (and just wait ages if it is dead).  
-	Use of WaitTicks and WaitSeconds – This links to the above point - the danger when using these functions is that the game state will change, and this could lead to previous assumptions being incorrect.  For example, you record a variable for a particular unit, then wait 1 second.  If you then try and do anything involving that unit, you could cause an error if in the meantime something has happened to that unit (e.g. it’s been destroyed).  You can avoid this by checking the variable is still valid (e.g. in the case of a variable oUnit, something like ‘if oUnit and not(oUnit.Dead)’ should work, but it’s easy to forget to do this.
-	Using LOG(repr(table)) on a large table – e.g. if you try and do repr on even just a single unit variable, it will take ages to print everything or even just crash the game.  Try to do it on a table of units and the game will just crash.
-	Errors in variable declarations – e.g. I once had a hard crash caused because at the start of a code file (above any functions) I had a variable declaration local refCategoryT1Mex = categories.STRUCTURE * categories.TECH1 * categories.EXTRACTION
-	The error was because there are no categories.EXTRACTION, only categories.MASSEXTRACTION.  Similarly, a typo in categories in that context would I think cause a hard crash.
-	Similarly, you can get a hard crash by trying to import a file that doesn’t exist (e.g. local M27MissingFile = import('/mods/M27AI/lua/AI/M27MissingFile.lua') – so if tidying up your code by removing unused code files make sure you’ve not imported that file anywhere first.
- Using FAF Develop

It’s advisable to do at least some testing on the FAF Develop version of the game (instead of the normal game), in case any of the planned changes will interfere with how your AI works.  This means you can pre-empt these and reduce the risk your AI fails when a new FAF patch is added to the core game, as well as help improve the FAF project in the event you come across an issue with the develop version itself (as opposed to a flaw in your code that it exposes).

I followed the following steps which resulted in FAF development working:
-	Host and play an online game through the FAF client, selecting the develop mode when hosting (NOTE: make sure you backup your AI first due to the risk of it being overwritten if you’ve already uploaded a version of your AI to the mods section and have the AI mod enabled when hosting the game; also disable your AI sim mod before actually creating the game to host):

![usingfafdevelop.png](/usingfafdevelop.png)

You can also create a shortcut to running the game offline using FAF development:
`C:\ProgramData\FAForever\bin\ForgedAlliance.exe /init init_fafdevelop.lua /EnableDiskWatch /showlog /log  C:\ProgramData\FAForever\logs\offlineDev.log`
- Error handling

With thanks to Softles, the below link discusses different options for error handling in [LUA](https://www.tutorialspoint.com/lua/lua_error_handling.htm)
However, one of the functions in here, xpcall, doesn’t work in FAF (at least it doesn’t when I’ve tried it).
When most errors occur in FAF, you’ll get an orange error message which tells you the line of code causing the error, a description of the error, and traces the different functions and line references that got to that point.  However, at this point, the thread will abort (meaning any code after it doesn’t run).
This is a big issue if you have looped code that is intended to always run – for example, platoon AI – your platoon can end up stuck not doing anything because it encountered a single error.
With thanks to Balthazaar, you can use the following line to produce a similar error message that doesn’t cause the code to stop (meaning if something unexpected happens you’ll have useful information to help identify it and can try and get your code to handle the error without coming to a grinding halt):
```lua
local a, s = pcall(assert, false, 'msg')
WARN(a, s)
```

For example, let's say you have code that will issue a move command to a unit.  If the unit is dead, then instead of issuing a move command you could just include these line items (with something more meaningful in msg such as ‘Unit is dead so stopping move command’), and avoid issuing the move command (so you don’t cause an actual error).
Global variable not recognised
Usually, this error message means you’ve made a typo when referencing a variable, or have forgotten that you’re calling a function from another file (so need to have a prefix with that file’s variable; i.e. at the start of the script file you’ll have a local variable importing the other file with the function you want, e.g. `local ABCUtilities = import('/mods/ABCAI/lua/ABCutilities.lua')` and then your function or variable reference from that file has ABCUtilities. as a prefix.

Another time this error can occur however is if you’ve messed up something in the code file itself.  For example, I once commented out a while loop and replaced it with an if condition to try and figure out what was wrong with my code.  However, I forgot that I’d also included a break within the while loop (to stop infinite loops).  Having that break remaining in my code but with no loop meant that if any function in that code file was referenced (even if it was completely separate from the affected function containing the break in it) it would return an error that it couldn’t find a global variable with that name.
- Debugging via replay: Offline replays

(With thanks to Relent0r for confirming the replay location, and Spouto for suggesting) when you play a game using the FAF exe `(C:\ProgramData\FAForever\bin\ForgedAlliance.exe)`, the last game you play gets stored as LastGame and is accessible in the Replay window.  This should get stored even if you close down the game part-way through (although I’ve not double-checked it gets stored in the event of a hard crash).  My lastreplay gets saved to the following location (if you wanted to make a copy to avoid the risk of overwriting it with a new game):
`C:\Users\[username]\Documents\My Games\Gas Powered Games\Supreme Commander Forged Alliance\replays\FAF_[FAF username]`
If you come across an error that is hard to replicate, then one approach is to play until you have a game that it occurs in, then make changes to the code to help debug (or fix) the error, and then run the replay.  It will desync due to the changes, but depending on the scenario can give a way of getting more information on what's causing the error/how to resolve it.

- Debugging via replay: Online replays

(With thanks to Relent0r for helping by confirming how they got this to work)
If you try to watch an ‘online’ replay (i.e. a replay from a game played via the FAF client, ending in .fafreplay, as opposed to the offline replay ending .SCFAReplay), then the client will first download the versions of the mods used in that replay.
This means you should be very careful when accessing an online replay due to the risk of overwriting your AI code (if you edit the same location).
It also makes it harder to diagnose issues with online replays, as you have to mimic the same version to avoid the client redownloading it.
Following a client update, mods are now saved in the below location:
`C:\ProgramData\FAForever\user\My Games\Gas Powered Games\Supreme Commander Forged Alliance\mods`
Simply deleting the folder for the AI in question and replacing it with alternative files (that use the same uuid and version number) won’t work, as it will still be replaced.  However, if you edit the folder and e.g. add-in logs for particular issues, then it won’t replace the entire folder.
I’ve not done further testing to figure out what the threshold is for the entire mod being replaced with a download of the version used in the replay.

- Accessing an online replay offline

Thanks to Jip for this suggestion of an alternative method of watching offline replays:
After starting the replay using the client you can find the scfareplay file in the cache:
`C:\ProgramData\FAForever\cache`
Then you can copy that to your replay folder, rename it and play it
You can then save it to:
`C:\Users\[yourusername]\Documents\My Games\Gas Powered Games\Supreme Commander Forged Alliance\replays\FAF_[yourfafusername]`
And then view the replay from the Replays menu when running the offline client (you'll need to try and view the replay using a consistent version of FAF, including either the FAFDevelop or normal FAF executable based on which was used for the replay).

## Detailed AI framework mechanics

There are 7 main classes that drive the default AI.

### AIBrain Class
This contains most data that the AI leverages and most core functions and threads such as
- creating builder managers
- intelligence gathering
- initialization functions
- economy data
- economy functions
- control functions
- threat functions

It is a C-Engine class so has a lua component and C component.
Files 
*/lua/aibrain.lua 
/engine/sim/CAiBrain.lua*

### Builder Class
This class defines builders that are used as data objects for various builder manager types. They come in the following types
- EngineerBuilder
- FactoryBuilder
- PlatoonFormBuilder

A builder object contains the following attributes

**PlatoonTemplate** - Defines either the platoon former template or the factory builder template. Both the PlatoonFormerManager and EngineerManager use the same template types that select squads based on unit categories, the FactoryManager uses units blueprint id's that pass to factories for construction. The min and max integers (table position 2 and 3) are only used in the platoonformer and define the minimum and maximum number of those category units that will be added to the platoon when it is formed.

**BuilderConditions** - Boolean based function list that are all required to return true in order for the builder to trigger. Used to manipulate builder usage based on data. They are functions stored in deperate lua files under the /lua/editor directory. In the builder files they are imported as variables such as EBC, UCBC etc. The format for the builder table object is
condition import, function name, parameters incased in braces (curly brackets). The brain will always be passed as the first parameter to any function that is a condition.

**Priority** - When a BuilderManager runs the GetHighestBuilder function, it queries for a builder using priority to define which is selected IF all conditions pass as true. In the case where there are multiple highest builders (e.g you have 5 builders that are all 1000 priority) a random one of that group will be selected. A common confusion that AI developers have initially is the relationship between builder priority and conditions. The best way to remember it is that priority is only relevant when all conditions are true.

**BuilderType** - Only used on the factory manager to filter what unit types a factory should attempt to check when using GetHighestBuilder. For the other managers it will be specified as 'Any'.

**InstanceCount** - Used to dermine how many instances of a builder can be used at any one time. For example the number of platoons created by a specific builder, or the number of engineers running a specific builder. Does not effect the FactoryManager(confirm?).

**FormRadius** - Used by the PlatoonFormerManager to use as the radius to search for units based on the BuilderManagers position. If not specified then it will use the platoonform managers radius as defined when the manager is created.

**BuilderData** - Used to input data to the managers that are specific to this builder, used by platoon functions for configuration. In the case of engineer builders it will usually define construction data that the EngineerBuildAI platoon function will leverage to construct buildings and units. Not used by the factory manager.

**PriorityFunction** - Can be used similar to a builder condition to manipulate the priority of a builder. It is checked on when the builder is being evaluated rather than within the builder condition monitor. It is most often used to disable or enable builders based on data metrics.

Files
*/lua/sim/builder.lua*


### BuilderManager Class
The BuilderManager class is a base class that the 3 main builder managers inherit when being instantiated.

It contains certain attributes that are common to the managers. 
Some of these are

Radius - The radius that the builder manager can operate on. Used as attributes like the radius that the platoon former manager will search for units, or the radius that the engineer manager will look when evaluating structures. This is often used by builder conditions to evaluate data.

LocationType - The name of the builder manager, usually the base name. This is a special attribute that can be passed into builder managers via the builder objects as the string ‘LocationType’. It will be automatically be set to whatever the LocationType attribute on the builder manager class instance is set to.

Location - The xyz coordinates of the BuilderManager instance. 

Note that the other managers often set these variables in their own class for mod compatibility.

The builder manager class contains shared functions that deal with the builder objects and store all builders for a specific base with tables. They contain a manager thread that will test builders for priority changes, the platoonformer manager uses the MangerThread extensively as it is not self driven.

Files
*/lua/sim/buildermanager.lua*

### FactoryManager Class
The factory manager class drives any factories that are assigned to the manager. It contains functions and data structures specifically for the factory managers. 

The process for adding factories happens within the EngineerManager where a function will be called when an OnUnitBuilt callback triggers. There is also a callback that is triggered, when a factory is captured it will add the factory to the manager that the engineer which captured it belongs to.

PreBuiltUnits - TODO

When a factory has been added to the manager via the AddFactory function it will setup callback triggers for factory destroyed, factory captured, factory reclaimed and unit built from factory. When the callbacks are setup it will fork a DelayBuildOrder function which started the factory build cycle.
It will then fork a rally point function for the factory before existing the AddFactory function.

**Factory Unit Build Cycle**

DelayBuildOrder function runs which will add a wait based on the parameter passed, this in turn runs the AssignBuildOrder function. If a viable builder is found then a BuildPlatoon function is run against the brain with the platoon template and factory table along with the count of instances.

After this the factory will not run any other functions until the FactoryFinishBuilding function triggers, which is based on the OnUnitBuilt callback. This will run an if statement that checks for specific unit categories and run functions for them, for example when they build an engineer it will add that engineer to the engineer manager, when they upgrade it will add the new upgraded factory to the factory manager. It will then run the AssignBuilderOrder function again against the factory and the cycle will repeat.

Note that the template that is passed to the factory can be one or many units depending on how the template is configured. If multiple units are passed then the factory will queue up the unit construction orders.

The factory manager also handles modded unit replacements via a brain table called CustomUnits.

There is also a rally point monitor that will check if a structure is within a 15 unit distance of the rally point. If it finds one it will try to move the rally point further away, then loop through all factories in the manager and change the rally points. 

Files
*/lua/sim/factorymanager.lua*

### PlatoonForm Manager Class
The platoonform manager class is a relatively small class that contains functions and attributes for the manager. Its primary function is to form platoons based on the builders of type PlatoonFormBuilder. 
The main function ist he ManagerLoopBody, this function will run one instance of the same function name within the BuilderManager class and the location ManagerLoopBody within the platoonform manager class. The ManagerLoopBody is called by the Manager Thread in the BuilderManager base class. It will will perform the following task.
Check the builder priority is greater or equal to 1. So a priority of zero will not trigger any platoons. It will also verify the instance count of the builder. It will then get the army pool and platoon template data. It will run the platoon function CanFormPlatoon with the template, platoonsize, location and radius. If this returns true and the builder status (condition checks) are true it will form the platoon using the FormPlatoon function.
It will then set a plan name, then fork the platoon behavior function that drives the platoon. If the builder contains any addon plans, functions or behaviours it will fork these as well. Add on behaviors can run seperate threads on a platoon which can take over or drive platoon behaviors. An example of these are the repair and refueling behavior for air units.

It is worth noting that the platoonform manager is the heaviest of the 3 main managers in regards to sim speed impact due to the loop cycle and functions that run on every loop. Decreasing the number of platoon formers will have a positive effect on the manager sim consumption. The AI developer can increase the delay between loop cycles to try and improve performance, some AI increase the cycle for expansion bases while keeping the main base default to try and improve manager performance.

Some AI developers will also build custom threads to handle structure upgrades which decreases the load on the platoon former manager and improves responsiveness.

Files
*/lua/sim/platoonformmanager.lua*

### EngineerManager Class
The engineer manager is responsible for directing all engineers that exist under a specific base. It contains functions and data leveraged by engineers and some supporting management threads. The engineer manager does contain some utility functions that were originally designed to allow economy management based on low resource callbacks but these are disabled in FAF as they did not function correctly.

When a unit is built by a factory the factory manager callback will check if the unit category is an engineer and if so it will call the AddUnit function of the engineer manager using the LocationType of the factory manager to decide the engineer manager instance that will be joined.

The AddUnit function will loop through the ConsumptionUnits table of the engineer manager and add the engineer to it. It will set engineer manager attributes against the engineer unit so that it can easily be queried in platoon logic. It will then add various callbacks for the enginer such as a unit captured and unit construction finished.

After this process the ForkEngineerTask function will be run which starts the build cycle of the engineer, it will in turn fork a Wait function. The Wait function will provide a small wait followed by running the AssignEngineerTask.

The AssignEngineerTask will check if the unit is currently engaged in another task and if so it will run the DelayAssign function then exit. The DelayAssign will in turn kill any forked assignment function that is running and then fork the Wait function which starts the cycle once again. If the engineer was not engaged in a task when the AssignEngineerTask function was run it will run the GetHighestBuilder function from its base class, if a builder is returned it will create a platoon based on the platoontemplate defined in the builder and start any platoon functions required (identical to the platoonform manager). It will then call the DelayAssign function so that the engineer assignment loop will continue while the engineer is performing its task.

#### Considerations

It is worth noting that both the engineer manager and factory manager are self driven. Meaning that each individual unit drives the selection of builders. The more units that exist under the manager the more load on the manager. The platoonform manager by comparison runs a looping thread that is constantly trying to create platoons. This difference in functionality is the main reason why the platoonform manager is the heavier of the 3.

Each base created has an instance of all 3 managers, this means the the more bases an AI has the more load on the sim. This is often why AI can slow down in a later game as more bases are established and more engineers, factories and platoon managers are created looking for builders.
Some AI developers will introduce limits to the number of bases that exist, or will modify loop cycles on the expansion base managers to decrease the load on the game.

Engineer location can impact the efficiency of an engineer, remember that if an engineer builds a mass extractor half way across the map there is every chance that it will then pick up a builder that requires it to be back at its base location, this will cause efficiency delays while the engineer moves back or calls for transports. 
This is a difficult problem to work around with the default framework, the TaskFinished function of the engineer manager will attempt to work around this problem by checking if the engineer it within a certain distance of its original base. If it is beyond that radius it will run a ReassignUnit function which will try to find another base that is closer which also has a factory manager operational. If a developer is strict with his builders on expansion bases this can lead to idle engineers. 
There are other possible solutions that developers can try but often they will require modifying the core framework. One such solution was to create a floating engineer manager that focuses on extractor builders and reclaim builders, once an engineer is beyond a certain radius from its base it will join this manager which only contains builders that operate at range making engineer far less likely to return to base wasting efficiency. Though the bases need to be good at maintaining certain engineer counts so that enough build power is available at all times.

## AI Builders
Refer to the diagrams in the "AI Coding Overview: How to create/edit an AI in FAF" section above which give an overview of how AI builders fit into the wider FAF AI.

If you're new to FAF then it's probably easiest to learn how AI builders work and how to change them by taking the existing Micro AI (see above for a link on how to download this) and editing it for specific scenarios.  Some examples are given below.

Note that you do not need to use the built-in AI builders to produce something - creating your system will provide greater flexibility, but isn't recommended as a first step to understanding how AI works.  Examples of AI which don't use the core AI builder system include DilliDalli and M27AI.

- Changing the initial build order
Do the following to change the initial build order for the MicroAI:
Open `lua/AI/AIBuilders/MicroBuilders.lua`
Locate the “MicroAICommanderBuilder” section
Change the BuildStructures section to reflect your preferred build order using the ACU.  The following means it builds a land fac, 2 PGens, 2 Mexes, 2 more PGens, and a second land fac:
```lua
BuildStructures = { -- The buildings to make
    'T1LandFactory',
    'T1EnergyProduction', --T1 Pgen
    'T1EnergyProduction',
    'T1Resource', -- Mass Extractor
    'T1Resource',
    'T1EnergyProduction',
    'T1EnergyProduction',
    'T1LandFactory',    
}
```
- Build order conditions and priorities
A BuilderGroup contains various builder subtables.  Each builder subtable can be used to tell the AI to build something if certain conditions are satisfied.

The Priority variable in the builder subtable determines which builder will be done first (the highest priority is done first).  I.e. the AI will loop through each builder within the buildergroup, check if the conditions are satisfied, and then try and build the builder (for which the conditions are satisfied) that has the highest priority.

Builder conditions require a specific format to be used.  An example of a builder subtable is given below:

```lua
Builder {
        BuilderName = 'MicroAI T1Engineer AirFac',
        PlatoonTemplate = 'EngineerBuilder',
        Priority = 90,
        InstanceCount = 1,
        BuilderConditions = {
            { EBC, 'GreaterThanEconStorageRatio', { 0.1, 0.8}},
            { UCBC, 'HaveGreaterThanUnitsWithCategory', { 1, 'FACTORY TECH1' } }, -- Don't build air fac immediately.
            { UCBC, 'HaveLessThanUnitsWithCategory', { 4, 'FACTORY TECH1' } }, -- Stop after 5 facs have been built.
        },
        BuilderType = 'Any',
        BuilderData = {
            NeedGuard = false,
            DesiresAssist = true,
            Construction = {
                BuildStructures = {
                    'T1AirFactory',
                }
            }
        }
    },
```

This builder has 3 build conditions, which use a subtable in the format {CodeFileRef, '[Function name]', {[function input 1], [function input 2]}},
Taking EBC as an example, this is defined at the start of the builders lua file as:
```lua
local EBC = '/lua/editor/EconomyBuildConditions.lua'
```

You can locate this file in the core FAF files (i.e. the lua-nx2 file - see before for how to access this).  One of the functions in this file is called GreaterThanEconStorageRatio:

```lua
function GreaterThanEconStorageRatio(aiBrain, mStorageRatio, eStorageRatio)
    local econ = AIUtils.AIGetEconomyNumbers(aiBrain)
    if (econ.MassStorageRatio >= mStorageRatio and econ.EnergyStorageRatio >= eStorageRatio) then
        return true
    end
    return false
end
```

You can therefore create your custom conditions using a similar approach - i.e. create a separate lua file, define a variable that imports it at the start of your builder code, and have a function with a similar structure (you can choose the number of variables but note that aiBrain should always be the first variable for the function), and then add a condition to a builder that references this.