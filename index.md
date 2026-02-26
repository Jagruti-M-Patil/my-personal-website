---
layout: default
---

{% assign p = site.data.profile %}

<section class="hero">
  <div class="grid grid-2">
    <div>
      <h1 class="h1">{{ p.name }}</h1>
      <p class="sub">{{ p.role }}</p>

      <div class="badges">
        <span class="badge">Biomedical Ultrasound</span>
        <span class="badge">H-scan</span>
        <span class="badge">Envelope Statistics</span>
        <span class="badge">Tissue Phantoms</span>
      </div>

      <div class="btnrow">
        <a class="btn" href="{{ '/research' | relative_url }}">Explore Research</a>
        <a class="btn secondary" href="{{ '/publications' | relative_url }}">Publications</a>
      </div>

      <p class="muted" style="margin-top:16px">{{ p.tagline }}</p>
    </div>

    <div class="card">
      <h3 style="margin-top:0">Quick Links</h3>
      <ul class="list">
        {% for l in p.links %}
          <li class="item"><a href="{{ l.url }}" target="_blank" rel="noopener">{{ l.label }}</a></li>
        {% endfor %}
        <li class="item"><a href="{{ '/contact' | relative_url }}">Contact</a></li>
      </ul>
    </div>
  </div>
</section>

<section class="grid grid-2">
  <div class="card">
    <h3 style="margin-top:0">Current Focus</h3>
    <ul class="list">
      <li class="item">QUS for ex-vivo brain tissue (GBM vs normal)</li>
      <li class="item">Longitudinal oral lesion progression imaging</li>
      <li class="item">Tissue-mimicking phantoms for calibration & validation</li>
    </ul>
  </div>
  <div class="card">
    <h3 style="margin-top:0">What I build</h3>
    <ul class="list">
      <li class="item">Signal processing pipelines (MATLAB / Python)</li>
      <li class="item">Quantitative imaging metrics & visualizations</li>
      <li class="item">Reproducible analysis workflows</li>
    </ul>
  </div>
</section>