---
layout: post
title:  "Iterating Over Pairs in the Shell"
date:   2015-08-21 16:00:30
categories: shell scripting
---

[Parameter substitution][parameter substitution] is useful for manipulating and expanding variables.
One useful application of this is to simulate pair variables.
The `${parameter#match}` directive evaluates to the value of $parameter with any matching prefix removed.
Similarly, `${parameter%match}` allows us to remove matching suffixes.
The following code splits values into pairs using colon as a separator:

{% highlight bash %}
for config in 3.20GHz:3 2.90GHz:2 3.20GHz:0; do
  FREQ=${config%:*}
  CORES=${config#*:}
  # Do something with freq and core counts
done
{% endhighlight %}

[parameter substitution]: http://www.tldp.org/LDP/abs/html/parameter-substitution.html
