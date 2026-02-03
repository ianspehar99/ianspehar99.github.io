---
title: Portfolio
permalink: /portfolio/
---

<div class="portfolio-grid">
  {% assign sorted_portfolio = site.portfolio | sort: "order" %}
  {% for item in sorted_portfolio %}
    <a class="portfolio-item" href="{{ item.url }}">
      
      {% if item.image %}
        <div class="portfolio-image">
          <img src="{{ item.image }}" alt="{{ item.title }}">
        </div>
      {% endif %}

      <h3>{{ item.title }}</h3>
      <p>{{ item.excerpt }}</p>
    </a>
  {% endfor %}
</div>

