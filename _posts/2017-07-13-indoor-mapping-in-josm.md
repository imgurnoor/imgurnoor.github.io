---
layout: post
title: Indoor Mapping in JOSM
date: 2017-07-13 18:54
author: gurnoor30
comments: true
categories: [Daily Diary, OSM]
---
Today, I did indoor mapping of MBA block of Guru Nanak Dev Engineering College, Ludhiana in JOSM. So for that, I followed <a href="http://wiki.openstreetmap.org/wiki/Proposed_features/IndoorOSM#The_Model_.2F_Tagging_Schema">this</a> link.

To clarify your vision regarding the area of rooms in the building you need a blueprint/plan of that building in image format for reference. For eg below is the plan of MBA block.

<img class="alignnone wp-image-626 size-full" src="https://www.singhgurnoor.com/wp-content/uploads/2017/07/mba-e1499968631355.jpg" alt="" width="550" height="380" />

For using the image for mapping in JOSM you need <strong>PicLayer-plugin</strong>. This can be done by
<pre>Edit -&gt; Preferences (F12) -&gt; Configure available plugins</pre>
Afterwards, the created picture can be loaded into JOSM by selecting
<pre>PicLayer -&gt; New picture layer from file</pre>
After that import osm data as a base layer and then place the image of MBA block on the top of the base layer of osm map layer where MBA block is located. It is like doing a drawing with the help of tracing paper. So here the pic of MBA block is acting as a tracing paper.

To position and scale MBA block pic on osm layer tag the corners of the plan (green arrow-button <a class="image" href="http://wiki.openstreetmap.org/wiki/File:05.Symbol_PicLayer01.jpg"><img src="http://wiki.openstreetmap.org/w/images/8/8e/05.Symbol_PicLayer01.jpg" alt="05.Symbol PicLayer01.jpg" width="35" height="35" /></a> ).

<img class="alignnone wp-image-622 size-full" src="https://www.singhgurnoor.com/wp-content/uploads/2017/07/dd3.png" alt="" width="1366" height="768" />

You need to click on the left side of image layer in order to get image adjusting tools as shown in the above screenshot.

Before the mapping activities can start, the OSM Layer must be activated. Then the rooms can be created (“Draw nodes”), this is done in the same way as one would map a normal polygon.

<img class="alignnone wp-image-623 size-full" src="https://www.singhgurnoor.com/wp-content/uploads/2017/07/dd5.png" alt="" width="201" height="167" />

After mapping, you can delete image layer and then you are left with

<img class="alignnone wp-image-625 size-full" src="https://www.singhgurnoor.com/wp-content/uploads/2017/07/dd7.png" alt="" width="156" height="198" />

Afterwards, different properties (tags) can be added to the different OSM features: doors, stairways, elevator, windows, rooms.

To add this manually is a complex task. So, the more efficient approach is to use the<strong> indoor-helper plugin.</strong>

<img class="alignnone wp-image-621 size-full" src="https://www.singhgurnoor.com/wp-content/uploads/2017/07/dd2.png" alt="" width="1365" height="750" />

Adding details via this plugin is very simple. You just need to click the power button after selecting pin icon on the upper right corner of the window and then add the details by selecting the level of building and so on...

<img class="alignnone wp-image-624 size-full" src="https://www.singhgurnoor.com/wp-content/uploads/2017/07/dd6.png" alt="" width="672" height="550" />

Today I edited ground floor of MBA block. I didn't edit the first floor and the second floor because before that I need to figure out how can I show the indoor details of multi-story building on the 2D and 3D map.

<img class="alignnone wp-image-627 size-full" src="https://www.singhgurnoor.com/wp-content/uploads/2017/07/dd8.png" alt="" width="387" height="478" />

Also to show the indoor mapping of MBA block on the map I need to explore its code like that of <a href="http://clement-lagrange.github.io/osmtools-indoor/#lat=50.60950&amp;lon=3.13776&amp;z=21&amp;room=224&amp;id_building=3440826&amp;id_level=3473285&amp;id_room=258772069">http://clement-lagrange.github.io/osmtools-indoor/#lat=50.60950&amp;lon=3.13776&amp;z=21&amp;room=224&amp;id_building=3440826&amp;id_level=3473285&amp;id_room=258772069 </a>which I will do tomorrow.

&nbsp;
