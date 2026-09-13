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

LINK 1: [A Life in Books](https://www.reddit.com/r/dataisbeautiful/comments/1jobwwu/a_life_in_books/)

LINK 2: [Visualizing the lifetimes and reigns of a](https://www.reddit.com/r/dataisbeautiful/comments/1iw1qceoc_visualizing_the_lietimes_and_reigns_of_a/)

LINK 3: [Proportion of Unicode characters originating in](https://www.reddit.com/r/dataisbeautiful/comments/1ky9bs3/proportion_of_unicode_characters_originating_in/)

LINK 4: [How public and jury votes affect the](https://www.reddit.com/r/dataisbeautiful/comments/1ksnbph/oc_how_public_and_jury_votes_affect_the/)

LINK 5: [American confidence in national institutions](https://www.reddit.com/r/dataisbeautiful/comments/1ky3tfs/oc_american_confindece_in_national_institutions/)