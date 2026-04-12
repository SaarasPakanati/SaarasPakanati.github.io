---
layout: page
title: about
permalink: /
subtitle: <a href='https://kishanbellur.github.io/'>Undergraduate Student Researcher</a>. University of Cincinnati
---

<div class="row">
  
  <div class="col-sm-8">
    <div class="profile float-left mr-3 mb-3">
      <img src="{{ 'assets/img/SaarasWebsitePic_121425.jpg' | relative_url }}" class="img-fluid z-depth-1 rounded" style="width: 100%; max-width: 300px;">
      <div class="address mt-2 text-center" style="font-size: 0.85rem; color: #777;">
        Cincinnati, Ohio
      </div>
    </div>

    <div class="clearfix bio-content">
      <p>Hey! I am Saaras Pakanati. I am a Mechanical Engineering Senior at the University of Cincinnati (<a href="https://www.uc.edu/campaigns/points-of-pride.html">Go Bearcats!</a>), working on multiphase flows.</p>

      <p>I am currently interested in exploring computational fluid dynamics and numerical techniques for optimizing simulations, with my current research spanning the experimental and computational evaluation of instabilities in liquid thin films, long-term storage of fuels in space, the development of contactless optical methods for spatio-temporal temperature measurement, and surfactant-based control of interfacial phenomena.</p>
    </div>
  </div>

  <div class="col-sm-4 border-left pl-4">
    
    <div class="resources-section mb-5">
      <h5 class="font-weight-bold mb-3">Resources</h5>
      <a href="{{ 'assets/pdf/Saaras_Pakanati_CV_Website.pdf' | relative_url }}" class="btn btn-sm btn-outline-primary btn-block mb-2">
        <i class="fas fa-file-pdf"></i> View CV
      </a>
      <a href="https://www.linkedin.com/in/saaras-pakanati/" class="btn btn-sm btn-outline-info btn-block mb-2">
        <i class="fab fa-linkedin"></i> LinkedIn
      </a>
      <a href="mailto:pakanass@mail.uc.edu" class="btn btn-sm btn-outline-secondary btn-block">
        <i class="fas fa-envelope"></i> Email
      </a>
    </div>

    <hr>

    <div class="posts-sidebar mt-4">
      <h5 class="font-weight-bold mb-3">Latest Posts</h5>
      {% if site.posts.size > 0 %}
        <ul style="list-style-type: none; padding-left: 0;">
          {% for post in site.posts limit:3 %}
            <li class="mb-3">
              <a href="{{ post.url | relative_url }}" style="color: var(--global-theme-color); font-weight: 500;">{{ post.title }}</a>
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

</div>
