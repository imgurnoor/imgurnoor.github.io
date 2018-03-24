---
layout: post
title: Accelerometer in smart devices
date: 2017-11-02 17:29
author: gurnoor
comments: true
categories: [Daily Diary]
---
Most Android-powered devices have an accelerometer.Motion sensors are useful for monitoring device movement, such as tilt, shake, rotation, or swing. The movement is usually a reflection of direct user input (for example, a user steering a car in a game or a user controlling a ball in a game), but it can also be a reflection of the physical environment in which the device is sitting (for example, moving with you while you drive your car). In the first case, you are monitoring motion relative to the device’s frame of reference or your application’s frame of reference; in the second case you are monitoring motion relative to the world’s frame of reference. Motion sensors by themselves are not typically used to monitor device position, but they can be used with other sensors, such as the geomagnetic field sensor, to determine a device’s position relative to the world’s frame of reference (see Position Sensorsfor more information).

All of the motion sensors return multi-dimensional arrays of sensor values for each <code>SensorEvent</code>. For example, during a single sensor event the accelerometer returns acceleration force data for the three coordinate axes, and the gyroscope returns rate of rotation data for the three coordinate axes. These data values are returned in a <code>float</code> array (<code>values</code>) along with other <code>SensorEvent</code> parameters.
<h3 id="sensors-motion-accel">Using the Accelerometer</h3>
An acceleration sensor measures the acceleration applied to the device, including the force of gravity. The following code shows you how to get an instance of the default acceleration sensor:
<pre class="prettyprint"><span class="kwd">private</span> <span class="typ">SensorManager</span><span class="pln"> mSensorManager</span><span class="pun">;</span>
<span class="kwd">private</span> <span class="typ">Sensor</span><span class="pln"> mSensor</span><span class="pun">;</span><span class="pln">
  </span><span class="pun">...</span><span class="pln">
mSensorManager </span><span class="pun">=</span> <span class="pun">(</span><span class="typ">SensorManager</span><span class="pun">)</span><span class="pln"> getSystemService</span><span class="pun">(</span><span class="typ">Context</span><span class="pun">.</span><span class="pln">SENSOR_SERVICE</span><span class="pun">);</span><span class="pln">
mSensor </span><span class="pun">=</span><span class="pln"> mSensorManager</span><span class="pun">.</span><span class="pln">getDefaultSensor</span><span class="pun">(</span><span class="typ">Sensor</span><span class="pun">.</span><span class="pln">TYPE_ACCELEROMETER</span><span class="pun">);</span></pre>
Conceptually, an acceleration sensor determines the acceleration that is applied to a device (A<sub>d</sub>) by measuring the forces that are applied to the sensor itself (F<sub>s</sub>) using the following relationship:
<pre class="no-pretty-print classic">A<sub>d</sub> = - ∑F<sub>s</sub> / mass
</pre>
However, the force of gravity is always influencing the measured acceleration according to the following relationship:
<pre class="no-pretty-print classic">A<sub>d</sub> = -g - ∑F / mass</pre>
&nbsp;

So, we can have following code
<pre>@Override
public void onSensorChanged(SensorEvent event) {
float[] values = event.values;

float x = values[0];
float y = values[1];
float z = values[2];

//txtShake.setText(x+" - "+y+" - "+z);

float cal = ((x*x)+(y*y)+(z*z))/(SensorManager.GRAVITY_EARTH * SensorManager.GRAVITY_EARTH);

if(cal&gt;3){
txtShake.setText("Device Shaken");
sensorManager.unregisterListener(this);

/* ACTION TO BE PERFORMED*/

}else{
txtShake.setText("Calculation is: "+cal);
}*/</pre>
