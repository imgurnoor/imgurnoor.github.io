---
layout: post
title: Use an Android device as a Raspberry Pi screen
date: 2017-08-01 04:12
author: gurnoor
comments: true
categories: [Daily Diary]
---
The ones that everyone is most familiar with are the HDMI port, which can go straight into your monitor or TV, or via the GPIO ports with a portable screen. One avenue that is rarely pursued is using VNC software to remotely view the Raspberry Pi desktop using another computer entirely. It’s actually fairly simple and we are going to concentrate on viewing your Pi screen via Android for maximum portability.

<strong>Update your Raspberry Pi</strong>
<pre>sudo apt-get update &amp;&amp; sudo apt-get upgrade

sudo rpi-update</pre>
<strong>All you need is </strong>
<ol>
 	<li>TightVNC tightvnc.com</li>
 	<li>VNC Viewer bit.ly/1jCzBRJ</li>
</ol>
<strong>Install the software</strong>

We’re going to be using TightVNC for our VNC needs here – specifically, the server side of the software. We’ll need to install it first though, so head back to the terminal and type:
<pre>sudo apt-get install tightvncserver</pre>
Start up<strong> VNC</strong>

Once everything’s installed we can actually start up the
VNC server
<pre>vncserver :1 -geometry 640x480 -depth 16
-pixelformat rgb565</pre>
First time<strong> setup</strong>

The fi rst time you turn it on, you will have to set a password. You’ll need to pick a password you can remember as it will also be used by the client as it connects via VNC. You can only use a maximum of eight characters for the password though, so think carefully about how you want to make it secure.

<strong>Stop and restart</strong>

As TightVNC doesn’t quite work like a normal service, you can’t do a usual service X restart (or equivalent) to turn it off or whatever you wish to do with it. Instead, if you want to restart
it, you’ll have to manually turn it off and then restart it with the original command. To kill it, use:
<pre>vncserver -kill :1</pre>
<em>... replacing 1 with the display number that you originally create.</em>

<strong>Correct resolution</strong>

We created our test server with a resolution of 640 x 480, just to get it running. However, this is unlikely to be the resolution of your phone. Luckily, this resolution is not fixed every time, so the best thing to do is to look up the resolution of your Android device and then modify the line used to start up the server. For example, if you have a 1080p tablet, you would use
<pre>vncserver :1 -geometry 1920x1080 -depth 16
-pixelformat rgb565</pre>
<strong>Get the app</strong>

On your Android device, go to the Play Store and look for VNC Viewer. Install it to your device and run it to make sure it works fi ne. We can now begin to try and connect it to the Raspberry Pi.

<strong>Raspberry Pi IP</strong>

We need the IP address of your Raspberry Pi so that we can connect to it. You can get it via two methods – our preferred method is to open the terminal and use ifconfi g to list the status of the Pi’s network interfaces; this will include the IP address of whatever is connected. If you’re using wireless to connect, you can also access the wireless config interface (iwconfi g) and see what the wireless has been assigned as an IP

<strong>Connect to the Pi</strong>

Now that we have the IP address, we can look at connecting to the Raspberry Pi. Open VNC Viewer and click the ‘+’ sign to set up a new connection. Leave the name blank for the moment, enter an IP address and choose ‘Save password’. It will ask for the password when you attempt to connect, after which it will then save it and not require it in the future

<strong>Use VNC</strong>

If this is the fi rst time that you are using VNC software, you will notice that there can be a little lag between what you do and what happens on-screen. Luckily, you can use your finger on the screen to move the mouse and tap to click, and the Android keyboard can be used as the keyboard. It can take a bit of getting used to and is not good for anything that you need to do fast, but it’s still very useful.

<strong>Turn it all off</strong>

Killing the VNC server can still be done when connected – your Android device will just disconnect. The same occurs if you just turn off the Pi. If you disconnect the VNC client from the Pi though, the server on the Pi will still be turned on; this means that you can at least reconnect at any time.

<strong>Turn server on at startup</strong>

Currently, every time you turn on the Pi you’ll have to turn on the VNC server. There’s no confi g setting or service setting that we can set to have it turn on by default, so to actually do this we need to write a script. Create a fi le using nano in the terminal at the following location
<pre>sudo nano /etc/init.d/vncserver</pre>
<strong>Write the script</strong>
<pre>#!/bin/sh -e
export USER=“pi”
# parameters for tightvncserver
DISPLAY=“1”
DEPTH=“16”
GEOMETRY=“1920x1080”
NAME=“VNCserver”
OPTIONS=“-name ${NAME} -depth ${DEPTH} -geometry
${GEOMETRY} :${DISPLAY}”
. /lib/lsb/init-functions
case “$1” in
start)
log_action_begin_msg “Starting vncserver for user
‘${USER}’ on localhost:{$DISPLAY}”
su ${USER} -c “/usr/bin/vncserver ${OPTIONS}”
;;
stop)
log_action_begin_msg “Stopping vncserver for user
‘${USER}’ on localhost:{$DISPLAY}”
su ${USER} -c “/usr/bin/vncserver -kill :${DISPLAY}”
;;
restart)
$0 stop
$0 start
;;
esac
exit 0</pre>
<strong>Make the file executable</strong>
<pre>sudo chmod +x /etc/init.d/vncserver</pre>
<strong>Update and test</strong>

The final step is to update the file rc.d (which handles startup scripts and such) so that it knows our new script is there. Do this with the following
<pre>sudo update-rc.d vncserver defaults</pre>
or can then also test it by using the following to make sure it works and also to turn it on for this session
<pre>sudo /etc/init.d/vncserver start</pre>
&nbsp;
<pre></pre>
