---
layout: post
title: More about UI
date: 2017-08-22 15:27
author: gurnoor
comments: true
categories: [Daily Diary]
---
<blockquote>Input controls are the interactive components in your app’s user interface. Android provides a wide variety of controls you can use in your UI, such as buttons, text fields, seek bars, check box, zoom buttons, toggle buttons, and many more.</blockquote>
<img src="https://www.tutorialspoint.com/android/images/ui_control.jpg" alt="UI Control" />
<h4 align="center">UI ELEMENTS</h4>
A <b>View</b> is an object that draws something on the screen that the user can interact with and a <b>ViewGroup</b> is an object that holds other View (and ViewGroup) objects in order to define the layout of the user interface.

You define your layout in an XML file which offers a human-readable structure for the layout, similar to HTML. For example, a simple vertical layout with a text view and a button looks like this −
<pre class="prettyprint notranslate prettyprinted"><span class="pun">&lt;?</span><span class="pln">xml version</span><span class="pun">=</span><span class="str">"1.0"</span><span class="pln"> encoding</span><span class="pun">=</span><span class="str">"utf-8"</span><span class="pun">?&gt;</span>
<span class="tag">&lt;LinearLayout</span> <span class="atn">xmlns:android</span><span class="pun">=</span><span class="atv">"<span class="skimlinks-unlinked">http://schemas.android.com/apk/res/android</span>"</span>
   <span class="atn">android:layout_width</span><span class="pun">=</span><span class="atv">"fill_parent"</span>
   <span class="atn">android:layout_height</span><span class="pun">=</span><span class="atv">"fill_parent"</span>
   <span class="atn">android:orientation</span><span class="pun">=</span><span class="atv">"vertical"</span> <span class="tag">&gt;</span>
   
   <span class="tag">&lt;TextView</span> <span class="atn">android:id</span><span class="pun">=</span><span class="atv">"@+id/text"</span>
      <span class="atn">android:layout_width</span><span class="pun">=</span><span class="atv">"wrap_content"</span>
      <span class="atn">android:layout_height</span><span class="pun">=</span><span class="atv">"wrap_content"</span>
      <span class="atn">android:text</span><span class="pun">=</span><span class="atv">"I am a TextView"</span> <span class="tag">/&gt;</span>
   
   <span class="tag">&lt;Button</span> <span class="atn">android:id</span><span class="pun">=</span><span class="atv">"@+id/button"</span>
      <span class="atn">android:layout_width</span><span class="pun">=</span><span class="atv">"wrap_content"</span>
      <span class="atn">android:layout_height</span><span class="pun">=</span><span class="atv">"wrap_content"</span>
      <span class="atn">android:text</span><span class="pun">=</span><span class="atv">"I am a Button"</span> <span class="tag">/&gt;</span>
