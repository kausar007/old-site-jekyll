---
layout: post
title:  "Cannot run Jekyll build as non-root user"
date:   2016-07-06 02:05:00 +0100
comments: true
categories: jekyll
---
You have run Jekyll as root user and now cannot run as any other user and get this error message:
{% highlight Plain Text %}
[kausar@centos ~]$ jekyll build
Configuration file: _config.yml
            Source: <omitted>
       Destination: <omitted>
 Incremental build: disabled. Enable with --incremental
      Generating...
jekyll 3.1.6 | Error:  Permission denied - /root
{% endhighlight %}
Running the following commands as **root** user will fix it.
{% highlight shell %}
# Make sure destination dir is owned by your user.
chown -R <user>:<group> <destination_dir>
# Remove jekyll metadata file.
jekyll clean
{% endhighlight %}
