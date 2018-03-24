---
layout: post
title: Services in Android
date: 2017-08-31 17:13
author: gurnoor
comments: true
categories: [Daily Diary]
---
<blockquote>A <b>service</b> is a component that runs in the background to perform long-running operations without needing to interact with the user and it works even if application is destroyed. A service can essentially take two states −</blockquote>
<table class="table table-bordered">
<tbody>
<tr>
<th>Sr.No.</th>
<th>State &amp; Description</th>
</tr>
<tr>
<td>1</td>
<td><b>Started</b>A service is <b>started</b> when an application component, such as an activity, starts it by calling <i>startService()</i>. Once started, a service can run in the background indefinitely, even if the component that started it is destroyed.</td>
</tr>
<tr>
<td>2</td>
<td><b>Bound</b>A service is <b>bound</b> when an application component binds to it by calling <i>bindService()</i>. A bound service offers a client-server interface that allows components to interact with the service, send requests, get results, and even do so across processes with interprocess communication (IPC).</td>
</tr>
</tbody>
</table>
A service has life cycle callback methods that you can implement to monitor changes in the service’s state and you can perform work at the appropriate stage. The following diagram on the left shows the life cycle when the service is created with startService() and the diagram on the right shows the life cycle when the service is created with bindService(): <i>(image courtesy : android.com )</i>

<img src="https://www.tutorialspoint.com/android/images/services.jpg" alt="Android Service lifecycle" />

To create an service, you create a Java class that extends the Service base class or one of its existing subclasses. The <b>Service</b> base class defines various callback methods and the most important are given below. You don’t need to implement all the callbacks methods. However, it’s important that you understand each one and implement those that ensure your app behaves the way users expect.
<table class="table table-bordered">
<tbody>
<tr>
<th>Sr.No.</th>
<th>Callback &amp; Description</th>
</tr>
<tr>
<td>1</td>
<td><b>onStartCommand()</b>The system calls this method when another component, such as an activity, requests that the service be started, by calling <i>startService()</i>. If you implement this method, it is your responsibility to stop the service when its work is done, by calling <i>stopSelf()</i> or <i>stopService()</i> methods.</td>
</tr>
<tr>
<td>2</td>
<td><b>onBind()</b>The system calls this method when another component wants to bind with the service by calling <i>bindService()</i>. If you implement this method, you must provide an interface that clients use to communicate with the service, by returning an <i>IBinder</i> object. You must always implement this method, but if you don’t want to allow binding, then you should return <i>null</i>.</td>
</tr>
<tr>
<td>3</td>
<td><b>onUnbind()</b>The system calls this method when all clients have disconnected from a particular interface published by the service.</td>
</tr>
<tr>
<td>4</td>
<td><b>onRebind()</b>The system calls this method when new clients have connected to the service, after it had previously been notified that all had disconnected in its <i>onUnbind(Intent)</i>.</td>
</tr>
<tr>
<td>5</td>
<td><b>onCreate()</b>The system calls this method when the service is first created using <i>onStartCommand()</i> or <i>onBind()</i>. This call is required to perform one-time set-up.</td>
</tr>
<tr>
<td>6</td>
<td><b>onDestroy()</b>The system calls this method when the service is no longer used and is being destroyed. Your service should implement this to clean up any resources such as threads, registered listeners, receivers, etc.</td>
</tr>
</tbody>
</table>
