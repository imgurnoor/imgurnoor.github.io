---
layout: post
title: Activity Lifecycle
date: 2017-08-18 15:22
author: gurnoor
comments: true
categories: [Daily Diary]
---
<figure class="post-image clear-fix"></figure>
<figure class="post-image clear-fix"></figure>
<div class="post-inner">
<div class="post-content">

Over the course of its lifetime, an activity goes through a number of states. You use a series of callbacks to handle transitions between states. The following sections introduce these callbacks.
<h3 id="oncreate">onCreate()</h3>
You must implement this callback, which fires when the system creates your activity. Your implementation should initialize the essential components of your activity: For example, your app should create views and bind data to lists here. Most importantly, this is where you must call setCintentView() to define the layout for the activity’s user interface.

When onCreate finishes, the next callback is always onStart().
<h3 id="onstart">onStart()</h3>
As onCreate() exits, the activity enters the Started state, and the activity becomes visible to the user. This callback contains what amounts to the activity’s final preparations for coming to the foreground and becoming interactive.
<h3 id="onresume">onResume()</h3>
The system invokes this callback just before the activity starts interacting with the user. At this point, the activity is at the top of the activity stack, and captures all user input. Most of an app’s core functionality is implemented in the onResume() method.

The onPause() callback always follows onResume().
<h3 id="onpause">onPause()</h3>
The system calls onPause() when the activity loses focus and enters a Paused state. This state occurs when, for example, the user taps the Back or Overlay button. When the system calls onPause() for your activity, it technically means your activity is still partially visible, but most often is an indication that the user is leaving the activity, and the activity will soon enter the Stopped or Resumed state.

An activity in the Paused state may continue to update the UI if the user is expecting the UI to update. Examples of such an activity include one showing a navigation map screen or a media player playing. Even if such activities lose focus, the user expects their UI to continue updating.

You should <strong>not</strong> use onPause() to save application or user data, make network calls, or execute database transactions.

Once onPause() finishes executing, the next callback is either onStop() or onRestart() , depending on what happens after the activity enters the Paused state.
<h3 id="onstop">onStop()</h3>
The system calls onStop() when the activity is no longer visible to the user. This may happen because the activity is being destroyed, a new activity is starting, or an existing activity is entering a Resumed state and is covering the stopped activity. In all of these cases, the stopped activity is no longer visible at all.

The next callback that the system calls is either onRestart(), if the activity is coming back to interact with the user, or by onDestroy() if this activity is completely terminating.
<h3 id="onrestart">onRestart()</h3>
The system invokes this callback when an activity in the Stopped state is about to restart. onRestart() restores the state of the activity from the time that it was stopped.

This callback is always followed by onStart().
<h3 id="ondestroy">onDestroy()</h3>
The system invokes this callback before an activity is destroyed.

This callback is the final one that the activity receives. onDestroy() is usually implemented to ensure that all of an activity’s resources are released when the activity, or the process containing it, is destroyed.

<img src="https://www.tutorialspoint.com/android/images/activity.jpg" alt="Android Activity lifecycle" />

&nbsp;

</div>
</div>
