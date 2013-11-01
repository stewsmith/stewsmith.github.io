---
layout: post
title:  "Mostly Unsolvable"
date:   2013-11-01 13:00:00
categories: jekyll update
---

Most problems are unsolvable.

In order to think about why this is true, we need to think about how programs and decision problems differ.

First, what are programs?  Once compiled, programs are actually just binary strings.  A binary string can
be interpreted as a natural number.  Therefore, every program can be represented as an integer.

Let's compare this to a decision problem.  A decision problem takes an input, runs an algorithm, and gives a yes
or no as an output.  It can take any number as an input and output yes (1) or no (0).  We can put it in a table
to see what that looks like when we do it for every number.

0 => 0  
1 => 0  
2 => 1  
3 => 1  
4 => 0  
... => ...  

Therefore, decision problems are represented by an infinite bit string, and programs are represented by a finite
bit string.  We can compare this to the real numbers and the natural numbers, respectively.  Real numbers are
[uncountable](http://en.wikipedia.org/wiki/Uncountable_set) and natural numbers are
[countable](http://en.wikipedia.org/wiki/Countable_set).  In other words, there are many, many more decision problems
than there are programs to solve them.

I learned this from watching the [Computational Complexity lecture by Erik Demaine](http://www.youtube.com/watch?v=moPtwq_cVH8).
It's an awesome lecture and covers P and NP too.
