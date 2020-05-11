---
layout: white_paper
title: White Papers
categories: white_paper
permalink: /white_paper
color: blue
updated: today
---

<ul>
{% for post in site.posts %}
    {% if post.categories contains "white_paper" %}
        <h1><a href="{{ post.url }}">{{ post.title }}</a></h1>
        {{post.excerpt}}
    {% endif %}
{% endfor %}
</ul>
