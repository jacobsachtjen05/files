---
layout: page
title: Homework
permalink: /homework/
---

Write-ups for each homework assignment in the course.

{% for post in site.posts %}
  {% if post.categories contains "homework" %}
- [{{ post.title }}]({{ post.url }}) — {{ post.date | date: "%B %d, %Y" }}
  {% endif %}
{% endfor %}
