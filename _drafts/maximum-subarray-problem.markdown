---
layout: post
title:  "Maximum Subarray Problem"
date:   2015-09-11 16:25:30
categories: shell scripting
---

The [maximum subarray problem][msp] is the task of identifying a sub-array of a 1-dimensional array with the largest sum.

{% highlight haskell %}
-- Slice returns a sub-array of length l, starting at index s
slice :: (Num a) => [a] -> Int -> Int -> [a]
slice arr s l = take l (drop s arr)

-- MSP Generates all sub-slices, sums their values and returnsn a tuple (sum, start index, length) 
msp :: (Num a, Ord a) => [a] -> (a, Int, Int)
msp arr = maximum [(sum (slice arr s l), s, l) | s <- [0..(length arr)], l <- [1..length arr - s]]
{% endhighlight %}


[msp]: https://en.wikipedia.org/wiki/Maximum_subarray_problem
