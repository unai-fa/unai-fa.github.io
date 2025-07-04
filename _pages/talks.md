---
layout: page
permalink: /talks/
title: talks
nav: true
nav_order: 3
---

{% assign sorted_talks = site.data.talks | sort: 'date' | reverse %}
{% assign years = sorted_talks | map: 'date' | map: 'split' | map: first | uniq %}

{% for year in years %}
  <h3 class="mt-4 mb-3">{{ year }}</h3>
  <ul class="list-unstyled">
  {% for talk in sorted_talks %}
    {% if talk.date contains year %}
      <li class="mb-3">
        <h5 class="mb-1">{{ talk.title }}</h5>
        <p class="mb-0 text-muted small">
          <strong>{{ talk.venue }}</strong> – {{ talk.location }} | {{ talk.date }}
        </p>
      </li>
    {% endif %}
  {% endfor %}
  </ul>
{% endfor %}