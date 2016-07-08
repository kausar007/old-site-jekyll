---
layout: post
title:  "Fix for failed to build gem native extension"
date:   2016-07-05 02:16:00 +0100
comments: true
categories: ruby centos error gem
---
While installing a ruby gem (usually first one) if you get an error like
{% highlight Plain Text %}
[kausar@centos ~]$ sudo gem install jekyll
Building native extensions. This could take a while...
ERROR: Error installing jekyll:
       ERROR: Failed to build gem native extension.

/usr/bin/ruby extconf.rb
mkmf.rb can't find header files for ruby at /usr/lib/ruby/ruby.h
{% endhighlight %}
This is because ruby development package is not installed on your machine. Installing `ruby-devel` will fix this issue:
{% highlight shell %}
sudo yum install ruby-devel
{% endhighlight %}
I hope this works for you.
