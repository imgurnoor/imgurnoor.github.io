---
layout: post
title: SMS API in Android
date: 2017-10-18 17:24
author: gurnoor
comments: true
categories: [Daily Diary]
---
In Android, you can use SmsManager API or devices Built-in SMS application to send SMS’s. In this tutorial, we shows you two basic examples to send SMS message −

<b>SmsManager API</b>
<pre class="result notranslate">SmsManager smsManager = SmsManager.getDefault();
smsManager.sendTextMessage("phoneNo", null, "sms message", null, null);
</pre>
<b>Built-in SMS application</b>
<pre class="result notranslate">Intent sendIntent = new Intent(Intent.ACTION_VIEW);
sendIntent.putExtra("sms_body", "default content"); 
sendIntent.setType("vnd.android-dir/mms-sms");
startActivity(sendIntent);
</pre>
Of course, both need <b>SEND_SMS permission</b>.
<pre class="result notranslate">&lt;uses-permission android:name="android.permission.SEND_SMS" /&gt;
</pre>
Apart from the above method, there are few other important functions available in SmsManager class. These methods are listed below −
<table class="table table-bordered">
<tbody>
<tr>
<th>Sr.No.</th>
<th>Method &amp; Description</th>
</tr>
<tr>
<td>1</td>
<td><b>ArrayList&lt;String&gt; divideMessage(String text)</b>This method divides a message text into several fragments, none bigger than the maximum SMS message size.</td>
</tr>
<tr>
<td>2</td>
<td><b>static SmsManager getDefault()</b>This method is used to get the default instance of the SmsManager</td>
</tr>
<tr>
<td>3</td>
<td><b>void sendDataMessage(String destinationAddress, String scAddress, short destinationPort, byte[] data, PendingIntent sentIntent, PendingIntent deliveryIntent)</b>This method is used to send a data based SMS to a specific application port.</td>
</tr>
<tr>
<td>4</td>
<td><b>void sendMultipartTextMessage(String destinationAddress, String scAddress, ArrayList&lt;String&gt; parts, ArrayList&lt;PendingIntent&gt; sentIntents, ArrayList&lt;PendingIntent&gt; deliveryIntents)</b>Send a multi-part text based SMS.</td>
</tr>
<tr>
<td>5</td>
<td><b>void sendTextMessage(String destinationAddress, String scAddress, String text, PendingIntent sentIntent, PendingIntent deliveryIntent)</b>Send a text based SMS.</td>
</tr>
</tbody>
</table>
<h2>Example</h2>
Following example shows you in practical how to use SmsManager object to send an SMS to the given mobile number.
<blockquote>To experiment with this example, you will need actual Mobile device equipped with latest Android OS, otherwise you will have to struggle with emulator which may not work.</blockquote>
<table class="table table-bordered">
<tbody>
<tr>
<th class="fivepct">Step</th>
<th>Description</th>
</tr>
<tr>
<td>1</td>
<td>You will use Android Studio IDE to create an Android application and name it as  under a package <i>com.example.sms</i>.</td>
</tr>
<tr>
<td>2</td>
<td>Modify <i>src/MainActivity.java</i> file and add required code to take care of sending sms.</td>
</tr>
<tr>
<td>3</td>
<td>Modify layout XML file <i>res/layout/activity_main.xml</i> add any GUI component if required. I’m adding a simple GUI to take mobile number and SMS text to be sent and a simple button to send SMS.</td>
</tr>
<tr>
<td>4</td>
<td>No need to define default string constants at res/values/strings.xml. Android studio takes care of default constants.</td>
</tr>
<tr>
<td>5</td>
<td>Modify <i>AndroidManifest.xml</i> to add permissions.</td>
</tr>
<tr>
<td>6</td>
<td>Run the application to launch Android emulator and verify the result of the changes done in the application.</td>
</tr>
</tbody>
</table>
