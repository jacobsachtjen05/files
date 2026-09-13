---
layout: page
title: Final Project
permalink: /final-project/
---

Progress updates and work on the final project.

{% for post in site.posts %}
  {% if post.categories contains "final-project" %}

- [{{ post.title }}]({{ post.url }}) — {{ post.date | date: "%B %d, %Y" }}

  {% endif %}
{% endfor %}
