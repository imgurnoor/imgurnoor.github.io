---
layout: post
title: Location Services in Android
date: 2017-11-25 17:45
author: gurnoor
comments: true
categories: [Daily Diary]
---
Android gives your applications access to the location services supported by the device through classes in the package<code>android.location</code>.the system The central component of the location farther. system<code>LocationManager</code> service, which provides APIs to determine location and bearing of the underlying device (if available).

As with other system services, you do not instantiate a <code>LocationManager</code> directly. Rather, you request an instance from the system by calling<code>getSystemService(Context.LOCATION_SERVICE)</code>. The method returns a handle to a new instance<code>LocationManager</code>

Once your application has a,<code>LocationManager</code> your application is able to do three things:
<ul>
 	<li>Query for the list of all <code>LocationProvider</code>s for the last known user location.</li>
 	<li>Register/unregister for periodic updates of the user’s current location from a location provider (specified either by criteria or name).</li>
 	<li>Register/unregister for a given to<code>Intent</code> be fired if the device comes within a given proximity (specified by a radius in meters) of a given lat/long.</li>
</ul>
