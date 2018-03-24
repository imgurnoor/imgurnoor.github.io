---
layout: post
title: Intent object in Android
date: 2017-09-25 17:15
author: gurnoor
comments: true
categories: [Daily Diary]
---
An Intent object is a bundle of information which is used by the component that receives the intent as well as information used by the Android system.

An Intent object can contain the following components based on what it is communicating or going to perform −
<h3>Action</h3>
This is mandatory part of the Intent object and is a string naming the action to be performed — or, in the case of broadcast intents, the action that took place and is being reported. The action largely determines how the rest of the intent object is structured . The Intent class defines a number of action constants corresponding to different intents. Here is a list of <a href="https://www.tutorialspoint.com/android/android_intent_standard_actions.htm">Android Intent Standard Actions</a>

The action in an Intent object can be set by the setAction() method and read by getAction().
<h3>Data</h3>
Adds a data specification to an intent filter. The specification can be just a data type (the mimeType attribute), just a URI, or both a data type and a URI. A URI is specified by separate attributes for each of its parts −

These attributes that specify the URL format are optional, but also mutually dependent −
<ul class="list">
 	<li>If a scheme is not specified for the intent filter, all the other URI attributes are ignored.</li>
 	<li>If a host is not specified for the filter, the port attribute and all the path attributes are ignored.</li>
</ul>
The setData() method specifies data only as a URI, setType() specifies it only as a MIME type, and setDataAndType() specifies it as both a URI and a MIME type. The URI is read by getData() and the type by getType().

Some examples of action/data pairs are −
<table class="table table-bordered">
<tbody>
<tr>
<th>Sr.No.</th>
<th>Action/Data Pair &amp; Description</th>
</tr>
<tr>
<td>1</td>
<td><b>ACTION_VIEW content://contacts/people/1</b>Display information about the person whose identifier is “1”.</td>
</tr>
<tr>
<td>2</td>
<td><b>ACTION_DIAL content://contacts/people/1</b>Display the phone dialer with the person filled in.</td>
</tr>
<tr>
<td>3</td>
<td><b>ACTION_VIEW tel:123</b>Display the phone dialer with the given number filled in.</td>
</tr>
<tr>
<td>4</td>
<td><b>ACTION_DIAL tel:123</b>Display the phone dialer with the given number filled in.</td>
</tr>
<tr>
<td>5</td>
<td><b>ACTION_EDIT content://contacts/people/1</b>Edit information about the person whose identifier is “1”.</td>
</tr>
<tr>
<td>6</td>
<td><b>ACTION_VIEW content://contacts/people/</b>Display a list of people, which the user can browse through.</td>
</tr>
<tr>
<td>7</td>
<td><b>ACTION_SET_WALLPAPER</b>Show settings for choosing wallpaper</td>
</tr>
<tr>
<td>8</td>
<td><b>ACTION_SYNC</b>It going to be synchronous the data,Constant Value is <b>android.intent.action.SYNC</b></td>
</tr>
<tr>
<td>9</td>
<td><b>ACTION_SYSTEM_TUTORIAL</b>It will start the platform-defined tutorial(Default tutorial or start up tutorial)</td>
</tr>
<tr>
<td>10</td>
<td><b>ACTION_TIMEZONE_CHANGED</b>It intimates when time zone has changed</td>
</tr>
<tr>
<td>11</td>
<td><b>ACTION_UNINSTALL_PACKAGE</b>It is used to run default uninstaller</td>
</tr>
</tbody>
</table>
<h3>Category</h3>
The category is an optional part of Intent object and it’s a string containing additional information about the kind of component that should handle the intent. The addCategory() method places a category in an Intent object, removeCategory() deletes a category previously added, and getCategories() gets the set of all categories currently in the object. Here is a list of <a href="https://www.tutorialspoint.com/android/android_intent_standard_categories.htm">Android Intent Standard Categories</a>.

You can check detail on Intent Filters in below section to understand how do we use categories to choose appropriate activity corresponding to an Intent.
<h3>Extras</h3>
This will be in key-value pairs for additional information that should be delivered to the component handling the intent. The extras can be set and read using the putExtras() and getExtras() methods respectively. Here is a list of <a href="https://www.tutorialspoint.com/android/android_intent_standard_extra_data.htm">Android Intent Standard Extra Data</a>
<h3>Flags</h3>
These flags are optional part of Intent object and instruct the Android system how to launch an activity, and how to treat it after it’s launched etc.
<table class="table table-bordered">
<tbody>
<tr>
<th>Sr.No</th>
<th>Flags &amp; Description</th>
</tr>
<tr>
<td>1</td>
<td><b>FLAG_ACTIVITY_CLEAR_TASK</b>If set in an Intent passed to Context.startActivity(), this flag will cause any existing task that would be associated with the activity to be cleared before the activity is started. That is, the activity becomes the new root of an otherwise empty task, and any old activities are finished. This can only be used in conjunction with FLAG_ACTIVITY_NEW_TASK.</td>
</tr>
<tr>
<td>2</td>
<td><b>FLAG_ACTIVITY_CLEAR_TOP</b>If set, and the activity being launched is already running in the current task, then instead of launching a new instance of that activity, all of the other activities on top of it will be closed and this Intent will be delivered to the (now on top) old activity as a new Intent.</td>
</tr>
<tr>
<td>3</td>
<td><b>FLAG_ACTIVITY_NEW_TASK</b>This flag is generally used by activities that want to present a “launcher” style behavior: they give the user a list of separate things that can be done, which otherwise run completely independently of the activity launching them..</td>
</tr>
</tbody>
</table>
