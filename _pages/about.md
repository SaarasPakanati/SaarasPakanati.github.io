---
layout: page
title: 
permalink: /
---
<style>
  .container { max-width: 70% !important; } 
  .resource-btn { margin-bottom: 8px; margin-right: 4px; display: inline-block; min-width: 100px; }
  .bio-img { width: 100%; max-width: 280px; }
  
  .main-name { font-size: 2.8rem; margin-bottom: 0; }
  .main-subtitle { font-size: 1.2rem; color: #777; margin-bottom: 2rem; }
  
  .highlight-link { color: var(--global-theme-color) !important; text-decoration: none; }
  .highlight-link:hover { text-decoration: underline; }
  /* Hide year header and all entries after the first */
  .latest-publication h2 { display: none !important; }
  .latest-publication ol.bibliography li:not(:first-child) { display: none !important; }
  .latest-publication ol.bibliography { padding-left: 0; margin-bottom: 0.5rem; }
</style>
<div class="row">
  <div class="col-12">
    <h1 class="main-name"><b>Saaras</b> Pakanati</h1>
    <p class="main-subtitle">
      <a href="https://pi.rice.edu" class="highlight-link">Incoming PhD Student</a>. Rice University
    </p>
  </div>
</div>
<div class="row mt-2">
  <div class="col-sm-8">
    <div class="profile float-left mr-4 mb-3">
      <img src="{{ 'assets/img/SaarasWebsitePic_052226.jpg' | relative_url }}" class="img-fluid z-depth-1 rounded bio-img">
    </div>
    <div class="clearfix bio-content">
      <p>Hey! I am Saaras Pakanati, an incoming PhD student in Mechanical Engineering at Rice University, advised by Dr. Daniel Preston.</p>
      <p>I previously worked as an undergraduate research assistant at the <a href="https://kishanbellur.github.io">UC Lab for Interfacial Dynamics</a>, advised by Dr. Kishan Bellur, studying fuel evaporation in space and thermally sensitive surfactant-based interfacial control.</p>
    </div>
  </div>
  <div class="col-sm-4 border-left pl-4">
    <div class="resources-section mb-4">
      <h5 class="font-weight-bold mb-3">Resources</h5>
      <div class="d-flex flex-wrap">
        <a href="{{ 'assets/pdf/Saaras_Pakanati_CV_Website.pdf' | relative_url }}" class="btn btn-sm btn-outline-primary resource-btn">
          <i class="fas fa-file-pdf"></i> VIEW CV
        </a>
        <a href="https://www.linkedin.com/in/saaras-pakanati/" class="btn btn-sm btn-outline-info resource-btn">
          <i class="fab fa-linkedin"></i> LINKEDIN
        </a>
        <a href="mailto:pakanass@mail.uc.edu" class="btn btn-sm btn-outline-secondary resource-btn">
          <i class="fas fa-envelope"></i> EMAIL
        </a>
      </div>
    </div>
    <hr>
    <div class="mt-4">
      <h5 class="font-weight-bold mb-3">Latest Publication</h5>
      <div class="publications latest-publication">
        {% bibliography -f papers -q @article --sort_by year --order descending %}
      </div>
      <p style="font-size: 0.85rem;"><a href="/research/">View all publications →</a></p>
    </div>
  </div>
</div>
