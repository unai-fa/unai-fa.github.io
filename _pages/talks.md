---
layout: page
permalink: /talks/
title: talks
description:
nav: true
nav_order: 3
---

{% assign sorted_talks = site.data.talks | sort: 'date' | reverse %}
{% assign years = sorted_talks | map: 'date' | map: 'split' | map: first | uniq %}

{% for year in years %}
  <h2 class="mt-5">{{ year }}</h2>
  {% for talk in sorted_talks %}
    {% if talk.date contains year %}
      <div class="card my-3 p-3">
        <h4 class="mb-1">{{ talk.title }}</h4>
        <p class="mb-1">
          <strong>{{ talk.venue }}</strong><br>
          <small>{{ talk.location }} &nbsp;|&nbsp; {{ talk.date }}</small>
        </p>
        {% if talk.description %}
          <p class="mb-1">{{ talk.description }}</p>
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
    {% endif %}
  {% endfor %}
{% endfor %}