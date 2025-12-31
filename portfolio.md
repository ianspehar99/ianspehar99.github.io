{% for item in site.portfolio %}
---

### [{{ item.title }}]({{ item.url }})

{% if item.image %}
<img src="{{ item.image }}" alt="{{ item.title }}" style="max-width:300px;">
{% endif %}

{{ item.excerpt }}

{% endfor %}
