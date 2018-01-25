---
layout: default
title: Theme Help
---

{% for setup in site.setup %}


  <a href="{{ setup.url | relative_url }}">
    <h2>{{ setup.title }}</h2>
  </a>

  <p class="post-excerpt">{{ setup.description | truncate: 160 }}</p>

{% endfor %}
