---
layout: page
permalink: /talks/
title: talks
description:
nav: true
nav_order: 3
---

{% assign talks_by_year = site.data.talks | group_by_exp:"talk", "talk.date | date: '%Y'" %}
{% for year in talks_by_year reversed %}
  <h2 class="mt-4">{{ year.name }}</h2>
  {% for talk in year.items %}
    <div class="card my-3 p-3">
      <h4 class="mb-1">{{ talk.title }}</h4>
      <p class="mb-1"><strong>{{ talk.venue }}</strong> <br> <small>{{ talk.location }} &nbsp;|&nbsp; {{ talk.date }}</small></p>
      {% if talk.description %}
        <p>{{ talk.description }}</p>
      {% endif %}
      <div>
        {% if talk.slides %}
          <a href="{{ talk.slides }}" class="btn btn-sm btn-outline-primary me-2">Slides</a>
        {% endif %}
        {% if talk.video %}
          <a href="{{ talk.video }}" class="btn btn-sm btn-outline-secondary">Video</a>
        {% endif %}
      </div>
    </div>
  {% endfor %}
{% endfor %}