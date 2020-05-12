---
layout: bioinformatics
title: Bioinformatics
categories: bioinformatics
permalink: /bioinformatics
color: turquoise
updated: today
---

<ul>
{% for post in site.posts %}
    {% if post.categories contains "bioinformatics" %}
        <h1><a href="{{ post.url }}">{{ post.title }}</a></h1>
        {{post.excerpt}}
    {% endif %}
{% endfor %}
</ul>
