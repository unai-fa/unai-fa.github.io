---
layout: page
permalink: /talks/
title: talks
nav: true
nav_order: 3
---

{% for talk in site.data.talks %}
  <h3>{{ talk.title }}</h3>
  <p><strong>{{ talk.venue }}</strong><br>{{ talk.location }} | {{ talk.date }}</p>
  <hr>
{% endfor %}