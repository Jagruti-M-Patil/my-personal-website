---
layout: page
title: Publications
---

{% for pub in site.data.publications %}
<div class="card" style="margin:12px 0">
  <div class="muted">{{ pub.year }} • {{ pub.venue }}</div>
  <h3 style="margin:6px 0">{{ pub.title }}</h3>
  <div class="muted">{{ pub.authors }}</div>

  {% if pub.links %}
  <div class="btnrow">
    {% for lk in pub.links %}
      <a class="btn secondary" href="{{ lk.url }}" target="_blank" rel="noopener">{{ lk.label }}</a>
    {% endfor %}
  </div>
  {% endif %}
</div>
{% endfor %}