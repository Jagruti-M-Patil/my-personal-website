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
document.addEventListener("DOMContentLoaded", function(){

  const track = document.getElementById("sliderTrack");
  const slides = track.children;
  let index = 0;
  let slideInterval;

  function moveToSlide(i){
    const slideWidth = slides[0].getBoundingClientRect().width + 16; // 16 = gap
    track.scrollTo({
      left: i * slideWidth,
      behavior: "smooth"
    });
  }

  function nextSlide(){
    index++;
    if(index >= slides.length){
      index = 0;
    }
    moveToSlide(index);
  }

  function startAutoSlide(){
    slideInterval = setInterval(nextSlide, 5000); // 5 seconds
  }

  function stopAutoSlide(){
    clearInterval(slideInterval);
  }

  // Arrow buttons still work
  window.slideMove = function(dir){
    index += dir;
    if(index < 0) index = slides.length - 1;
    if(index >= slides.length) index = 0;
    moveToSlide(index);
  }

  // Pause on hover
  track.addEventListener("mouseenter", stopAutoSlide);
  track.addEventListener("mouseleave", startAutoSlide);

  startAutoSlide();

});
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