---
layout: default
title: Categories
---

# Categories

<div class="categories">
    <ul>
        {% for category in site.tags %}
        <a href="/category/{{category.basename}}"><li>{{category.basename}}</li></a>
        {% endfor %}
    </ul>
</div>
