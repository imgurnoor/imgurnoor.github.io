---
layout: post
title: Update Mapnik Version on OSM server.
date: 2017-07-03 10:55
author: gurnoor30
comments: true
categories: [OSM]
---
<b>Mapnik</b> is an open source toolkit for rendering maps. To update mapnik version you first of all need to check current mapnik version installed on your system. For that use command
<pre>mapnik-config -v</pre>
If the program 'mapnik-config' is currently not installed. You can install it by typing:
<pre>sudo apt-get install libmapnik2-dev</pre>
In my case, I have to update from mapnik 2.3.0 to the latest version. So to update issue following commands.
<pre><code># you might have to update your outdated clang
sudo add-apt-repository -y ppa:ubuntu-toolchain-r/test
sudo apt-get update -y
sudo apt-get install -y gcc-6 g++-6 clang-3.8
export CXX="clang++-3.8" &amp;&amp; export CC="clang-3.8"

# install mapnik
git clone https://github.com/mapnik/mapnik mapnik-3.x --depth 10
cd mapnik-3.x
git submodule update --init
sudo apt-get install python zlib1g-dev clang make pkg-config curl
source bootstrap.sh
./configure CUSTOM_CXXFLAGS="-D_GLIBCXX_USE_CXX11_ABI=0" CXX=${CXX} CC=${CC}
make
make test
sudo make install</code></pre>
Make sure that you get no error while issuing make command.

After that, you have to update the path of <strong>plugin</strong> directory (the one where you clone mapnik-3.x ) of mapnik in renderd.conf file which is located at <strong>/usr/local/etc/.</strong>

What mistake I did was giving the incomplete path to the plugin directory. You have to give complete path up to <strong>input</strong> directory of mapnik.

<img class="alignnone wp-image-585 size-full" src="https://www.singhgurnoor.com/wp-content/uploads/2017/07/mapnik5.png" alt="mapnik5" width="485" height="93" />

&nbsp;

You can verify your updated version by giving mapnik-config -v command as mentioned above.

<img class="alignnone wp-image-578 size-full" src="https://www.singhgurnoor.com/wp-content/uploads/2017/07/mapnik1.png" alt="mapnik1" width="597" height="39" />

Also, you should get " rendering is using mapnik "latest version" ."  after issuing
<pre>renderd -f -c /usr/local/etc/renderd.conf</pre>
<img class="alignnone wp-image-577 size-full" src="https://www.singhgurnoor.com/wp-content/uploads/2017/07/mapnik.png" alt="mapnik" width="982" height="181" />

In the next blog, I will discuss about the errors I received while compiling mod_tile with <strong>make</strong> command and their respective solution.
