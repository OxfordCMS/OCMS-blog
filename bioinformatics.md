---
layout: page
title: Bioinformatics
categories: bioinformatics
permalink: /bioinformatics
description: Tutorials on bioinformatics tools and analyses for microbiome data
updated: today
---

<ul>
{% for post in site.posts %}
    {% if post.categories contains "bioinformatics" %}
        <h1><a href="{{ post.toclink }}">{{ post.title }}</a></h1>
        {{post.excerpt}}
    {% endif %}
{% endfor %}
</ul>
