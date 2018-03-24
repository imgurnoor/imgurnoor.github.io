---
layout: post
title: Classes and Objects in JAVA
date: 2017-08-11 15:07
author: gurnoor
comments: true
categories: [Uncategorized]
---
<b>Class</b> − A class can be defined as a template/blueprint that describes the behavior/state that the object of its type supports.

A class is defined by the <em>class</em> keyword and must start with a capital letter. The body of a class is surrounded by {}.

<img class="alignnone size-full wp-image-107" src="https://androidailyblog.files.wordpress.com/2016/12/class.png?w=616" sizes="(max-width: 432px) 100vw, 432px" srcset="https://androidailyblog.files.wordpress.com/2016/12/class.png 432w, https://androidailyblog.files.wordpress.com/2016/12/class.png?w=150 150w, https://androidailyblog.files.wordpress.com/2016/12/class.png?w=300 300w" alt="class" data-attachment-id="107" data-permalink="https://androidailyblog.wordpress.com/2016/06/21/objects-and-classes/class/" data-orig-file="https://androidailyblog.files.wordpress.com/2016/12/class.png?w=616" data-orig-size="432,127" data-comments-opened="1" data-image-meta="{&quot;aperture&quot;:&quot;0&quot;,&quot;credit&quot;:&quot;&quot;,&quot;camera&quot;:&quot;&quot;,&quot;caption&quot;:&quot;&quot;,&quot;created_timestamp&quot;:&quot;0&quot;,&quot;copyright&quot;:&quot;&quot;,&quot;focal_length&quot;:&quot;0&quot;,&quot;iso&quot;:&quot;0&quot;,&quot;shutter_speed&quot;:&quot;0&quot;,&quot;title&quot;:&quot;&quot;,&quot;orientation&quot;:&quot;0&quot;}" data-image-title="class" data-image-description="" data-medium-file="https://androidailyblog.files.wordpress.com/2016/12/class.png?w=616?w=300" data-large-file="https://androidailyblog.files.wordpress.com/2016/12/class.png?w=616?w=432" />
<div class="paragraph">

The data associated with a class is stored in variables; the behavior associated with a class or object is implemented with <em>methods</em>.

</div>
<div class="paragraph">

A class is contained in a text file with the same name as the class plus the extension<code>.java</code>. It is also possible to define inner classes, these are classes defined within another class, in this case, we do not need a separate file for this class.

<b>Object</b> − Objects have states and behaviors. Example: A dog has states – color, name, breed as well as behavior such as wagging their tail, barking, eating. An object is an instance of a class.

</div>
The object is the real element which has data and can perform actions. Each object is created based on the class definition. The class can be seen as the blueprint of an object, i.e., it describes how an object is created.
<div class="separator">A class can contain any of the following variable types:</div>
<ul class="list">
 	<li>
<div><b>Local variables: </b>Variables defined inside methods, constructors or blocks are called local variables. The variable will be declared and initialized within the method and the variable will be destroyed when the method has completed.</div></li>
 	<li>
<div><b>Instance variables: </b>Instance variables are variables within a class but outside any method. These variables are initialized when the class is instantiated. Instance variables can be accessed from inside any method, constructor or blocks of that particular class.</div></li>
 	<li>
<div><b>Class variables: </b>Class variables are variables declared with in a class, outside any method, with the static keyword</div></li>
</ul>
