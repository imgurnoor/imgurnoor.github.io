---
layout: post
title: Whatsapp, Facebook and many other realtime messaging started with ejabberd
date: 2017-12-01 15:05
author: gurnoor
comments: true
categories: [Daily Diary]
---
<b>ejabberd</b> is an XMPP application server. ejabberd stands for <b>E</b>rlang <b>Jabber</b> <b>D</b>aemon (Jabber being a former name for XMPP) and is written in lowercase only.

ejabberd has a high level of compliance with XMPP.<sup id="cite_ref-14" class="reference"></sup> It provides a web interface which can be translated into other languages. ejabberd supports distributed computing by clustering, supports live upgrades,  shared roster groups and provides support for virtual hosts. Database management systems supported include PostgreSQL and MySQL, and ODBC is supported for connectivity to other systems. LDAP authentication is supported, as is login via SSL/TLS, SASL and STARTTLS.

ejabberd is extensible via <b>modules</b>, which can provide support for additional capabilities such as saving offline messages or a user database.
<h4>To download ejabberd server on your server type</h4>
<pre>apt-get -y install ejabberd</pre>
<h4>Next step is to add admin user</h4>
<pre>ejabberdctl register admin localhost password</pre>
Now give <strong>Admin</strong> Privileges

By default, hostname used by eJabberd is 'localhost', which can be modified from config file.

For our example we will call our admin user "<b>admin@localhost</b>" and modify the following lines in <b>/etc/ejabberd/ejabberd.cfg</b>:
<pre>%% Admin user
{acl, admin, {user, "admin", "localhost"}}.

%% Hostname
{hosts, ["localhost"]}.
</pre>
Now restart Ejabberd server
<pre>service ejabberd restart</pre>
Now you can navigate to your eJabberd Web Admin interface on droplet's IP address port <b>5280</b>
<pre>http://domainname:5280/admin</pre>
