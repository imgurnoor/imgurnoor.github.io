---
layout: post
title: Text to Speech feature in Android
date: 2017-11-09 17:34
author: gurnoor
comments: true
categories: [Daily Diary]
---
Android allows you convert your text into voice. Not only you can convert it but it also allows you to speak text in variety of different languages.

Android provides <b>TextToSpeech</b> class for this purpose. In order to use this class, you need to instantiate an object of this class and also specify the <b>initListnere</b>. Its syntax is given below −
<pre class="prettyprint notranslate prettyprinted"><span class="kwd">private</span> <span class="typ">EditText</span><span class="pln"> write</span><span class="pun">;</span><span class="pln">
ttobj</span><span class="pun">=</span><span class="kwd">new</span> <span class="typ">TextToSpeech</span><span class="pun">(</span><span class="pln">getApplicationContext</span><span class="pun">(),</span> <span class="kwd">new</span> <span class="typ">TextToSpeech</span><span class="pun">.</span><span class="typ">OnInitListener</span><span class="pun">()</span> <span class="pun">{</span>
   <span class="lit">@Override</span>
   <span class="kwd">public</span> <span class="kwd">void</span><span class="pln"> onInit</span><span class="pun">(</span><span class="kwd">int</span><span class="pln"> status</span><span class="pun">)</span> <span class="pun">{</span>
   <span class="pun">}</span>
<span class="pun">});</span></pre>
In this listener, you have to specify the properties for TextToSpeech object , such as its language ,pitch e.t.c. Language can be set by calling <b>setLanguage()</b> method. Its syntax is given below −
<pre class="result notranslate">ttobj.setLanguage(Locale.UK);
</pre>
The method setLanguage takes an Locale object as parameter. The list of some of the locales available are given below −
<table class="table table-bordered">
<tbody>
<tr>
<th>Sr.No</th>
<th>Locale</th>
</tr>
<tr>
<td>1</td>
<td>US</td>
</tr>
<tr>
<td>2</td>
<td>CANADA_FRENCH</td>
</tr>
<tr>
<td>3</td>
<td>GERMANY</td>
</tr>
<tr>
<td>4</td>
<td>ITALY</td>
</tr>
<tr>
<td>5</td>
<td>JAPAN</td>
</tr>
<tr>
<td>6</td>
<td>CHINA</td>
</tr>
</tbody>
</table>
Once you have set the language, you can call <b>speak</b> method of the class to speak the text. Its syntax is given below −
<pre class="prettyprint notranslate prettyprinted"><span class="pln">ttobj</span><span class="pun">.</span><span class="pln">speak</span><span class="pun">(</span><span class="pln">toSpeak</span><span class="pun">,</span> <span class="typ">TextToSpeech</span><span class="pun">.</span><span class="pln">QUEUE_FLUSH</span><span class="pun">,</span> <span class="kwd">null</span><span class="pun">);</span></pre>
Apart from the speak method, there are some other methods available in the TextToSpeech class. They are listed below −
<table class="table table-bordered">
<tbody>
<tr>
<th>Sr.No</th>
<th>Method &amp; description</th>
</tr>
<tr>
<td>1</td>
<td><b>addSpeech(String text, String filename)</b>This method adds a mapping between a string of text and a sound file.</td>
</tr>
<tr>
<td>2</td>
<td><b>getLanguage()</b>This method returns a Locale instance describing the language.</td>
</tr>
<tr>
<td>3</td>
<td><b>isSpeaking()</b>This method checks whether the TextToSpeech engine is busy speaking.</td>
</tr>
<tr>
<td>4</td>
<td><b>setPitch(float pitch)</b>This method sets the speech pitch for the TextToSpeech engine.</td>
</tr>
<tr>
<td>5</td>
<td><b>setSpeechRate(float speechRate)</b>This method sets the speech rate.</td>
</tr>
<tr>
<td>6</td>
<td><b>shutdown()</b>This method releases the resources used by the TextToSpeech engine.</td>
</tr>
<tr>
<td>7</td>
<td><b>stop()</b>This method stop the speak.</td>
</tr>
</tbody>
</table>
Screen shots of simple app for  text to speech.
<div class="tiled-gallery type-rectangular" data-original-width="616" data-carousel-extra="{&quot;blog_id&quot;:119845696,&quot;permalink&quot;:&quot;https:\/\/androidailyblog.wordpress.com\/2016\/09\/08\/text-to-speech\/&quot;,&quot;likes_blog_id&quot;:119845696}">
<div class="gallery-row" data-original-width="616" data-original-height="362">
<div class="gallery-group images-1" data-original-width="206" data-original-height="362">
<div class="tiled-gallery-item tiled-gallery-item-small"><a href="https://androidailyblog.wordpress.com/wp-1482636107097-png/"> <img title="wp-1482636107097.png" src="https://androidailyblog.files.wordpress.com/2016/12/wp-1482636107097.png?w=202&amp;h=358" alt="wp-1482636107097.png" width="202" height="358" data-attachment-id="646" data-orig-file="https://androidailyblog.files.wordpress.com/2016/12/wp-1482636107097.png" data-orig-size="720,1280" data-comments-opened="1" data-image-meta="{&quot;aperture&quot;:&quot;0&quot;,&quot;credit&quot;:&quot;&quot;,&quot;camera&quot;:&quot;&quot;,&quot;caption&quot;:&quot;&quot;,&quot;created_timestamp&quot;:&quot;0&quot;,&quot;copyright&quot;:&quot;&quot;,&quot;focal_length&quot;:&quot;0&quot;,&quot;iso&quot;:&quot;0&quot;,&quot;shutter_speed&quot;:&quot;0&quot;,&quot;title&quot;:&quot;&quot;,&quot;orientation&quot;:&quot;0&quot;}" data-image-title="wp-1482636107097.png" data-image-description="" data-medium-file="https://androidailyblog.files.wordpress.com/2016/12/wp-1482636107097.png?w=169" data-large-file="https://androidailyblog.files.wordpress.com/2016/12/wp-1482636107097.png?w=576" data-original-width="202" data-original-height="358" /> </a></div>
</div>
<div class="gallery-group images-1" data-original-width="205" data-original-height="362">
<div class="tiled-gallery-item tiled-gallery-item-small"><a href="https://androidailyblog.wordpress.com/wp-1482636181469-png/"> <img title="wp-1482636181469.png" src="https://androidailyblog.files.wordpress.com/2016/12/wp-1482636181469.png?w=201&amp;h=358" alt="wp-1482636181469.png" width="201" height="358" data-attachment-id="648" data-orig-file="https://androidailyblog.files.wordpress.com/2016/12/wp-1482636181469.png" data-orig-size="720,1280" data-comments-opened="1" data-image-meta="{&quot;aperture&quot;:&quot;0&quot;,&quot;credit&quot;:&quot;&quot;,&quot;camera&quot;:&quot;&quot;,&quot;caption&quot;:&quot;&quot;,&quot;created_timestamp&quot;:&quot;0&quot;,&quot;copyright&quot;:&quot;&quot;,&quot;focal_length&quot;:&quot;0&quot;,&quot;iso&quot;:&quot;0&quot;,&quot;shutter_speed&quot;:&quot;0&quot;,&quot;title&quot;:&quot;&quot;,&quot;orientation&quot;:&quot;0&quot;}" data-image-title="wp-1482636181469.png" data-image-description="" data-medium-file="https://androidailyblog.files.wordpress.com/2016/12/wp-1482636181469.png?w=169" data-large-file="https://androidailyblog.files.wordpress.com/2016/12/wp-1482636181469.png?w=576" data-original-width="201" data-original-height="358" /> </a></div>
</div>
<div class="gallery-group images-1" data-original-width="205" data-original-height="362">
<div class="tiled-gallery-item tiled-gallery-item-small"><a href="https://androidailyblog.wordpress.com/wp-1482636088329-png/"> <img title="wp-1482636088329.png" src="https://androidailyblog.files.wordpress.com/2016/12/wp-1482636088329.png?w=201&amp;h=358" alt="wp-1482636088329.png" width="201" height="358" data-attachment-id="645" data-orig-file="https://androidailyblog.files.wordpress.com/2016/12/wp-1482636088329.png" data-orig-size="720,1280" data-comments-opened="1" data-image-meta="{&quot;aperture&quot;:&quot;0&quot;,&quot;credit&quot;:&quot;&quot;,&quot;camera&quot;:&quot;&quot;,&quot;caption&quot;:&quot;&quot;,&quot;created_timestamp&quot;:&quot;0&quot;,&quot;copyright&quot;:&quot;&quot;,&quot;focal_length&quot;:&quot;0&quot;,&quot;iso&quot;:&quot;0&quot;,&quot;shutter_speed&quot;:&quot;0&quot;,&quot;title&quot;:&quot;&quot;,&quot;orientation&quot;:&quot;0&quot;}" data-image-title="wp-1482636088329.png" data-image-description="" data-medium-file="https://androidailyblog.files.wordpress.com/2016/12/wp-1482636088329.png?w=169" data-large-file="https://androidailyblog.files.wordpress.com/2016/12/wp-1482636088329.png?w=576" data-original-width="201" data-original-height="358" /> </a></div>
</div>
</div>
</div>
