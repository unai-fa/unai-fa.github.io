---
layout: page
permalink: /talks/
title: talks
description: Conference presentations and invited talks
nav: true
nav_order: 3
---

{% for talk in site.data.talks %}
<div class="talk">
  <h3>{{ talk.title }}</h3>
  <p><strong>{{ talk.venue }}</strong> | {{ talk.location }} | {{ talk.date }}</p>
  {% if talk.description %}
    <p>{{ talk.description }}</p>
  {% endif %}
  {% if talk.slides %}
    <a href="{{ talk.slides }}" class="btn btn-sm btn-primary">Slides</a>
  {% endif %}
  {% if talk.video %}
    <a href="{{ talk.video }}" class="btn btn-sm btn-secondary">Video</a>
  {% endif %}
</div>
<hr>
{% endfor %}