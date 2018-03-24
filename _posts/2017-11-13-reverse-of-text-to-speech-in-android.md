---
layout: post
title: Reverse of Text to Speech in Android
date: 2017-11-13 17:37
author: gurnoor
comments: true
categories: [Daily Diary]
---
The reverse of Text To Speech is also possible using following code
<pre>  SpeechRecognizer speechRecognizer;</pre>
Initialization of SpeechRecognizer
<pre> speechRecognizer = SpeechRecognizer.createSpeechRecognizer(this);
 speechRecognizer.setRecognitionListener(this);</pre>
&nbsp;

Even we can perform some action using its methods like one is:-
<pre> public void onResults(Bundle results) {
 ArrayList&lt;String&gt; resultList = results.getStringArrayList(SpeechRecognizer.RESULTS_RECOGNITION);
 StringBuilder builder = new StringBuilder();

 for(String s : resultList){

 if(s.toLowerCase().contains("emergency")){
 //Intent i = new Intent(Intent.ACTION_CALL);

 break;
 }

 builder.append(s);
 }

 textView.setText(builder.toString());
 }</pre>
etc.

Sample screenshots of a simple app:-
<div class="tiled-gallery type-rectangular" data-original-width="616" data-carousel-extra="{&quot;blog_id&quot;:119845696,&quot;permalink&quot;:&quot;https:\/\/androidailyblog.wordpress.com\/2016\/09\/09\/speech-to-text\/&quot;,&quot;likes_blog_id&quot;:119845696}">
<div class="gallery-row" data-original-width="616" data-original-height="362">
<div class="gallery-group images-1" data-original-width="206" data-original-height="362">
<div class="tiled-gallery-item tiled-gallery-item-small"><a href="https://androidailyblog.wordpress.com/wp-1482635730699-png/"> <img title="wp-1482635730699.png" src="https://androidailyblog.files.wordpress.com/2016/12/wp-1482635730699.png?w=202&amp;h=358" alt="wp-1482635730699.png" width="202" height="358" data-attachment-id="638" data-orig-file="https://androidailyblog.files.wordpress.com/2016/12/wp-1482635730699.png" data-orig-size="720,1280" data-comments-opened="1" data-image-meta="{&quot;aperture&quot;:&quot;0&quot;,&quot;credit&quot;:&quot;&quot;,&quot;camera&quot;:&quot;&quot;,&quot;caption&quot;:&quot;&quot;,&quot;created_timestamp&quot;:&quot;0&quot;,&quot;copyright&quot;:&quot;&quot;,&quot;focal_length&quot;:&quot;0&quot;,&quot;iso&quot;:&quot;0&quot;,&quot;shutter_speed&quot;:&quot;0&quot;,&quot;title&quot;:&quot;&quot;,&quot;orientation&quot;:&quot;0&quot;}" data-image-title="wp-1482635730699.png" data-image-description="" data-medium-file="https://androidailyblog.files.wordpress.com/2016/12/wp-1482635730699.png?w=169" data-large-file="https://androidailyblog.files.wordpress.com/2016/12/wp-1482635730699.png?w=576" data-original-width="202" data-original-height="358" /> </a></div>
</div>
<div class="gallery-group images-1" data-original-width="205" data-original-height="362">
<div class="tiled-gallery-item tiled-gallery-item-small"><a href="https://androidailyblog.wordpress.com/wp-1482635759148-png/"> <img title="wp-1482635759148.png" src="https://androidailyblog.files.wordpress.com/2016/12/wp-1482635759148.png?w=201&amp;h=358" alt="wp-1482635759148.png" width="201" height="358" data-attachment-id="640" data-orig-file="https://androidailyblog.files.wordpress.com/2016/12/wp-1482635759148.png" data-orig-size="720,1280" data-comments-opened="1" data-image-meta="{&quot;aperture&quot;:&quot;0&quot;,&quot;credit&quot;:&quot;&quot;,&quot;camera&quot;:&quot;&quot;,&quot;caption&quot;:&quot;&quot;,&quot;created_timestamp&quot;:&quot;0&quot;,&quot;copyright&quot;:&quot;&quot;,&quot;focal_length&quot;:&quot;0&quot;,&quot;iso&quot;:&quot;0&quot;,&quot;shutter_speed&quot;:&quot;0&quot;,&quot;title&quot;:&quot;&quot;,&quot;orientation&quot;:&quot;0&quot;}" data-image-title="wp-1482635759148.png" data-image-description="" data-medium-file="https://androidailyblog.files.wordpress.com/2016/12/wp-1482635759148.png?w=169" data-large-file="https://androidailyblog.files.wordpress.com/2016/12/wp-1482635759148.png?w=576" data-original-width="201" data-original-height="358" /> </a></div>
</div>
<div class="gallery-group images-1" data-original-width="205" data-original-height="362">
<div class="tiled-gallery-item tiled-gallery-item-small"><a href="https://androidailyblog.wordpress.com/wp-1482635741675-png/"> <img title="wp-1482635741675.png" src="https://androidailyblog.files.wordpress.com/2016/12/wp-1482635741675.png?w=201&amp;h=358" alt="wp-1482635741675.png" width="201" height="358" data-attachment-id="639" data-orig-file="https://androidailyblog.files.wordpress.com/2016/12/wp-1482635741675.png" data-orig-size="720,1280" data-comments-opened="1" data-image-meta="{&quot;aperture&quot;:&quot;0&quot;,&quot;credit&quot;:&quot;&quot;,&quot;camera&quot;:&quot;&quot;,&quot;caption&quot;:&quot;&quot;,&quot;created_timestamp&quot;:&quot;0&quot;,&quot;copyright&quot;:&quot;&quot;,&quot;focal_length&quot;:&quot;0&quot;,&quot;iso&quot;:&quot;0&quot;,&quot;shutter_speed&quot;:&quot;0&quot;,&quot;title&quot;:&quot;&quot;,&quot;orientation&quot;:&quot;0&quot;}" data-image-title="wp-1482635741675.png" data-image-description="" data-medium-file="https://androidailyblog.files.wordpress.com/2016/12/wp-1482635741675.png?w=169" data-large-file="https://androidailyblog.files.wordpress.com/2016/12/wp-1482635741675.png?w=576" data-original-width="201" data-original-height="358" /> </a></div>
</div>
</div>
</div>
