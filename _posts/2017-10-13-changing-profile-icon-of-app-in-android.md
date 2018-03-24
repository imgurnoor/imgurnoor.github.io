---
layout: post
title: Changing profile icon of app in Android
date: 2017-10-13 17:21
author: gurnoor
comments: true
categories: [Daily Diary]
---
<div>The default Icon of the app can be changed easily.</div>
<ul>
 	<li>Firstly, we need a logo in PNG format and it should not be very big in size and dimensions.</li>
 	<li>Copy it.</li>
 	<li>Paste it in mipmap in res or in drawables of res. Drawables is more preferable.</li>
 	<li>Now, go to AndroidManifest.XML file.</li>
 	<li>Change the path in
<pre>android:icon="@mipmap/ic_launcher"</pre>
to
<pre>android:icon="@drawables/app_logo"</pre>
</li>
 	<li>Now the Icon of the app will be changed.</li>
</ul>
