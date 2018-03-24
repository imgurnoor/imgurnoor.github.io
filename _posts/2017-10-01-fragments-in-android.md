---
layout: post
title: Fragments in Android
date: 2017-10-01 17:17
author: gurnoor
comments: true
categories: [Daily Diary]
---
<div class="article-content entry-content">
<div dir="ltr">
<blockquote>A <b>Fragment </b>is a piece of an activity which enable more modular activity design. It will not be wrong if we say, a fragment is a kind of<b>sub-activity</b>.</blockquote>
<div>Following are important points about fragment −</div>
<ul class="list">
 	<li>
<div>A fragment has its own layout and its own behaviour with its own life cycle callbacks.</div></li>
 	<li>
<div>You can add or remove fragments in an activity while the activity is running.</div></li>
 	<li>
<div>You can combine multiple fragments in a single activity to build a multi-plane UI.</div></li>
 	<li>
<div>A fragment can be used in multiple activities.</div></li>
 	<li>
<div>Fragment life cycle is closely related to the life cycle of its host activity which means when the activity is paused, all the fragments available in the activity will also be stopped.</div></li>
 	<li>
<div>A fragment can implement a behaviour that has no user interface component.</div></li>
 	<li>
<div>Fragments were added to the Android API in Honeycomb version of Android which API version 11.</div></li>
</ul>
<h2>Fragment Life Cycle</h2>
Android fragments have their own life cycle very similar to an android activity. This section briefs different stages of its life cycle.

<img src="https://www.tutorialspoint.com/android/images/fragment.jpg" alt="Fragment" />
<h4 align="Center">FRAGMENT LIFECYCLE</h4>
Here is the list of methods which you can to override in your fragment class −
<ul class="list">
 	<li><b>onAttach()</b>The fragment instance is associated with an activity instance.The fragment and the activity is not fully initialized. Typically you get in this method a reference to the activity which uses the fragment for further initialization work.</li>
 	<li><b>onCreate()</b> The system calls this method when creating the fragment. You should initialize essential components of the fragment that you want to retain when the fragment is paused or stopped, then resumed.</li>
 	<li><b>onCreateView()</b> The system calls this callback when it’s time for the fragment to draw its user interface for the first time. To draw a UI for your fragment, you must return a <b>View</b> component from this method that is the root of your fragment’s layout. You can return null if the fragment does not provide a UI.</li>
 	<li><b>onActivityCreated()</b>The onActivityCreated() is called after the onCreateView() method when the host activity is created. Activity and fragment instance have been created as well as the view hierarchy of the activity. At this point, view can be accessed with the findViewById() method. example. In this method you can instantiate objects which require a Context object</li>
 	<li><b>onStart()</b>The onStart() method is called once the fragment gets visible.</li>
 	<li><b>onResume()</b>Fragment becomes active.</li>
 	<li><b>onPause()</b> The system calls this method as the first indication that the user is leaving the fragment. This is usually where you should commit any changes that should be persisted beyond the current user session.</li>
 	<li><b>onStop()</b>Fragment going to be stopped by calling onStop()</li>
 	<li><b>onDestroyView()</b>Fragment view will destroy after call this method</li>
 	<li><b>onDestroy()</b>onDestroy() called to do final clean up of the fragment’s state but Not guaranteed to be called by the Android platform</li>
</ul>
</div>
</div>
