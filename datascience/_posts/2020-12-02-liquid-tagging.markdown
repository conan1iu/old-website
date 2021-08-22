---
layout: post
title:  "Separating posts by category with Liquid"
date:   2020-12-02 00:28:16 +1100
categories: ds
---

<h1><b>Separating and organinising blog posts by their categories</b></h1>

Using liquid it is possible to directly loop all posts for a certain category or tag:

{% highlight liquid %}
{% raw %}
 {% for post in site.categories['category'] limit:n %}
    <a href="{{ post.url }}">{{ post.title }}</a>
  {% endfor %}
{% endraw %}
{% endhighlight %}

Where `n` is the (maximum) number of posts that show. It's the same code for tags; just replace `site.categories['news']` with `site.tags['news']`.
