---
layout: default
---

{% assign p = site.data.profile %}

<section class="hero">
  <div class="grid grid-2">

    <div>
      <h1 class="h1">{{ p.name }}</h1>
      <p class="sub">{{ p.role }}</p>

      <p style="max-width:520px;">
        I develop advanced quantitative ultrasound techniques to characterize 
        tissue microstructure and enable early detection of pathological changes. 
        My work integrates signal processing, envelope statistics, and 
        tissue-mimicking phantoms for validation.
      </p>

      <div class="btnrow" style="margin-top:20px;">
        <a class="btn" href="{{ '/assets/CV.pdf' | relative_url }}">Download CV</a>
        <a class="btn secondary" href="https://scholar.google.com" target="_blank">Google Scholar</a>
      </div>
    </div>

    <div>
      <img src="{{ '/assets/img/profile.jpg' | relative_url }}" 
           style="width:100%; border-radius:16px; border:1px solid #e5e7eb;">
    </div>

  </div>
</section>


<section>
  <h2>Research Focus</h2>
  <div class="grid grid-2" style="margin-top:20px;">

    <div class="card">
      <h3>Quantitative Ultrasound</h3>
      <p>
        Envelope statistics (Nakagami, Burr), H-scan imaging, and 
        integrated backscatter analysis for tissue differentiation.
      </p>
    </div>

    <div class="card">
      <h3>Brain & Oral Tissue Studies</h3>
      <p>
        Ex-vivo glioblastoma analysis and longitudinal oral lesion 
        progression using advanced QUS parameters.
      </p>
    </div>

    <div class="card">
      <h3>Tissue-Mimicking Phantoms</h3>
      <p>
        Designing agarose and PVA-based phantoms with controlled 
        acoustic scatterers for validation and benchmarking.
      </p>
    </div>

    <div class="card">
      <h3>Signal Processing Pipelines</h3>
      <p>
        MATLAB & Python workflows for reproducible quantitative 
        imaging and statistical analysis.
      </p>
    </div>

  </div>
</section>