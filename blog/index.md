---
layout: default
title: Blog
---

# {{ page.title }}

{:.no-table}
{: style="width:90%"}
{% for post in site.posts %} |<span class="image-caption"> <a href="{{post.url}}">![{{post.title}}]({% if post.image %} {{post.image}} {% else %} /assets/img/defaultpost.png {% endif %})</a> {% if post.credit %} <br> {{post.credit}} </span> {% endif %} | [{{ post.title }}]({{ post.url }} ) | {{ post.date | date_to_string }} | 
{% endfor %}

