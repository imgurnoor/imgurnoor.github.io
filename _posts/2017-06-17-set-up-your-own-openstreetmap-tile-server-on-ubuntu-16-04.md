---
layout: post
title: Set up Your Own OpenStreetMap Tile Server on Ubuntu 16.04
date: 2017-06-17 14:23
author: gurnoor30
comments: true
categories: [OSM]
---
From last two days I was struggling for the deployment  of OSM Tile Server on my machine because I was getting <strong>" NOT Found"</strong> error on  URL :-
<pre>localhost/osm_tiles/0/0/0.png</pre>
I followed <a href="https://www.linuxbabe.com/linux-server/openstreetmap-tile-server-ubuntu-16-04" target="_blank" rel="noopener">linuxbabe</a> link to set my tile server so I will not go into much detail regarding the setup instructions, For that you can follow that link.

I will here discuss the errors which I faced and the corresponding solution for that.
<ul>
 	<li>
<h3><strong>Download Map Data</strong></h3>
</li>
</ul>
I accidentally downloaded the .osh file of India from <a href="http://download.geofabrik.de/asia/india.html" target="_blank" rel="noopener">http://download.geofabrik.de/asia/india.html </a>which was not properly processed . So to resolve that issue I downloaded the .osm file with the help of command
<pre>wget -c http://download.geofabrik.de/asia/india-latest.osm.pbf</pre>
<ul>
 	<li>
<h3><strong>Syntax error in rendered.conf file</strong></h3>
</li>
</ul>
In editing step of rendered.conf file I accidentally put ' ; '  before [rendered] and also the path of  XML was also not correct under [default] section.

&nbsp;
<ul>
 	<li>
<h3><strong>Error : Socket bind failed for: /var/run/renderd/renderd.sock</strong></h3>
</li>
</ul>
So to resolve this error i followed  <a href="https://stackoverflow.com/questions/16851034/i-get-an-error-saying-socket-bind-failed-for-var-run-renderd-renderd-sock-if-i/28884976#28884976" target="_blank" rel="noopener">this</a> link , In my case It was <strong>missing writing rights </strong>which I resolved by using this command
<pre>sudo chown osm:osm /var/lib/mod_tile</pre>
<ul>
 	<li>
<h3><strong>Rendering Issue</strong></h3>
</li>
</ul>
If you are facing any issue related to rendering of file then you can use this command
<pre>renderd -f -c /usr/local/etc/renderd.conf</pre>
<ul>
 	<li>
<h3><strong>Default path of localhost</strong></h3>
</li>
</ul>
So if you are following the above mentioned <a href="https://www.linuxbabe.com/linux-server/openstreetmap-tile-server-ubuntu-16-04" target="_blank" rel="noopener">link</a> to download JavaScript library, they make a directory in
<pre>/var/www/osm</pre>
So you are suppose to extract your files in this directory. After extracting files and creating index.html file in the same directory you are suppose to change the path of <strong>Documentroot</strong> as
<pre> /var/www/osm</pre>
which is located at
<pre><strong> /etc/apache2/sites-available/000-default.conf.
</strong></pre>
If you don't want to explicitly change <strong>Documentroot</strong>, you can then extract your files in /var/www, which is the  default path of localhost.
