---
layout: page
title: Training Resources
categories: training
permalink: /training
description: Learn more on theories and technologies involved in microbiome research.
updated: today
---

<ul>
{% for post in site.posts %}
    {% if post.categories contains "training" %}
        <h2><a href="{{ post.toclink }}">{{ post.title }}</a></h2>
        {{post.content}}
    {% endif %}
{% endfor %}
</ul>
