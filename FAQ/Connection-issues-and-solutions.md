Forged Alliance needs a direct connection between all players of the
game. To resolve connection issues FAF now uses the [ICE networking
technique](https://en.wikipedia.org/wiki/Interactive_Connectivity_Establishment)
to establish connections via players. This is also used and fully
supported for multiple players inside the same LAN.

**Port forwarding is no longer necessary with ICE and won't help your
connectivity issues.**

## Unable to connect to someone

From our current tests and recent diagnosis, we are pretty sure that the
ICE adapter has no technical issues itself. However, not all operating
systems behave the same (e.g. each Windows 10 installation can be
different due to installed patches, installed software, configured
network adapters etc.). These are problems that FAF cannot fix for you.

Here are some tips that might help you still:

-   Play with your network settings
-   Disable virtual adapters
-   If you use docker or WSL you might have hyper-v enabled, if so try
    disabling it via "DISM /Online /Disable-Feature:Microsoft-Hyper-V"
    type that into cmd
-   Check your antivirus
-   Use a VPN
-   Use a Linux based operating system (guaranteed fix )

### It's still not working!

-   Post in <http://forums.faforever.com/viewforum.php?f=3>. Include the
    downlords-faf-client.log and ice adapter log which can be found as
    specified in the forums header.
-   Enable the advanced ice adapter log in the client settings and send
    it to the developers.

## Unable to connect / connecting takes ages

Due to a very difficult and rare bug the ice adapters first connection
attempts may fail. This occurs only on a small minority of
installations. The bug is mitigated by the adapter forcing a relay
(proxy) connection on the third connection attempt. This may cause your
connection process to take up to 30 seconds.

In case you're still unable to connect / don't want to wait that long,
you can manually tell the adapter to force a relay connection. To do
this, head over to the FAF client settings (top left), go to the Forged
Alliance tab and select "Force relay connection".

## I'm always getting a relay connection

If you're experiencing high latencies this might be caused by being
relayed to a lot of peers via the faforever.com server. You can confirm
this by opening the ice adapter debug window (click the button in the
info window), if it displays "relay" as local or remote candidate for
any other player, you have a relay connection to them.

This means the adapter failed to establish a direct connection. (Also
see *Unable to connect / connecting takes ages* section about this) This
may be caused by your local network but also by your ISP (Internet
Service Provider). Due to the limited amount of IPv4 addresses some
carriers are employing so called "Carrier grade NATs / symmetrical NATs"
where multiple customers get hidden behind one public IP address. In
this case you will always get a relay connection, which should in most
cases be fine, the only thing you could do about this would be
contacting your ISP.

Another reason for this behavior could be your NAT (in your router)
assigning packet traveling out a random port instead of the same port as
used in the local network. You can try finding out if your router does
this and if it does take a look at its configuration if you're able to
set it to mapping ports "static"ally.

## Connection loss in game

In case you encounter frequent connection issues after the game has
already started, please first of all verify your internet connection is
stable. To do this use a tool like
[ping.canbeuseful.com](https://ping.canbeuseful.com) or the ping tool in
a terminal (*ping faforever.com -t* on Windows, *ping faforever.com* on
macOS/Linux) to monitor your connectivity and latency while playing the
game.

If you see issues in this test, please refer to your ISP and
test/investigate your private network for technical issues. Try reducing
network load on your and other devices, use an Ethernet cable instead of
WiFi, reduce WiFi traffic, switch the WiFi channel, remove network
switch, test on another device, ...

### It's still not working!

-   Post in <http://forums.faforever.com/viewforum.php?f=3>. Include the
    downlords-faf-client.log and ice adapter log which can be found as
    specified in the forums header.
-   Annoy the client devs to add proper ice adapter logging to the
    client

## Multiple computers behind the same router

This used to be an issue in the past but is resolved now. Playing with
multiple computers behind the same router should work without any
additional configuration.
