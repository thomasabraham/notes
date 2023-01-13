---
layout: post
title: Git cheat sheet
date: 2023-01-13
categories: cheat-sheets
---

## Hard reset - to completely discard last N commits
{% highlight shell %}
git reset --hard HEAD~N
{% endhighlight %}
For example, to discard last one commit, use
{% highlight shell %}
git reset --hard HEAD~1
{% endhighlight %}

## Soft reset - to undo last N commits, while still keeping the changes.
{% highlight shell %}
git reset --soft HEAD~N
{% endhighlight %}
For example, to discard last one commit, use
{% highlight shell %}
git reset --soft HEAD~1
{% endhighlight %}

