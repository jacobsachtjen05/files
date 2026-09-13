---
layout: page
title: My DH Exploration
permalink: /my-dh-exploration/
---

Prep and presentation for my own Digital Humanities Exploration.

{% for post in site.posts %}
  {% if post.categories contains "my-dh-exploration" %}
- [{{ post.title }}]({{ post.url }}) — {{ post.date | date: "%B %d, %Y" }}
  {% endif %}
{% endfor %}
