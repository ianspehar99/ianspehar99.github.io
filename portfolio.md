<div class="portfolio-grid">
  {% for item in site.portfolio %}
    <a href="{{ item.url }}" class="portfolio-item">
      {% if item.image %}
      <img src="{{ item.image }}" alt="{{ item.title }}">
      {% endif %}
      <h3>{{ item.title }}</h3>
      <p>{{ item.excerpt }}</p>
    </a>
  {% endfor %}
</div>
