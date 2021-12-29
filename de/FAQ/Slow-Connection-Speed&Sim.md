# Slow Connection and/or Speed up your Sim Speed
## Improving your connection
This page is for general slow game troubleshooting or optimizing your game speed

Fixing high ping or inconsistent connection, in order of importance
1. Use Ethernet, not WiFi
1. Ports are forwarded See: [Connection issues and solutions](/FAQ/Connection-Issuses-and-Solutions)
1. You need a high quality Broadband connection, 0.5 Mbps upload and download just for Forged alliance.
1. Shut off anything else going on your computer or on any computer that is doing things on the net (roommates/family)
1. Run Malwarebytes and a Free Antivirus, Avast, Sophos, Bitdefender, etc
1. Check ISP and router ping, the ping needs to be less than 250: http://freeola.com/line-test/ . If The ping is higher than 250, contact your ISP for troubleshooting.
1. Check ping to router: Go to cmd prompt, use ipconfig to get gateway IP (usually 192.168.1.1), run command "ping 192.168.1.1 -n 50", make sure no pings are greater than 10 ms. If so router, switch, ehternet cables or NIC card is bad.

## Improving your SIM Speed/CPU score
**What is SIM speed**

SIM speed is the speed at which the central processing unit ("CPU") of your computer is able to run the real time simulations that take place in Forged Alliance. The game normally runs at zero SIM speed, indicating that the simulations happen in real time. When many units come into play, especially on large maps, the SIM speed may go into negative and cause the game simulations to take place slower than real time.

**SIM speed in game**

Because all players need to perform the simulation calculations, the slowest CPU is determining of the actual SIM speed the game will run at. The SIM speed of the game you are playing is displayed in the upper right corner of the screen. Alternatively you can open the console using the tilde key (~) and entering the command "ren_shownetworkstats". This renders a list of all players in the game and their respective SIM speeds. The lowest possible SIM speed is -10 and the highest possible SIM speed is +10. A SIM speed higher than zero is only possible by manually adjusting the SIM speed to run faster than real time. When viewing a replay this can be done with the default keys plus (+) and minus (-) on the NumPad. Adjusting SIM speed in game is not possible, unless the option is enabled by the host of the game.

**CPU score benchmark**

The CPU score in the lobby is an integrated benchmark, designed to predict SIM speed performance of your CPU in game. A low CPU score is better, with a score over 400 usually being indicative of bad performance due to low SIM speed. You can test the accuracy of your CPU score by loading a replay from Seton's Clutch. The more units that come into play as the game progresses, the heavier the load on your CPU will be. If you have a SIM speed below -2 at about 20 to 30 minutes into the game, this could be considered disruptive to other players.

**Actual CPU performance**

A high performing CPU is the only way to prevent slowdown of SIM speed below acceptable levels. The actual performance of a CPU in Forged Alliance is determined by several factors. Single thread performance and clock frequency of the CPU are the biggest determining factors. High single thread performance but low clock frequency will therefore result in low SIM speed performance. This is generally the case for mobile devices. CPU's with a high clock frequency and low single thread performance will also result in low SIM speed. Single thread performance is generally much higher in Intel CPU's, but AMD CPU's operating at high clock frequency can match the performance of lower clocked Intel processors. Also, it is beneficial to have at least a dual, but preferably a quad core CPU. The SIM speed calculations will always take place on a single logical core of your CPU however. It cannot be threaded across multiple cores of the CPU. The reason for utilizing a CPU with multiple cores is that the game and the operating system of your computer can offload other threads to other cores. This makes sure that the single logical core running the simulation, will have as much free resources available as possible.

**Increasing SIM speed performance**
Here are some ways of improving your CPU score, listed in order of effectiveness:

1. Get a CPU with a high clock frequency, in combination with good single thread performance as measured in this chart: https://www.cpubenchmark.net/singleThread.html
1. Make sure your CPU does not overheat - and make sure there is no dust in your pc. A hot CPU is throttled to prevent overheating.
1. Close any unnecessary background programs. These can severely impact your SIM speed.
1. Reduce the quality settings and resolution of Forged Alliance
1. Set the ForgedAlliance process priority to "High" and uncheck CPU 0. In limited examples this led to a ~3% SIM speed improvement. You can use this program to save these settings: [Process Lasso](https://bitsum.com/)

## Improving UI performance

Ideally your UI should behave exactly the same when you start the game at sim speed 0, when the game sim speed slows down to -10 and when you watch a replay at +10 speed. The thread that is responsible for UI, ren thread, is separate from the sim thread, however it is always assigned to core0 of your cpu, the same core that most often handles hardware interrupts. It has been found that putting the ren thread on any other core and placing the sim thread on a core that is different from the core that bears the ren thread improves ui performance during large battles and laggy newtork games. Furthermore it is beneficial to give the ren thread higher priority. One tool that can help you accomplish this task is process hacker. Once FA starts, you can observe different threads within FA, with the two most cpu intensive threads being the ren and sim threads. (http://processhacker.sourceforge.net/)

One other possible source of poor UI performance are heavily defragmented harddrives and ssd that have slow read performance with old data. The simple solution for this is to copy all game data, sounds and mod files, erase the originals and replace with the copy.

Another source of stutter in the ui are GPU's that decrease their powerlevel when underused. This can usually be remedied by choosing the high performance profile in the gpu control panel, make sure you do not have this problem by monitoring the powerlevel during gameplay, using a program such as nvidia inspector. 