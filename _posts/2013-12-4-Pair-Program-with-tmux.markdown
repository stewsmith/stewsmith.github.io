---
layout: post
title:  "Pair Program with tmux"
comments: true
date:   2013-12-04 09:30:02
categories: jekyll update
---

Pair programming should not involve two people hunched
over one screen.  Using ssh and tmux, both people can
share the same screen on seperate computers and see
live updates.


Ed and Ian want to pair program.
<ol>
<li>  Ed ssh's into a machine
<li>  Ed creates a user for Ian
    {% highlight ruby %}
        ed@machine:~$ adduser ian
    {% endhighlight %}
<li> Ed starts a tmux session
    {% highlight ruby %}
        ed@machine:~$ tmux
    {% endhighlight %}
<li> Ian ssh's into the machine
<li> Ian changes users to become Ed
    {% highlight ruby %}
        ian@machine:~$ su ed
    {% endhighlight %}
<li> Ian attaches to ed's tmux session
    (note Ian's prompt will display 'ed')
    {% highlight ruby %}
        ed@machine:~$ tmux attach
    {% endhighlight %}
<ol>


Now Ian and Ed share a screen and can see what the other
is typing and make changes. Try it!

Thanks to [Ed Zane](https://twitter.com/eddiezane) for
showing me this.
