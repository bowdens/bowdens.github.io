---
layout: default
title: Categories
---

# Categories

<div class="all-categories">
<ul style="list">
{% for category in site.categories %}
{%assign name=category[0]%}
<li>
<details>
<summary><a href="/category/{{category[0]}}">{{category[0] | capitalize}}</a></summary>
<table class="no-table" style="width:90%">
    {% for post in site.categories[name] %}
        {% include listpost.html post=post %}
    {% endfor %}
</table>
<br>
</details>
</li>
{% endfor %}
</ul>
</div>
