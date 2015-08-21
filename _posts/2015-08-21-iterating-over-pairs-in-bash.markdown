---
layout: post
title:  "Iterating Over Pairs in the Shell"
date:   2015-08-21 16:00:30
categories: shell scripting
---

[Parameter substitution][parameter substitution] is used for manipulating and expanding variables.
One possible application for this is to simulate data tuples.
The code below demonstrates how to simulate tuples by splitting values into pairs.
The `${parameter#match}` directive evaluates to the value of $parameter with any matching prefix removed, while `${parameter%match}` allows us to remove matching suffixes.
When used together, these directives allow us to split each value using colon as a separator.

{% highlight bash %}
for config in 3.20GHz:3 2.90GHz:2 3.20GHz:0; do
  FREQ=${config%:*}
  CORES=${config#*:}
  # Do something with freq and core counts
done
{% endhighlight %}

[parameter substitution]: http://www.tldp.org/LDP/abs/html/parameter-substitution.html
