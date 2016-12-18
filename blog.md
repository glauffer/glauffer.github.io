---
layout: page
title: Blog
subtitle: This came up as a form to write some stuff I would like to remeber, so why not share online?
---

{% capture written_year %}'None'{% endcapture %}
{% for post in site.posts %}
  {% capture year %}{{ post.date | date: '%Y' }}{% endcapture %}
  <!-- {% if year != written_year %} -->
    <!-- <h2 id="{{ year | slugify }}" class="archive__subtitle">{{ year }}</h2> -->
    <!-- {% capture written_year %}{{ year }}{% endcapture %} -->
  <!-- {% endif %} -->
{% endfor %}

