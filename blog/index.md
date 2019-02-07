---
layout: default
title: Blog
---

# {{ page.title }}

<table class="no-table" style="width:100%">
{% for post in site.posts %} {% include listpost.html post=post %}
{% endfor %}
</table>

<a href="/category">View posts by category</a>
