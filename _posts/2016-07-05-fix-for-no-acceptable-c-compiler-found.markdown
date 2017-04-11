---
layout: post
title:  "Fix for no acceptable C compiler found"
date:   2016-07-05 02:51:00 +0100
comments: true
categories: ruby centos error gem make
---
While installing a ruby gem (usually first one) or running `make install` command for any other installation, if an error is thrown like
{% highlight Plain Text %}
configure: error: in `/usr/lib/ruby/gems/1.8/gems/ffi-1.9.10/ext/ffi_c/libffi-x86_64-linux':
configure: error: no acceptable C compiler found in $PATH
See `config.log' for more details
make: *** ["/usr/lib/ruby/gems/1.8/gems/ffi-1.9.10/ext/ffi_c/libffi-x86_64-linux"/.libs/libffi_convenience.a] Error 1
{% endhighlight %}
This is because `gcc` is not installed on the machine. Installing `gcc` will fix this issue:
{% highlight shell %}
sudo yum install gcc
{% endhighlight %}
