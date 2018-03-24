---
layout: post
title: Getting started with Android Studio
date: 2017-08-14 15:14
author: gurnoor
comments: true
categories: [Uncategorized]
---
<h3 id="create-a-new-android-project">Create a new Android project</h3>
<div class="paragraph">

Press the <em>Start a new Android Studio project</em> link to get started. Alternatively you can select the <span class="menuseq"><span class="menu">File</span> ▸ <span class="menuitem">New Project…</span></span> entry from the menu, if you already created a project earlier.

</div>
<div class="imageblock">
<div class="content"><img src="https://i2.wp.com/www.vogella.com/tutorials/Android/img/xas_first10.png.pagespeed.ic.rm2kbxsoWF.webp" alt="Creating a new Android Studio project" /></div>
</div>
<div class="paragraph">

Use the following data of input for your project. Project location and package name are derived from your input. If you want another package name, press the small <em>Edit</em> hyperlink.

</div>
<img class="" src="http://cdn.teamandroid.com/wp-content/uploads/2017/05/Android-Studio-3.0-Preview-2.png" alt="Image result for android studio 3.0" width="540" height="410" />
<table class="tableblock frame-all grid-all spread" style="height: 414px;" width="642"><caption class="title">Table 2. Setting for your Android project

</caption><colgroup> <col /> <col /></colgroup>
<thead>
<tr>
<th class="tableblock halign-left valign-top">Property</th>
<th class="tableblock halign-left valign-top">Value</th>
</tr>
</thead>
<tbody>
<tr>
<td class="tableblock halign-left valign-top">
<p class="tableblock">Application name</p>
</td>
<td class="tableblock halign-left valign-top">
<p class="tableblock">Test App</p>
</td>
</tr>
<tr>
<td class="tableblock halign-left valign-top">
<p class="tableblock">Company Domain</p>
</td>
<td class="tableblock halign-left valign-top">
<p class="tableblock"><span class="skimlinks-unlinked">gurnoor.me.example.com</span></p>
</td>
</tr>
<tr>
<td class="tableblock halign-left valign-top">
<p class="tableblock">Package Name</p>
</td>
<td class="tableblock halign-left valign-top">
<p class="tableblock">me.gurnoor.myapplication</p>
</td>
</tr>
<tr>
<td class="tableblock halign-left valign-top">
<p class="tableblock">Project Location</p>
</td>
<td class="tableblock halign-left valign-top">C:\Users\Kunwar’s\AndroidStudioProjects\TestApp</td>
</tr>
<tr>
<td class="tableblock halign-left valign-top">
<p class="tableblock">C++ support</p>
</td>
<td class="tableblock halign-left valign-top">
<p class="tableblock">optional (I don’t need it )</p>
</td>
</tr>
</tbody>
</table>
&nbsp;

Press next and then select target device and select for what you want to develop .

Select Mobile and Tablets .

Minimun Sdk can also be selected.

<img class="alignnone size-full wp-image-430" src="https://androidailyblog.files.wordpress.com/2016/08/target.png?w=616" sizes="(max-width: 616px) 100vw, 616px" srcset="https://androidailyblog.files.wordpress.com/2016/08/target.png?w=616 616w, https://androidailyblog.files.wordpress.com/2016/08/target.png?w=150 150w, https://androidailyblog.files.wordpress.com/2016/08/target.png?w=300 300w, https://androidailyblog.files.wordpress.com/2016/08/target.png?w=768 768w, https://androidailyblog.files.wordpress.com/2016/08/target.png?w=1024 1024w, https://androidailyblog.files.wordpress.com/2016/08/target.png 1066w" alt="target" data-attachment-id="430" data-permalink="https://androidailyblog.wordpress.com/2016/08/08/getting-started-with-android-studio/target/" data-orig-file="https://androidailyblog.files.wordpress.com/2016/08/target.png?w=616" data-orig-size="1066,736" data-comments-opened="1" data-image-meta="{&quot;aperture&quot;:&quot;0&quot;,&quot;credit&quot;:&quot;&quot;,&quot;camera&quot;:&quot;&quot;,&quot;caption&quot;:&quot;&quot;,&quot;created_timestamp&quot;:&quot;0&quot;,&quot;copyright&quot;:&quot;&quot;,&quot;focal_length&quot;:&quot;0&quot;,&quot;iso&quot;:&quot;0&quot;,&quot;shutter_speed&quot;:&quot;0&quot;,&quot;title&quot;:&quot;&quot;,&quot;orientation&quot;:&quot;0&quot;}" data-image-title="target" data-image-description="" data-medium-file="https://androidailyblog.files.wordpress.com/2016/08/target.png?w=616?w=300" data-large-file="https://androidailyblog.files.wordpress.com/2016/08/target.png?w=616?w=616" />

Now select the type of activity . For beginners its preferable to choose empty activity.

