# Installing Luajit and Lupa for client builds

The python client needs Lupa for parsing Lua scripts. The procedure for
building a Lupa package on Windows is not trivial.

This guide assumes building in a Windows 7 x64 VM in Virtualbox.

## Get up Windows VM

Install Windows 7 Professional SP1 x64, install KB3020369 (Servicing
Stack Update, prereq for KB3125574), install KB3125574 (convenience
roll-up, "SP2")

## Build Luajit

-   Install Python2/3
-   Install [Git for Windows](https://git-scm.com/download/win).
-   Install [Windows
    SDK](https://www.microsoft.com/en-us/download/confirmation.aspx?id=8279).
    Make sure to select the "VC++ Compiler" feature.
-   Install [.Net Framework
    4.5](https://www.microsoft.com/en-US/download/confirmation.aspx?id=42643).
-   Install [Windows Management Framework
    3.0](https://www.microsoft.com/en-us/download/details.aspx?id=34595)
    (For Win7 x64, select KB2506143-x64).
-   Enable Powershell Scripts:

` * Start `*`Powershell`` ``ISE`*` as Administrator`
` * Execute: `*`Set-ExecutionPolicy`` ``RemoteSigned`*

## Build Lupa