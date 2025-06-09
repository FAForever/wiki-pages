---
title: FAFLive Streaming Guide
description: Basic guide for streaming under the FAFLive handle
published: true
date: 2025-06-09T10:27:14.084Z
tags: streaming, faflive
editor: markdown
dateCreated: 2025-06-07T16:05:20.732Z
---

# Rudimentary Guide to Streaming for FAFLive on Twitch

This is a work-in-progress to standardise the streaming process under the FAFLive handle


## Prerequisites

1.  Guest Streamkey from FAFLive

This allows multiple accounts to broadcast under the FAFLive handle. To obtain one, you’ll have to request it from whoever is currently in charge of the FAFLive Twitch account (This is probably Hybrid as of June 2025). You’ll need to give them your email but it doesn’t have to be the same one registered to your Twitch account. If successful, you will receive a stream key that looks like this: 

[Image goes here]

You can then input this streamkey to your streaming software of choice. Then, any stream from your PC will be broadcast to FAFLive until you change the streamkey. (Please Google how to do this for your preferred platform because there’s so many out there)


2. Moderator role for FAFLive on your Twitch account

[Image goes here]

The Moderator role not only allows you to moderate chat, but also grants you permission to modify the Nightbot settings. Nightbot is a tool integrated with FAFLive for automatic moderation, chat commands, and basic stream info editing. The lattermost allows us to modify the stream’s title or tags without needing full access to the FAFLive Twitch account. 

Similar to above, you can get the moderator role by requesting it from whoever is in charge of the FAFLive Twitch account. However, you must give them your Twitch handle instead of your email. It’s up to you whether you want to use your personal Twitch handle or if you want to create another one exclusively for FAF. 

## Basic Nightbot Guide
The full documentation can be found [here](https://docs.nightbot.tv/). This section of the guide will focus primarily on the common Nightbot use cases for FAFLive.

### Stream Titles (!title)

The !title command displays the current title of the stream and allows you and your moderators to modify it.

	!title title

<span style="color:red">title</span> is the title you wish to change your stream title to. Only place a title to change the title. Omitting this value displays the current title.



### Stream tags (!tags)

The !tags command allows you to update Twitch stream tags for better directory discoverability.

	!tags stream,tags
  
<span style="color:red">stream</span>, <span style="color:purple">tags</span> tags  is an optional list of comma-separated list of stream tags.

### Polls (!poll)

The !poll command allows you and your moderators to easily create polls using Straw Poll.

	!poll new title | option 1 | option 2

<span style="color:red">title</span> is the main title/question of your poll.

<span style="color:purple">options</span> are the individual options your users can vote for. Split by a vertical bar |, 

2 options are required, however, a maximum of 30 can be added.

### Chat commands (!commands)

The !commands command allows users to get a link to your custom commands page and allows you to add, remove, and modify custom commands.

Viewing Commands

	!commands

This returns a link to FAFLive’s custom commands page: https://nightbot.tv/t/faflive/commands

Adding Commands

	!commands add !command_name command response

<span style="color:red">command_name</span> is the name of the command you wish to use. Commands are usually prefixed with an exclamation mark

<span style="color:purple">command response</span>  is the message you want Nightbot to reply with when the command is called


Editing Commands

	!commands edit !command_name command response


<span style="color:red">!command_name</span>	 is the name of command you wish to edit

<span style="color:purple">command response</span>  is the message you want Nightbot to reply with when the command is called


Deleting Commands

	!commands delete !command_name

<span style="color:red">command_name</span> is the name of command you wish to delete

## Asset Management
*Under construction because Razana hasn’t had to deal with this yet.*


## Casting guidelines
*Under construction because Razana isn’t an experienced caster and everyone has their own preferred style. Please leave your comments here on what should be added*

- Check your audio and video quality before going live. A caster with a bad mic and screen isn’t going to be a fun experience for the viewers. Having a few days to test recordings and streams can help you iron out any issues before the actual tournament.
- 
- Maintain a fairly neutral and constructive tone. Casters have the benefit of full vision when casting and aren’t under the mental strain of competing in a tournament setting. It’s easy and even helpful to point out mistakes but don’t go too hard on berating the player for it.
- 
- Describe what you see. This sounds needlessly obvious but taking the extra step to describe what’s happening on screen helps illustrate a clearer picture of what’s going on, especially for the newbies. A yardstick that I use to remind myself about this is the hypothetical question: If someone tuning into the stream closes their eyes, can they visualise what is happening on-stream with how I’m describing it? Using words such as “This”, “That”, or “Those” in your sentences without further descriptors isn’t helpful for audience members who aren’t aware of the implications behind your statements. For example, if a player were to take a bad air fight: Simply saying “That’s pretty bad from Razana” versus following it up with “Razana had less ASF and didn’t have the better air micro to make up for it during the air fight”. 
- 
- Be conservative with the zooming and panning. It is very easy to nauseate the audience if you go too crazy with the camera movement. Tone down your zoom and pan sensitivity in the game settings and try not to rely on it too much if you want to draw the audience’s attention to something. As an alternative, you can use the draw feature (Hold right-click without anything selected) to highlight something interesting on-screen while being relatively zoomed out. This is not to say that you shouldn’t zoom and pan across the map. Just don’t do it too much and too fast. Extreme example of how not to zoom: https://www.youtube.com/watch?v=Gs9IeUF3f3w&t=623s




## Moderation

*Under construction because Razana hasn’t had to deal with this yet.*
