---
layout: page
title: Welcome
---
{% include JB/setup %}

You've stumbled on the Internet home of Kevin Iverson.  

## Blog

A collection of posts mostly so I don't forget stuff, but might be useful for others.

<ul class="posts">
  {% for post in site.posts %}
    <li><span>{{ post.date | date_to_string }}</span> &raquo; <a href="{{ BASE_PATH }}{{ post.url }}">{{ post.title }}</a></li>
  {% endfor %}
</ul>

