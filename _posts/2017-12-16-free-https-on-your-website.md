---
layout: post
title: Free HTTPS on your website
date: 2017-12-16 18:25
author: gurnoor
comments: true
categories: [Daily Diary]
---
You can get free SSL certificate for your website. Today I will tell you the procedure for Linux server having apache web server.
<div class="install">
<h3>Install</h3>
On Ubuntu systems, the Certbot team maintains a <a href="https://help.ubuntu.com/community/PPA">PPA</a>. Once you add it to your list of repositories all you'll need to do is apt-get the following packages.
<pre>$ sudo apt-get update
$ sudo apt-get install software-properties-common
$ sudo add-apt-repository ppa:certbot/certbot
$ sudo apt-get update
$ sudo apt-get install python-certbot-apache 
</pre>
</div>
<div class="get-started">
<h3>Get Started</h3>
Certbot has a fairly solid beta-quality Apache plugin, which is supported on many platforms, and automates both obtaining and installing certs:
<pre>$ sudo certbot --apache</pre>
Running this command will get a certificate for you and have Certbot edit your Apache configuration automatically to serve it. If you're feeling more conservative and would like to make the changes to your Apache configuration by hand, you can use the <tt>certonly</tt> subcommand:
<pre>$ sudo certbot --apache certonly</pre>
To learn more about how to use Certbot <a href="https://certbot.eff.org/docs">read our documentation</a>.
<h3>Automating renewal</h3>
The Certbot packages on your system come with a cron job that will renew your certificates automatically before they expire. Since Let's Encrypt certificates last for 90 days, it's highly advisable to take advantage of this feature. You can test automatic renewal for your certificates by running this command:
<pre>$ sudo certbot renew --dry-run
</pre>
If that appears to be working correctly, you can arrange for automatic renewal by adding a <tt>cron</tt> or <tt>systemd</tt> job which runs the following:
<pre>certbot renew</pre>
</div>
