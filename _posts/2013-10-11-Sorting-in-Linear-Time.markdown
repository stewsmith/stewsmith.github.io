---
layout: post
title:  "Sorting in Linear Time"
date:   2013-10-11 11:26:00
categories: jekyll update
---

You may have read the title of this post and thought, "That is ridiculous.  The fastest a list can be sorted is O(nlogn)".  You are right.  Here is the proof:

Theorem:  Any decision tree sorting n elements has Ω(nlogn).<br>
-There are n! leaves on our decision tree.  That is, there are n! ways of arranging n items in a list.<br>
-A binary tree of height h has no more than 2^h leaves.

So ...<br>
n! <= leaves <= 2^h<br>
h >= lg(n!)<br>
= Ω(nlgn)

So far "Sorting in Linear Time" seems like a pretty terrible title for this post considering we just proved that the fastest we can sort is Ω(nlogn).
But O(nlgn) is the best we can do when we can only compare items among themselves.  If we know of a boundary or limit of our array of items, then we are not constrained by comparison sort.

When we know the boundaries of our input, we can apply that information and place each item in the list in its correct position as we encounter it.  Think about sorting a deck of cards.
We know the upper and lower bounds and can place each card in its correct position.

As an example, we can think of an array with a max element of 500 and a min element of 0.  We would make 501
'bins' and put each element into the index corresponding to its value.  We may not have 501 elements, so some
the bins would be blank, but this is a cost of sorting in linear time.

To learn more about sorting in linear time, check out [Counting Sort](http://en.wikipedia.org/wiki/Counting_sort),
[Bucket Sort](http://en.wikipedia.org/wiki/Bucket_sort) and [Radix Sort](http://en.wikipedia.org/wiki/Radix_sort).

