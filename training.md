---
layout: training
title: Training Resources
categories: training
permalink: /training
color: pink
updated: today
---

<ul>
{% for post in site.posts %}
    {% if post.categories contains "training" %}
        <h2><a href="{{ post.url }}">{{ post.title }}</a></h2>
        {{post.content}}
    {% endif %}
{% endfor %}
</ul>
