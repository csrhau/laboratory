---
layout: post
title:  "Iterating Over Pairs in the Shell"
date:   2015-08-21 16:00:30
categories: shell scripting
---

[Parameter substitution][parameter substitution] is used for manipulating and expanding variables.
This allows us to simulate data tuples with composite values joined by a separator.
The code below iterates over a list and uses parameter substitution to 'unpack' each element into a pair of values:

{% highlight bash %}
for config in 3.20GHz:3 2.90GHz:2 3.20GHz:0; do
  FREQ=${config%:*}
  CORES=${config#*:}
  # Do something with freq and core counts
done
{% endhighlight %}

This works because the `${parameter#match}` directive evaluates to the value of $parameter with any matching prefix removed, while `${parameter%match}` allows us to remove matching suffixes.

[parameter substitution]: http://www.tldp.org/LDP/abs/html/parameter-substitution.html
