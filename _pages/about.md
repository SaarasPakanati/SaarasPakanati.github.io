---
layout: about
title: about
permalink: /
subtitle: <a href='https://kishanbellur.github.io/'>Undergraduate Student Researcher</a>. University of Cincinnati

# We set these to false/null so the theme doesn't automatically 
# inject them in the wrong places.
profile: 
  enabled: false
selected_papers: false 
social: false 

announcements:
  enabled: false 

latest_posts:
  enabled: false 
---

<div class="row">
  
  <div class="col-sm-8">
    <div class="profile float-left mr-3 mb-2">
      <img src="{{ 'assets/img/SaarasWebsitePic_121425.jpg' | relative_url }}" class="img-fluid z-depth-1 rounded" width="250px">
      <div class="address mt-1 text-center" style="font-size: 0.8rem;">
        Cincinnati, Ohio
      </div>
    </div>

    <div class="clearfix">
      <p>Hey! I am Saaras Pakanati. I am a Mechanical Engineering Senior at the University of Cincinnati (<a href="https://www.uc.edu/campaigns/points-of-pride.html">Go Bearcats!</a>), working on multiphase flows.</p>

      <p>I am currently interested in exploring computational fluid dynamics and numerical techniques for optimizing simulations, with my current research spanning the experimental and computational evaluation of instabilities in liquid thin films, long-term storage of fuels in space, the development of contactless optical methods for spatio-temporal temperature measurement, and surfactant-based control of interfacial phenomena.</p>
      
      <p>Feel free to reach out over <a href="mailto:pakanass@mail.uc.edu">Email</a>!</p>
    </div>
  </div>

  <div class="col-sm-4 border-left">
    
    <div class="sidebar-links mb-4">
      <h5 class="font-weight-bold">Resources</h5>
      <ul style="list-style-type: none; padding-left: 0;">
        <li class="mb-2">
          <a href="{{ 'assets/pdf/Saaras_Pakanati_CV_Website.pdf' | relative_url }}" class="btn btn-sm btn-outline-primary btn-block">
            <i class="fas fa-file-pdf"></i> View CV
          </a>
        </li>
        <li>
          <a href="https://www.linkedin.com/in/saaras-pakanati/" class="btn btn-sm btn-outline-info btn-block">
            <i class="fab fa-linkedin"></i> LinkedIn
          </a>
        </li>
      </ul>
    </div>

    <hr>

    <div class="latest-posts">
      <h5 class="font-weight-bold">Latest Posts</h5>
      {% include latest_posts.html %}
    </div>
    
  </div>

</div>
