---
layout: page
title: White Papers
categories: white_paper
permalink: /white_paper
description: Perspectives and findings from internal research conducted at the OCMS.
updated: today
---

<ul>
{% for post in site.posts %}
    {% if post.categories contains "white_paper" %}
        <h1><a href="{{ post.toclink }}">{{ post.title }}</a></h1>
        {{post.excerpt}}
    {% endif %}
{% endfor %}
</ul>
