---
layout: post
title: WebView in Android
date: 2017-10-07 17:19
author: gurnoor
comments: true
categories: [Daily Diary]
---
WebView is a view that display web pages inside your application. You can also specify HTML string and can show it inside your application using WebView. WebView makes turns your application to a web application.

In order to add WebView to your application, you have to add <b>&lt;WebView&gt;</b> element to your xml layout file. Its syntax is as follows −
<pre class="prettyprint notranslate prettyprinted"><span class="tag">&lt;WebView</span>  <span class="atn">xmlns:android</span><span class="pun">=</span><span class="atv">"http://schemas.android.com/apk/res/android"</span>
   <span class="atn">android:id</span><span class="pun">=</span><span class="atv">"@+id/webview"</span>
   <span class="atn">android:layout_width</span><span class="pun">=</span><span class="atv">"fill_parent"</span>
   <span class="atn">android:layout_height</span><span class="pun">=</span><span class="atv">"fill_parent"</span>
<span class="tag">/&gt;</span></pre>
In order to use it, you have to get a reference of this view in Java file. To get a reference, create an object of the class WebView. Its syntax is −
<pre class="result notranslate">WebView browser = (WebView) findViewById(R.id.webview);
</pre>
In order to load a web url into the WebView, you need to call a method <b>loadUrl(String url)</b> of the WebView class, specifying the required url. Its syntax is:
<pre class="result notranslate">browser.loadUrl("http://www.google.com");
</pre>
Apart from just loading url, you can have more control over your WebView by using the methods defined in WebView class. They are listed as follows −
<table class="table table-bordered">
<tbody>
<tr>
<th>Sr.No</th>
<th>Method &amp; Description</th>
</tr>
<tr>
<td>1</td>
<td><b>canGoBack()</b>This method specifies the WebView has a back history item.</td>
</tr>
<tr>
<td>2</td>
<td><b>canGoForward()</b>This method specifies the WebView has a forward history item.</td>
</tr>
<tr>
<td>3</td>
<td><b>clearHistory()</b>This method will clear the WebView forward and backward history.</td>
</tr>
<tr>
<td>4</td>
<td><b>destroy()</b>This method destroy the internal state of WebView.</td>
</tr>
<tr>
<td>5</td>
<td><b>findAllAsync(String find)</b>This method find all instances of string and highlight them.</td>
</tr>
<tr>
<td>6</td>
<td><b>getProgress()</b>This method gets the progress of the current page.</td>
</tr>
<tr>
<td>7</td>
<td><b>getTitle()</b>This method return the title of the current page.</td>
</tr>
<tr>
<td>8</td>
<td><b>getUrl()</b>This method return the url of the current page.</td>
</tr>
</tbody>
</table>
If you click on any link inside the webpage of the WebView, that page will not be loaded inside your WebView. In order to do that you need to extend your class from <b>WebViewClient</b> and override its method. Its syntax is −
<pre class="prettyprint notranslate prettyprinted"><span class="kwd">private</span> <span class="kwd">class</span> <span class="typ">MyBrowser</span> <span class="kwd">extends</span> <span class="typ">WebViewClient</span> <span class="pun">{</span>
   <span class="lit">@Override</span>
   <span class="kwd">public</span> <span class="kwd">boolean</span><span class="pln"> shouldOverrideUrlLoading</span><span class="pun">(</span><span class="typ">WebView</span><span class="pln"> view</span><span class="pun">,</span> <span class="typ">String</span><span class="pln"> url</span><span class="pun">)</span> <span class="pun">{</span><span class="pln">
      view</span><span class="pun">.</span><span class="pln">loadUrl</span><span class="pun">(</span><span class="pln">url</span><span class="pun">);</span>
      <span class="kwd">return</span> <span class="kwd">true</span><span class="pun">;</span>
   <span class="pun">}</span>
<span class="pun">}</span></pre>
<h2>Example</h2>
Here is an example demonstrating the use of WebView Layout. It creates a basic web application that will ask you to specify a url and will load this url website in the WebView.

To experiment with this example, you need to run this on an actual device on which internet is running.
<table class="table table-bordered">
<tbody>
<tr>
<th>Steps</th>
<th>Description</th>
</tr>
<tr>
<td>1</td>
<td>You will use Android studio to create an Android application under a package com.example.kunwars.myapplication.</td>
</tr>
<tr>
<td>2</td>
<td>Modify src/MainActivity.java file to add WebView code.</td>
</tr>
<tr>
<td>3</td>
<td>Modify the res/layout/activity_main to add respective XML components</td>
</tr>
<tr>
<td>4</td>
<td>Modify the AndroidManifest.xml to add the necessary permissions</td>
</tr>
<tr>
<td>5</td>
<td>Run the application and choose a running android device and install the application on it and verify the results.</td>
</tr>
</tbody>
</table>
