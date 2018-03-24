---
layout: post
title: Creating a Splash Screen on Android
date: 2017-10-15 14:35
author: gurnoor
comments: true
categories: [Uncategorized]
---
<h3>So, what’s the difference between the bad Splash Screen and the good Splash Screen ?</h3>
The difference is just the way you implement if. Previously, developers implemented the Splash Screen by displaying their brand logo on the screen during a certain time. The right way to implement a Launch Screen is now just to display your brand logo the time the application starts and not more then that.

To create a correct Splash Screen, you need to create a background that will display your brand logo to the screen. For this, you must create an XML file in the res/drawable folder
<pre>&lt;?xml version="1.0" encoding="utf-8"?&gt;
&lt;layer-list xmlns:android="http://schemas.android.com/apk/res/android"&gt;

&lt;item android:drawable="@color/colorPrimary" /&gt;

&lt;item&gt;
 &lt;bitmap android:src="@drawable/logo"
 android:gravity="center" /&gt;

&lt;/item&gt;

&lt;/layer-list&gt;</pre>
Next step is to create a dedicated theme for your Splash Activity. For this, you must inherit from the Theme.AppCompat.NoActionBar theme
<pre>&lt;resources&gt;

&lt;style name="AppTheme" parent="Theme.AppCompat.Light.DarkActionBar"&gt;
 &lt;item name="colorPrimary"&gt;@color/colorPrimary&lt;/item&gt;
 &lt;item name="colorPrimaryDark"&gt;@color/colorPrimaryDark&lt;/item&gt;
 &lt;item name="colorAccent"&gt;@color/colorAccent&lt;/item&gt;
 &lt;/style&gt;

&lt;style name="SplashTheme" parent="Theme.AppCompat.NoActionBar"&gt;
 &lt;item name="android:windowBackground"&gt;@drawable/background&lt;/item&gt;
 &lt;/style&gt;

&lt;/resources&gt;</pre>
<p id="c24d" class="graf graf--p graf-after--figure">Note that your Splash Theme has just to define the android:windowBackground item and set up the background created previously.</p>
<p id="e830" class="graf graf--p graf-after--p">Now, you can create your SplashActivity</p>

<pre>package com.gurnoor.splashscreen;

import android.content.Intent;
 import android.os.Bundle;
 import android.support.annotation.Nullable;
 import android.support.v7.app.AppCompatActivity;
 public class SplashActivity extends AppCompatActivity {

@Override
 protected void onCreate(@Nullable Bundle savedInstanceState) {
 super.onCreate(savedInstanceState);
 Intent intent = new Intent(this, MainActivity.class);
 startActivity(intent);
 finish();
 }
 }</pre>
Now you have to just launch the MainActivity of your Android Application and then finish the SplashActivity by calling the finish() method.

Don’t forget to define your SplashActivity in the Android Manifest and apply the SplashTheme on it :
<pre>&lt;?xml version="1.0" encoding="utf-8"?&gt;
&lt;manifest xmlns:android="http://schemas.android.com/apk/res/android"
 package="com.gurnoor.splashscreen"&gt;

&lt;application
 android:allowBackup="true"
 android:icon="@mipmap/ic_launcher"
 android:label="@string/app_name"
 android:supportsRtl="true"
 android:theme="@style/AppTheme"&gt;

&lt;activity android:name=".SplashActivity" android:theme="@style/SplashTheme"&gt;
 &lt;intent-filter&gt;
 &lt;action android:name="android.intent.action.MAIN" /&gt;
 &lt;category android:name="android.intent.category.LAUNCHER" /&gt;

&lt;/intent-filter&gt;

&lt;/activity&gt;

&lt;activity android:name=".MainActivity" /&gt;

&lt;/application&gt;

&lt;/manifest&gt;</pre>
