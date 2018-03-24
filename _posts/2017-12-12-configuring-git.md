---
layout: post
title: Configuring git
date: 2017-12-12 18:02
author: gurnoor
comments: true
categories: [Daily Diary]
---
<div id="initializing-repositories-and-configuring-git" class="section">
<h2>Initializing repositories and configuring git</h2>
There are several way to initiliaze a git repository. The first is used to initialize git in an existing repository. The second is used to retrieve an existing repository.

To initialize a new project, in the project directory, initialize the git repository with:
<div class="highlight-python">
<pre>git init</pre>
</div>
This will enable git to keep track of changes in this folder, and subfolders by creating a .git hidden folder containing the git skeleton.

The second way is:
<div class="highlight-python">
<pre>git clone https://github.com/Gurnoor30196/OpenStreetMap.git</pre>
</div>
This will clone the repository containing the documents of this tutorial.
<div class="admonition note">
<p class="first admonition-title">Note</p>
<p class="last">Each new repository should be in its own directory. One git repository should not be created or cloned in an existing git repository, ie a folder you’ve initialized a git repository and its subfolders.</p>

</div>
Before continuing let’s configure git. You will have to do this once per computer you use <tt class="docutils literal"><span class="pre">git</span> <span class="pre">config</span> <span class="pre">--global</span></tt>:
<div class="highlight-python">
<pre>git config --global user.name "Your Name Comes Here"
git config --global user.email you@yourdomain.com``
git config --global core.editor vim
git config color.ui auto</pre>
</div>
The <tt class="docutils literal"><span class="pre">--global</span></tt> option corresponds to a user-wide configuration. The configuration will be stored in a hidden repository in your home. You can also configure each git repository individually, by removing this option, or system-wide by replacing the <tt class="docutils literal"><span class="pre">--global</span></tt> option with <tt class="docutils literal"><span class="pre">--system</span></tt>. Usually, we just configure repositories user-wide.

You can check your configuration with:
<div class="highlight-python">
<pre>git config --list</pre>
</div>
If you’ve configured git several times at different levels, you will probably see several entries twice or three times in the configuration list. The user-wide configuration overrides the system-wide configuration, and the local configuration overrides the user-wide configuration.

</div>