<img class="alignnone size-full wp-image-431" src="https://androidailyblog.files.wordpress.com/2016/08/activity-and.png?w=616" sizes="(max-width: 616px) 100vw, 616px" srcset="https://androidailyblog.files.wordpress.com/2016/08/activity-and.png?w=616 616w, https://androidailyblog.files.wordpress.com/2016/08/activity-and.png?w=150 150w, https://androidailyblog.files.wordpress.com/2016/08/activity-and.png?w=300 300w, https://androidailyblog.files.wordpress.com/2016/08/activity-and.png?w=768 768w, https://androidailyblog.files.wordpress.com/2016/08/activity-and.png?w=1024 1024w, https://androidailyblog.files.wordpress.com/2016/08/activity-and.png 1061w" alt="activity-and" data-attachment-id="431" data-permalink="https://androidailyblog.wordpress.com/2016/08/08/getting-started-with-android-studio/activity-and/" data-orig-file="https://androidailyblog.files.wordpress.com/2016/08/activity-and.png?w=616" data-orig-size="1061,735" data-comments-opened="1" data-image-meta="{&quot;aperture&quot;:&quot;0&quot;,&quot;credit&quot;:&quot;&quot;,&quot;camera&quot;:&quot;&quot;,&quot;caption&quot;:&quot;&quot;,&quot;created_timestamp&quot;:&quot;0&quot;,&quot;copyright&quot;:&quot;&quot;,&quot;focal_length&quot;:&quot;0&quot;,&quot;iso&quot;:&quot;0&quot;,&quot;shutter_speed&quot;:&quot;0&quot;,&quot;title&quot;:&quot;&quot;,&quot;orientation&quot;:&quot;0&quot;}" data-image-title="activity-and" data-image-description="" data-medium-file="https://androidailyblog.files.wordpress.com/2016/08/activity-and.png?w=616?w=300" data-large-file="https://androidailyblog.files.wordpress.com/2016/08/activity-and.png?w=616?w=616" />

Now click next.

Then fill the details accordingdly.

<img class="alignnone size-full wp-image-432" src="https://androidailyblog.files.wordpress.com/2016/08/activity-cust.png?w=616" sizes="(max-width: 616px) 100vw, 616px" srcset="https://androidailyblog.files.wordpress.com/2016/08/activity-cust.png?w=616 616w, https://androidailyblog.files.wordpress.com/2016/08/activity-cust.png?w=150 150w, https://androidailyblog.files.wordpress.com/2016/08/activity-cust.png?w=300 300w, https://androidailyblog.files.wordpress.com/2016/08/activity-cust.png?w=768 768w, https://androidailyblog.files.wordpress.com/2016/08/activity-cust.png?w=1024 1024w, https://androidailyblog.files.wordpress.com/2016/08/activity-cust.png 1068w" alt="activity-cust" data-attachment-id="432" data-permalink="https://androidailyblog.wordpress.com/2016/08/08/getting-started-with-android-studio/activity-cust/" data-orig-file="https://androidailyblog.files.wordpress.com/2016/08/activity-cust.png?w=616" data-orig-size="1068,743" data-comments-opened="1" data-image-meta="{&quot;aperture&quot;:&quot;0&quot;,&quot;credit&quot;:&quot;&quot;,&quot;camera&quot;:&quot;&quot;,&quot;caption&quot;:&quot;&quot;,&quot;created_timestamp&quot;:&quot;0&quot;,&quot;copyright&quot;:&quot;&quot;,&quot;focal_length&quot;:&quot;0&quot;,&quot;iso&quot;:&quot;0&quot;,&quot;shutter_speed&quot;:&quot;0&quot;,&quot;title&quot;:&quot;&quot;,&quot;orientation&quot;:&quot;0&quot;}" data-image-title="activity-cust" data-image-description="" data-medium-file="https://androidailyblog.files.wordpress.com/2016/08/activity-cust.png?w=616?w=300" data-large-file="https://androidailyblog.files.wordpress.com/2016/08/activity-cust.png?w=616?w=616" />

Now press Finish Button and this Prograss Dialog will Appear.

<img class="alignnone size-full wp-image-433" src="https://androidailyblog.files.wordpress.com/2016/08/build-app.png?w=616" sizes="(max-width: 577px) 100vw, 577px" srcset="https://androidailyblog.files.wordpress.com/2016/08/build-app.png 577w, https://androidailyblog.files.wordpress.com/2016/08/build-app.png?w=150 150w, https://androidailyblog.files.wordpress.com/2016/08/build-app.png?w=300 300w" alt="build-app" data-attachment-id="433" data-permalink="https://androidailyblog.wordpress.com/2016/08/08/getting-started-with-android-studio/build-app/" data-orig-file="https://androidailyblog.files.wordpress.com/2016/08/build-app.png?w=616" data-orig-size="577,142" data-comments-opened="1" data-image-meta="{&quot;aperture&quot;:&quot;0&quot;,&quot;credit&quot;:&quot;&quot;,&quot;camera&quot;:&quot;&quot;,&quot;caption&quot;:&quot;&quot;,&quot;created_timestamp&quot;:&quot;0&quot;,&quot;copyright&quot;:&quot;&quot;,&quot;focal_length&quot;:&quot;0&quot;,&quot;iso&quot;:&quot;0&quot;,&quot;shutter_speed&quot;:&quot;0&quot;,&quot;title&quot;:&quot;&quot;,&quot;orientation&quot;:&quot;0&quot;}" data-image-title="build-app" data-image-description="" data-medium-file="https://androidailyblog.files.wordpress.com/2016/08/build-app.png?w=616?w=300" data-large-file="https://androidailyblog.files.wordpress.com/2016/08/build-app.png?w=616?w=577" />

Now Gradle will configure Programs for us and will Create our project.
