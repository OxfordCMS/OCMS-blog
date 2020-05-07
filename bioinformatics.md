---
layout: bioinformatics
title: Bioinformatics Resources
categories: bioinformatics
permalink: /bioinformatics
---

# Tutorials


<ul>
{% for post in site.posts %}
{% if post.categories contains "bioinformatics" %}
    <h3><a href="{{ post.url }}">{{ post.title }}</a></h3>
    {{ post.content }}
{% endif %}
{% endfor %}
</ul>
