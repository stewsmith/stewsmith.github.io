---
layout: post
title:  "JavaScript Pass-By-What?"
comments: true
date:   2014-01-24 11:07:02
categories: jekyll update
---

JavaScript is always pass-by-value even though it sometimes looks
like pass-by-reference.

Let's look at a couple of examples to understand JavaScript memory.
When copying primitive values from one variable to another, they
are stored separately in memory.

{% highlight javascript %}
var a = 10;
var b = a;

b = 5;
alert("a is " + a);     // "a is 10"

{% endhighlight %}

Objects, on the other hand, act differently. When you assign a variable
to the value of another object, they both point to the same memory
on the heap. Look at this code:

{% highlight javascript %}
var bob_dylan = new Object();
var robert_zimmerman = bob_dylan;

bob_dylan.age = 72
alert("Robert Zimmerman is " + robert_zimmerman.age);     // "Robert Zimmerman is 72"

{% endhighlight %}

Okay cool. But what happens when you pass primitives and objects to functions?
Again, they act differently. Primitives follow standard pass-by-value behavior.
Objects are a bit trickier.

{% highlight javascript %}
function set_nickname(obj) {
    obj.nickname = "Bobby";
}

var bob_dylan = new Object();
set_nickname(bob_dylan);
alert("Dylan's nickname is " + bob_dylan.nickname);      // "Dylan's nickname is Bobby"

{% endhighlight %}

This looks a whole lot like pass-by-reference! But if we modify set_nickname by two lines:

{% highlight javascript %}
function set_nickname(obj) {
    obj.nickname = "Bobby";
    obj = new Object();
    obj.nickname = "Charles";
}

var bob_dylan = new Object();
set_nickname(bob_dylan);
alert("Dylan's nickname is " + bob_dylan.nickname);      // "Dylan's nickname is Bobby"

{% endhighlight %}

We can see that Dylan's nickname is still "Bobby". When we reassigned obj in set_nickname,
it made a different object in memory, which did not persist beyond the function.
So even though it looks like pass-by-reference, Javascript always is pass-by-value.

I learned this from the excellent book [Professional Javascript for Web Developers](http://www.amazon.com/Professional-JavaScript-Developers-Nicholas-Zakas/dp/1118026691).
