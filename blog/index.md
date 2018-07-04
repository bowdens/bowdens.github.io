---
layout: default
title: Blog
---

<h1>{{ page.title }}</h1>
<ul class="posts">
    <hr>
    {% for post in site.posts %}
    <li> <a href="{{post.url}}" title="{{post.title}}">{{post.title}} ({{ post.date | date_to_string}})</a></li>
    <hr>
    {% endfor %}
</ul>
