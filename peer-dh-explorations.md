---
layout: page
title: Peers' DH Explorations
permalink: /peer-dh-explorations/
---

Notes and takeaways from classmates' Digital Humanities Explorations.

{% for post in site.posts %}
  {% if post.categories contains "peer-dh-exploration" %}
- [{{ post.title }}]({{ post.url }}) — {{ post.date | date: "%B %d, %Y" }}
  {% endif %}
{% endfor %}