<span class="tag">&lt;/LinearLayout&gt;</span></pre>
<h2>Android UI Controls</h2>
There are number of UI controls provided by Android that allow you to build the graphical user interface for your app.
<table class="table table-bordered">
<tbody>
<tr>
<th><span class="skimlinks-unlinked">Sr.No</span>.</th>
<th>UI Control &amp; Description</th>
</tr>
<tr>
<td>1 . TextView</td>
<td>This control is used to display text to the user.</td>
</tr>
<tr>
<td>2 . EditText</td>
<td>EditText is a predefined subclass of TextView that includes rich editing capabilities.</td>
</tr>
<tr>
<td>3 . AutoCompleteTextView</td>
<td>The AutoCompleteTextView is a view that is similar to EditText, except that it shows a list of completion suggestions automatically while the user is typing.</td>
</tr>
<tr>
<td>4 . Button</td>
<td>A push-button that can be pressed, or clicked, by the user to perform an action.</td>
</tr>
<tr>
<td>5 . ImageButton</td>
<td>An ImageButton is an AbsoluteLayout which enables you to specify the exact location of its children. This shows a button with an image (instead of text) that can be pressed or clicked by the user.</td>
</tr>
<tr>
<td>6. CheckBox</td>
<td>An on/off switch that can be toggled by the user. You should use check box when presenting users with a group of selectable options that are not mutually exclusive.</td>
</tr>
<tr>
<td>7  . ToggleButton</td>
<td>An on/off button with a light indicator.</td>
</tr>
<tr>
<td>8 . RadioButton</td>
<td>The RadioButton has two states: either checked or unchecked.</td>
</tr>
<tr>
<td>9 . RadioGroup</td>
<td>A RadioGroup is used to group together one or more RadioButtons.</td>
</tr>
<tr>
<td>10 . ProgressBar</td>
<td>The ProgressBar view provides visual feedback about some ongoing tasks, such as when you are performing a task in the background.</td>
</tr>
<tr>
<td>11 . Spinner</td>
<td>A drop-down list that allows users to select one value from a set.</td>
</tr>
<tr>
<td>12 . TimePicker</td>
<td>The TimePicker view enables users to select a time of the day, in either 24-hour mode or AM/PM mode.</td>
</tr>
<tr>
<td>13 . DatePicker</td>
<td>The DatePicker view enables users to select a date of the day.</td>
</tr>
</tbody>
</table>
<h2>Create UI Controls</h2>
Input controls are the interactive components in your app’s user interface. Android provides a wide variety of controls you can use in your UI, such as buttons, text fields, seek bars, check box, zoom buttons, toggle buttons, and many more.

As explained in previous chapter, a view object may have a unique ID assigned to it which will identify the View uniquely within the tree. The syntax for an ID, inside an XML tag is −
<pre class="prettyprint notranslate prettyprinted"><span class="pln">android</span><span class="pun">:</span><span class="pln">id</span><span class="pun">=</span><span class="str">"@+id/text_id"</span></pre>
To create a UI Control/View/Widget you will have to define a view/widget in the layout file and assign it a unique ID as follows −
<pre class="prettyprint notranslate prettyprinted"><span class="pun">&lt;?</span><span class="pln">xml version</span><span class="pun">=</span><span class="str">"1.0"</span><span class="pln"> encoding</span><span class="pun">=</span><span class="str">"utf-8"</span><span class="pun">?&gt;</span>
<span class="tag">&lt;LinearLayout</span> <span class="atn">xmlns:android</span><span class="pun">=</span><span class="atv">"<span class="skimlinks-unlinked">http://schemas.android.com/apk/res/android</span>"</span>
   <span class="atn">android:layout_width</span><span class="pun">=</span><span class="atv">"fill_parent"</span> 
   <span class="atn">android:layout_height</span><span class="pun">=</span><span class="atv">"fill_parent"</span>
   <span class="atn">android:orientation</span><span class="pun">=</span><span class="atv">"vertical"</span> <span class="tag">&gt;</span>
   
   <span class="tag">&lt;TextView</span> <span class="atn">android:id</span><span class="pun">=</span><span class="atv">"@+id/text_id"</span>
      <span class="atn">android:layout_width</span><span class="pun">=</span><span class="atv">"wrap_content"</span>
      <span class="atn">android:layout_height</span><span class="pun">=</span><span class="atv">"wrap_content"</span>
      <span class="atn">android:text</span><span class="pun">=</span><span class="atv">"I am a TextView"</span> <span class="tag">/&gt;</span>
<span class="tag">&lt;/LinearLayout&gt;</span></pre>
Then finally create an instance of the Control object and capture it from the layout, use the following −
<pre class="prettyprint notranslate prettyprinted"><span class="typ">TextView</span><span class="pln"> myText </span><span class="pun">=</span> <span class="pun">(</span><span class="typ">TextView</span><span class="pun">)</span><span class="pln"> findViewById</span><span class="pun">(</span><span class="pln">R</span><span class="pun">.</span><span class="pln">id</span><span class="pun">.</span><span class="pln">text_id</span><span class="pun">);</span></pre>
