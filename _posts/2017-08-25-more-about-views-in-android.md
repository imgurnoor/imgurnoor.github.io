---
layout: post
title: More About Views in Android
date: 2017-08-25 17:03
author: gurnoor
comments: true
categories: [Uncategorized]
---
<h3 id="view-the-user-interface-widgets-in-android">View – The user interface widgets in Android</h3>
<div class="paragraph">

A <em>view</em> in Android represents a widget, e.g., a button, or a layout manager. The Android SDK provides standard views (widgets), e.g., via the <code>Button</code>, <code>TextView</code>, <code>EditText</code> classes. Additional libraries provide more complex widgets, for example, <code>RecyclerView</code>.

</div>
<div class="paragraph">

All views in Android extend the <code>android.view.View</code> class, this class provides a lot of base functionality for subclasses. For example, it provides the base support for touch.

</div>
<div class="paragraph">

The main packages for views are part of the <code>android.view</code> namespace for all the base classes and <code>android.widget</code> for the default widgets of the Android platform.

</div>
&nbsp;
<h3 id="layoutmanager_overview">Using a layout manager</h3>
<div class="paragraph">

A layout manager is responsible for layouting itself and its child <code>Views</code> It is a subclass of <code>ViewGroup</code>.

</div>
<div class="paragraph">

Android supports different default layout managers.

</div>
<div class="paragraph">

The most relevant layout managers in Android are:

</div>
<div class="ulist">
<ul>
 	<li><code>LinearLayout</code></li>
 	<li><code>RelativeLayout</code></li>
 	<li><code>GridLayout etc</code></li>
</ul>
<h3 id="layoutmanager_attributes">Layout attributes</h3>
<div class="paragraph">

All layout manager can be configured via attributes. We can specify their desired width and height via the following attributes.

</div>
<div class="paragraph"></div>
<div class="ulist">
<ul>
 	<li><code>android:layout_width</code> – Defines the width of the widget.</li>
 	<li><code>android:layout_height</code> – Defines the height of the widget.</li>
</ul>
</div>
<div class="paragraph">

Views can define their size. This can be done in units of measurement or via pre-defined layout values. For example, as <code>100dp</code>.

</div>
<div class="paragraph">

The <code>match_parent</code> value tells the application to maximize the widget in its parent. The <code>wrap_content</code> value tells the layout to allocate the minimum amount so that the widget is rendered correctly.

</div>
</div>
