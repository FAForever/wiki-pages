## Before you start

It is always good to have some knowledge of how you want your AI to play
out. So before you create an AI, it is recommended that you have a good
idea of how the features of Forged Alliance works, e.g. The Economy.

You will need a text editor of some kind:

\- Sublime Text or Notepad ++ will do.

## Setup info

To add an AI to the game we need to load our code in the FA init file,
it can't be done through the usual modding means.

Some root folders we'll use when modding:

1\) **/lua/** - this houses the main body of the lua code. Files and
functions here overwrite previous code, but we can still call functions
from the original versions of the file.

2\) **/schook/** - this houses code that gets appended to the rest of
the moddable files on startup, so **/schook/lua/** will get added to the
end of stuff in **/lua/**

## AI Coding Overview

The following diagram illustrates the code you might need or want to
edit to create an AI:

<figure>
<img src="Forged_Alliance_AI_lua_breakdown.jpg" title="Forged_Alliance_AI_lua_breakdown.jpg" width="800" alt="Forged_Alliance_AI_lua_breakdown.jpg" /><figcaption aria-hidden="true">Forged_Alliance_AI_lua_breakdown.jpg</figcaption>
</figure>

Each item corresponds to a file in the Forged Alliance Lua code, with a
basic description and file location included.

The items with a bold outline are what we'll need to edit to create a
basic AI; other items are only needed for more advanced AI modding which
we won't cover here.

## Adding an AI to the lobby

To do that we need to get a little info about our AI into the
**aitypes** table in **/lua/ui/lobby/aitypes.lua**

Fortunately for us this is really easy, we just need to add our AI table
somewhere in the **/lua/AI/CustomAIs_v2/** folder (all files in this
folder with a **.lua** get loaded).

For example, we could create a file **/lua/AI/CustomAIs_v2/EpicAi.lua**,
containing:

` AI = {`
`   Name = "MyCustomAI",`
`   Version = "1.0.0",`
`   AIList = {`
`     {`
`       key = 'mycustomai1',`
`       name = "AI: Custom 1",`
`     },`
`     {`
`       key = 'mycustomai2',`
`       name = "AI: Custom 2",`
`     },`
`   },`
`   CheatAIList = {`
`     {`
`       key = 'mycustomaix',`
`       name = "AIx: Custom",`
`     },`
`   },`
` }`

This is the table that the lobby will load in to give your AI as an
option, and has subcategories for normal and cheating AIs. We can stick
as many AIs as we like in here.

Next we need to create some lobby tooltips for our new AIs, these are
the help texts that come up when someone hovers over our AI. To do this
we will be adding to the **Tooltips** object in
**/lua/ui/help/tooltips.lua**.

Since this is already full of stuff, what we really want to do is append
to it (rather than have to maintain an up to date tooltips.lua every
time a new FAF patch comes out).

For this we create our shadow file in **schook**:
**/schook/lua/ui/help/tooltips.lua**, and our file contents should look
something like:

` Tooltips.aitype_mycustomai1 = { title = "This is the title for Custom AI 1", description = "This AI really is epic!!", }`
` `
` Tooltips.aitype_mycustomai2 = { title = "AI: Custom 2", description = "This AI is really epic as well!!", }`
` `
` Tooltips.aitype_mycustomaix = { title = "AIx: Custom", description = "This AI cheats so is marginally less epic :(", }`

This is all we need to add our AIs to the lobby.

## AI Specification

Please Note! AI **Keys** (Identifiers) are really important for this
part. Make sure they are unique!

AI behaviour gets keyed by files in the **/lua/AI/AIBaseTemplates/**
folder.

This is where it gets interesting. Once you have configured your
**keys**, you can start creating templates for your AI to follow. In
order to do this, you need to create a **BuildTemplate** and a list of
**Builders**. You must always keep your **keys** around during this
part, as they are what identify an AI individually.

A **BuildTemplate** contains a function that returns your **key** so it
knows to use that **BuildTemplate** for the AI that is linked with the
specific **keys**. Let's take the **epic1** key as shown above.

Here is an example that creates a **BuildTemplate** for an AI:

`BaseBuilderTemplate {`
`   BaseTemplateName = 'MyCustomAITemplate1',`
`   Builders = {`
`     -- BuilderGroups go here; these enumerate all the things the AI can build`
`     -- We'll go into more detail on what these are in the 'AI Builders' section`
`   },`
`   NonCheatBuilders = {`
`   },`
`   BaseSettings = {`
`     -- Base settings can go here (which code can access later)`
`   },`
`   ExpansionFunction = function(aiBrain, location, markerType)`
`       return 0`
`   end,`
`   FirstBaseFunction = function(aiBrain)`
`       local per = ScenarioInfo.ArmySetup[aiBrain.Name].AIPersonality`
`       if not per then return 1 end`
`       if per == 'mycustomai1' then`
`           return 150, 'mycustomai1'`
`       end`
`       return 1, 'mycustomai1'`
`   end,`
`}`

Feel free to use the example above to help get you started.

## AI Builders

Todo :)

(This is the important bit though)

## AI Examples

A bare-bones AI implementation is available on GitHub:
[1](https://github.com/HardlySoftly/Forged-Alliance-AI)