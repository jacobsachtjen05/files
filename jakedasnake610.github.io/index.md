---
layout: home
title: Home
---

# Welcome to my course blog

Hi, I'm Jake — this is where I'll be posting weekly reflections, homework, and updates on my Digital Humanities exploration and final project for [Course Name].

## Explore
- [Homework](/homework/)
- [Guest Expert Visits](/guest-visits/)
- [My DH Exploration](/my-dh-exploration/)
- [Peers' DH Explorations](/peer-dh-explorations/)
- [Final Project](/final-project/)

## Latest posts
{% for post in site.posts limit:5 %}
- [{{ post.title }}]({{ post.url }}) — {{ post.date | date: "%B %d, %Y" }}
{% endfor %}
