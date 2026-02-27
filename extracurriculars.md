---
layout: page
title: Extracurriculars
---
{% assign hl = site.data.extracurriculars_highlights %}

<div class="slider xl">
  <button class="slider-btn prev" aria-label="Previous" onclick="extraSlideMove(-1)">‹</button>

  <div class="slider-track" id="extraSliderTrack">
    {% for h in hl %}
      <div class="slide">
        <img src="{{ h.image | relative_url }}" alt="{{ h.caption }}">
        <div class="caption">{{ h.caption }}</div>
      </div>
    {% endfor %}
  </div>

  <button class="slider-btn next" aria-label="Next" onclick="extraSlideMove(1)">›</button>
</div>

<script>
document.addEventListener("DOMContentLoaded", function(){
  const track = document.getElementById("extraSliderTrack");
  const slides = track ? track.children : [];
  let index = 0;
  let timer;

  function moveTo(i){
    if(!slides.length) return;
    const step = slides[0].getBoundingClientRect().width + 16;
    track.scrollTo({ left: i * step, behavior: "smooth" });
  }

  function next(){
    if(!slides.length) return;
    index = (index + 1) % slides.length;
    moveTo(index);
  }

  function start(){ timer = setInterval(next, 4500); }
  function stop(){ clearInterval(timer); }

  window.extraSlideMove = function(dir){
    if(!slides.length) return;
    index = index + dir;
    if(index < 0) index = slides.length - 1;
    if(index >= slides.length) index = 0;
    moveTo(index);
  }

  track.addEventListener("mouseenter", stop);
  track.addEventListener("mouseleave", start);

  start();
});
</script>

<section class="grid grid-2" style="margin-top:18px;">

  <div class="card">
    <div class="section-head">
      <h2 style="margin:0;">Training & Certifications</h2>
      <span class="pill">Training</span>
    </div>

    <ul class="clean-list">
      <li><strong>R10 Ethics Champion</strong>, IEEE R10 Ethics Super Power Challenge Assessment (2024)</li>
      <li>Certification in Scientific Writing, IIT Gandhinagar (2023)</li>
      <li>Workshop on Ethical Conduct of Research on Human Participants, IIT Gandhinagar (2023)</li>
      <li>Foundations of Healthcare Systems Engineering, Johns Hopkins University (Coursera)</li>
    </ul>
  </div>

  <div class="card">
    <div class="section-head">
      <h2 style="margin:0;">Service & Leadership</h2>
      <span class="pill">Service</span>
    </div>

    <ul class="clean-list">
      <li>Member, Ultrasonics Student Volunteer Committee, <strong>IEEE IUS 2025</strong></li>
      <li>Organizing Team Member, NYASA IIT Gandhinagar: Spreading Smiles (2024, 2025)</li>
      <li>Local Organizing Committee Member, IEEE South Asian Ultrasonics Symposium (2024)</li>
      <li>Volunteer, 7th edition of Sanjeevani: Health and Awareness Mela by NYASA IITGN (2023)</li>
      <li>Volunteer, Orientation program: 1st year B.E. Biomedical Freshers, LDCE (2019)</li>
      <li>Exam Writer, Divyang Seva Mandal: University exam for blind students (2017)</li>
    </ul>
  </div>

</section>

<section style="margin-top:22px;">
  <div class="card">
    <div class="section-head">
      <h2 style="margin:0;">Honors & Awards</h2>
      <span class="pill">Honors</span>
    </div>

    <ul class="clean-list">
      <li><strong>Best Poster Award</strong>, Annual PMRF Symposium, IIT Hyderabad (2025) — Biological Sciences & Engineering</li>
      <li><strong>3rd Place, Best Poster Award</strong>, IEEE South Asian Ultrasonics Symposium, Gandhinagar, India (2024)</li>
      <li><strong>Prime Minister’s Research Fellowship (PMRF)</strong>, Cycle 11 (May 2023)</li>
      <li><strong>GATE Biomedical 2022</strong> — AIR 19 (out of 1614 candidates)</li>
      <li><strong>Gold Medalist</strong>, Branch Topper — B.E. Biomedical Engineering, GTU (2021)</li>
      <li>Kaizen 2021 — Second position (Final Year UG Project): Neuron Modeling for Healthy and Alzheimer’s Condition</li>
    </ul>
  </div>
</section>