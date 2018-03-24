---
layout: post
title: Proximity Sensor in Android
date: 2017-10-31 17:27
author: gurnoor
comments: true
categories: [Daily Diary]
---
The proximity sensor is common on most smartphones, the ones that have a touchscreen. This is because the primary function of a proximity sensor is to disable accidental touch events. The most common scenario being- The ear coming in contact with the screen and generating touch events, while on a call.
<pre class="default prettyprint prettyprinted"><code><span class="kwd">public</span> <span class="kwd">class</span> <span class="typ">MainActivity</span> <span class="kwd">extends</span> <span class="typ">AppCompatActivity</span> <span class="kwd">implements</span> <span class="typ">SensorEventListener</span> <span class="pun">{</span>

    <span class="kwd">private</span> <span class="typ">SensorManager</span><span class="pln"> mSensorManager</span><span class="pun">;</span>
    <span class="kwd">private</span> <span class="typ">Sensor</span><span class="pln"> mProximity</span><span class="pun">;</span>

    <span class="lit">@Override</span>
    <span class="kwd">protected</span> <span class="kwd">void</span><span class="pln"> onCreate</span><span class="pun">(</span><span class="typ">Bundle</span><span class="pln"> savedInstanceState</span><span class="pun">)</span> <span class="pun">{</span>
        <span class="kwd">super</span><span class="pun">.</span><span class="pln">onCreate</span><span class="pun">(</span><span class="pln">savedInstanceState</span><span class="pun">);</span><span class="pln">
        setContentView</span><span class="pun">(</span><span class="pln">R</span><span class="pun">.</span><span class="pln">layout</span><span class="pun">.</span><span class="pln">activity_main</span><span class="pun">);</span><span class="pln">


        mSensorManager </span><span class="pun">=</span> <span class="pun">(</span><span class="typ">SensorManager</span><span class="pun">)</span><span class="pln"> getSystemService</span><span class="pun">(</span><span class="typ">Context</span><span class="pun">.</span><span class="pln">SENSOR_SERVICE</span><span class="pun">);</span><span class="pln">
        mProximity </span><span class="pun">=</span><span class="pln"> mSensorManager</span><span class="pun">.</span><span class="pln">getDefaultSensor</span><span class="pun">(</span><span class="typ">Sensor</span><span class="pun">.</span><span class="pln">TYPE_PROXIMITY</span><span class="pun">);</span>

    <span class="pun">}</span>

    <span class="lit">@Override</span>
    <span class="kwd">protected</span> <span class="kwd">void</span><span class="pln"> onResume</span><span class="pun">()</span> <span class="pun">{</span>
        <span class="kwd">super</span><span class="pun">.</span><span class="pln">onResume</span><span class="pun">();</span><span class="pln">
        mSensorManager</span><span class="pun">.</span><span class="pln">registerListener</span><span class="pun">(</span><span class="kwd">this</span><span class="pun">,</span><span class="pln"> mProximity</span><span class="pun">,</span> <span class="typ">SensorManager</span><span class="pun">.</span><span class="pln">SENSOR_DELAY_NORMAL</span><span class="pun">);</span>
    <span class="pun">}</span>

    <span class="lit">@Override</span>
    <span class="kwd">protected</span> <span class="kwd">void</span><span class="pln"> onPause</span><span class="pun">()</span> <span class="pun">{</span>
        <span class="kwd">super</span><span class="pun">.</span><span class="pln">onPause</span><span class="pun">();</span><span class="pln">
        mSensorManager</span><span class="pun">.</span><span class="pln">unregisterListener</span><span class="pun">(</span><span class="kwd">this</span><span class="pun">);</span>
    <span class="pun">}</span>

    <span class="lit">@Override</span>
    <span class="kwd">public</span> <span class="kwd">void</span><span class="pln"> onSensorChanged</span><span class="pun">(</span><span class="typ">SensorEvent</span> <span class="kwd">event</span><span class="pun">)</span> <span class="pun">{</span>
        <span class="kwd">if</span> <span class="pun">(</span><span class="kwd">event</span><span class="pun">.</span><span class="pln">sensor</span><span class="pun">.</span><span class="pln">getType</span><span class="pun">()</span> <span class="pun">==</span> <span class="typ">Sensor</span><span class="pun">.</span><span class="pln">TYPE_PROXIMITY</span><span class="pun">)</span> <span class="pun">{</span>
            <span class="kwd">if</span> <span class="pun">(</span><span class="kwd">event</span><span class="pun">.</span><span class="pln">values</span><span class="pun">[</span><span class="lit">0</span><span class="pun">]</span> <span class="pun">&gt;=</span> <span class="pun">-</span><span class="lit">0.01</span> <span class="pun">&amp;&amp;</span> <span class="kwd">event</span><span class="pun">.</span><span class="pln">values</span><span class="pun">[</span><span class="lit">0</span><span class="pun">]&lt;=</span> <span class="lit">0.01</span><span class="pun">)</span> <span class="pun">{</span>
                <span class="com">//near</span>
                <span class="typ">Toast</span><span class="pun">.</span><span class="pln">makeText</span><span class="pun">(</span><span class="pln">getApplicationContext</span><span class="pun">(),</span> <span class="str">"near"</span><span class="pun">,</span> <span class="typ">Toast</span><span class="pun">.</span><span class="pln">LENGTH_SHORT</span><span class="pun">).</span><span class="pln">show</span><span class="pun">();</span>
            <span class="pun">}</span> <span class="kwd">else</span> <span class="pun">{</span>
                <span class="com">//far</span>
                <span class="typ">Toast</span><span class="pun">.</span><span class="pln">makeText</span><span class="pun">(</span><span class="pln">getApplicationContext</span><span class="pun">(),</span> <span class="str">"far"</span><span class="pun">,</span> <span class="typ">Toast</span><span class="pun">.</span><span class="pln">LENGTH_SHORT</span><span class="pun">).</span><span class="pln">show</span><span class="pun">();</span>
            <span class="pun">}</span>
        <span class="pun">}</span>
    <span class="pun">}</span>

    <span class="lit">@Override</span>
    <span class="kwd">public</span> <span class="kwd">void</span><span class="pln"> onAccuracyChanged</span><span class="pun">(</span><span class="typ">Sensor</span><span class="pln"> sensor</span><span class="pun">,</span> <span class="kwd">int</span><span class="pln"> accuracy</span><span class="pun">)</span> <span class="pun">{</span>

    <span class="pun">}</span>

<span class="pun">}</span></code></pre>
