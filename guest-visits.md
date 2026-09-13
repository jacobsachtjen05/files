---
layout: page
title: Guest Expert Visits
permalink: /guest-visits/
---

Notes and reflections from guest speakers who visit the class.

{% for post in site.posts %}
  {% if post.categories contains "guest-visit" %}
- [{{ post.title }}]({{ post.url }}) — {{ post.date | date: "%B %d, %Y" }}
  {% endif %}
{% endfor %}
