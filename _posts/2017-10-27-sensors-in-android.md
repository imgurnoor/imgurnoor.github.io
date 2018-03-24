---
layout: post
title: Sensors in Android
date: 2017-10-27 17:26
author: gurnoor
comments: true
categories: [Daily Diary]
---
Most of the android devices have built-in sensors that measure motion, orientation, and various environmental condition. The android platform supports three broad categories of sensors.
<ul class="list">
 	<li>Motion Sensors</li>
 	<li>Environmental sensors</li>
 	<li>Position sensors,                  etc.</li>
</ul>
Some of the sensors are hardware based and some are software based sensors. Whatever the sensor is, android allows us to get the raw data from these sensors and use it in our application. For this android provides us with some classes.

Android provides SensorManager and Sensor classes to use the sensors in our application. In order to use sensors, first thing you need to do is to instantiate the object of SensorManager class. It can be achieved as follows.
<pre class="result notranslate">SensorManager sMgr;
sMgr = (SensorManager)this.getSystemService(SENSOR_SERVICE);
</pre>
The next thing you need to do is to instantiate the object of Sensor class by calling the getDefaultSensor() method of the SensorManager class. Its syntax is given below −
<pre class="result notranslate">Sensor light;
light = sMgr.getDefaultSensor(Sensor.TYPE_LIGHT);
</pre>
Once that sensor is declared , you need to register its listener and override two methods which are onAccuracyChanged and onSensorChanged. Its syntax is as follows −
<pre class="result notranslate">sMgr.registerListener(this, light,SensorManager.SENSOR_DELAY_NORMAL);
public void onAccuracyChanged(Sensor sensor, int accuracy) {
}

public void onSensorChanged(SensorEvent event) {
}</pre>
