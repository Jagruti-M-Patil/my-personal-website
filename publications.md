---
layout: page
title: Publications & Conferences
---

{% assign pubs = site.data.publications %}
{% assign confs = site.data.conferences %}
{% assign hl = site.data.highlights %}

## Highlights

<div class="slider">
  <button class="slider-btn prev" aria-label="Previous" onclick="slideMove(-1)">‹</button>

  <div class="slider-track" id="sliderTrack">
    {% for h in hl %}
      <div class="slide">
        <img src="{{ h.image | relative_url }}" alt="{{ h.caption }}">
        <div class="caption">{{ h.caption }}</div>
      </div>
    {% endfor %}
  </div>

  <button class="slider-btn next" aria-label="Next" onclick="slideMove(1)">›</button>
</div>

<script>
  function slideMove(dir){
    const track = document.getElementById('sliderTrack');
    const slide = track.querySelector('.slide');
    if(!slide) return;
    const gap = 16;
    const step = slide.getBoundingClientRect().width + gap;
    track.scrollBy({ left: dir * step, behavior: 'smooth' });
  }
</script>

---

## Peer-Reviewed Publications

{% for p in pubs.peer_reviewed %}
<div class="pub card">
  <div class="pub-meta">{{ p.year }} • {{ p.venue }}</div>
  <div class="pub-title">{{ p.title }}</div>
  <div class="pub-authors">{{ p.authors }}</div>
  {% if p.url and p.url != "#" %}
    <div class="pub-links"><a class="btn secondary" href="{{ p.url }}" target="_blank" rel="noopener">{{ p.link_label }}</a></div>
  {% endif %}
</div>
{% endfor %}

## In Preparation

{% for p in pubs.in_preparation %}
<div class="pub card">
  <div class="pub-title">{{ p.title }}</div>
  <div class="pub-authors">{{ p.authors }}</div>
</div>
{% endfor %}

## Conference Presentations

{% for y in confs %}
### {{ y.year }}

{% for c in y.items %}
<div class="conf card">
  <div class="pub-title">{{ c.title }}</div>
  <div class="pub-authors">{{ c.authors }}</div>
  <div class="pub-meta">{{ c.venue }} • {{ c.location }} • {{ c.date }} • <span class="tag">{{ c.type }}</span></div>
</div>
{% endfor %}

{% endfor %}