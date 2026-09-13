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

Links for homework 1:

LINK 1: https://www.reddit.com/r/dataisbeautiful/comments/1jobwwu/a_life_in_books/

LINK 2: https://www.reddit.com/r/dataisbeautiful/comments/1iw1qce/oc_visualizing_the_lifetimes_and_reigns_of_a/

LINK 3: https://www.reddit.com/r/dataisbeautiful/comments/1ky9bs3/proportion_of_unicode_characters_originating_in/

LINK 4: https://www.reddit.com/r/dataisbeautiful/comments/1ksnbph/oc_how_public_and_jury_votes_affect_the/

LINK 5: https://www.reddit.com/r/dataisbeautiful/comments/1ky3tfs/oc_american_confindece_in_national_institutions/