---
layout: page
title: 
permalink: /
---

<style>
  .container { max-width: 70% !important; } 
  .resource-btn { margin-bottom: 8px; margin-right: 4px; display: inline-block; min-width: 100px; }
  .bio-img { width: 100%; max-width: 280px; }
  
  /* Custom Heading Styles */
  .main-name { font-size: 2.8rem; margin-bottom: 0; }
  .main-subtitle { font-size: 1.2rem; color: #777; margin-bottom: 2rem; }
  
  /* Link style for the subtitle */
  .highlight-link { color: var(--global-theme-color) !important; text-decoration: none; }
  .highlight-link:hover { text-decoration: underline; }
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

    <div class="posts-sidebar mt-4">
      <h5 class="font-weight-bold mb-3">Latest Posts</h5>
      {% if site.posts.size > 0 %}
        <ul style="list-style-type: none; padding-left: 0;">
          {% for post in site.posts limit:3 %}
            <li class="mb-2">
              <a href="{{ post.url | relative_url }}" style="color: var(--global-theme-color); font-weight: 500; font-size: 0.95rem;">{{ post.title }}</a>
              <br>
              <small class="text-muted">{{ post.date | date: "%b %d, %Y" }}</small>
            </li>
          {% endfor %}
        </ul>
      {% else %}
        <p class="text-muted" style="font-size: 0.9rem;">No posts yet.</p>
      {% endif %}
    </div>
    
  </div>

  ##### Latest Publication

  {% bibliography -f papers -q @article --sort_by year --order descending --max 1 %}
  
  <p style="font-size: 0.85rem;"><a href="/research/">View all publications →</a></p>

</div>
