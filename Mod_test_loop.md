## Introduction

All of the ideas in this document and more and included in the
[ModBootstrap mod](ModBootstrap_mod "wikilink") in the mod vault.
Consider using it to get started.

When modding it is very useful to create a mod test loop. This is a
structure that will instantly invoke your code when you save changes to
a file. That way you don't have to restart FA to test your changes.

## Overview

-   You need to launch the game with
    [/EnableDiskWatch](Command_Line_Switches "wikilink").
-   Create a file ui-invoke.lua that has your code.
-   Override gamemain.lua.CreateUi to, each beat, import your test file
    and call a function in it.
-   Bind a shortcut key to also import your file and call the function,
    so you can rerun whenever you want without having to save the file.
-   For the sim layer, override simInit.BeginSession, fork a thread,
    import your test file (another one) and call a function in it, then
    wait one tick.

## Test file

-   Your test file will tear down the previous test.
-   Your test file will set up a new test and store it globally.
-   Your test file will run the test. The code you run should be called
    in a pcall structure so if it has an error, it won't crash
    everything.

## Result

You now have a file that when you edit it and save changes, it will
instantly rerun again. You have a second file to run a test in the sim
layer. This is a great way to test some ideas instantly to work out how
things work/

## How it works

The EnableDiskWatch command line argument asks FA to reload your test
file when it is changed, but not until it is next accessed naturally -
which might be never. The loop we created imports your test file over
and over again, which forces your file to be reloaded now. Your loop
also invoked the test file (aside from importing it) And your shortcut
key can be used to reinvoke without having to save changes.