---
layout: page
permalink: /research/
nav: true
nav_order: 2
---

<style>
  /* 1. Aggressively hide the default page header and title */
  header.post-header, h1.post-title { display: none !important; }
  
  /* 2. Widen the container for this specific page */
  .container { max-width: 95% !important; }
  
  /* 3. Standardize the header weights to match the theme */
  .publications h3 { 
    font-weight: 500 !important; 
    margin-top: 2.5rem; 
    margin-bottom: 1rem; 
  }
</style>

<div class="publications">
  <p>Please refer to my <a href="https://scholar.google.com/citations?user=N44aHPUAAAAJ&hl=en&oi=ao">Google Scholar</a> for an up-to-date publications list.</p>
  <p><i>*Denotes equal contribution.</i></p>
</div>

<link rel="stylesheet" href="https://unpkg.com/leaflet@1.9.4/dist/leaflet.css" />
<script src="https://unpkg.com/leaflet@1.9.4/dist/leaflet.js"></script>

<div class="publications">
  <h3>Where my work has been presented</h3>
  <div id="talks-map" style="height: 350px; width: 100%; border-radius: 8px; border: 1px solid #ddd; margin-bottom: 20px; z-index: 1;"></div>
</div>

<script>
  document.addEventListener("DOMContentLoaded", function() {
    var map = L.map('talks-map').setView([39.8283, -98.5795], 4);
    
    L.tileLayer('https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png', {
      attribution: '© OpenStreetMap'
    }).addTo(map);

    var locations = [
      { name: "University of Cincinnati (Multiple Talks), Cincinnati OH", coords: [39.1329, -84.5150] },
      { name: "ASME IMECE 2025, Memphis TN", coords: [35.15200281608736, -90.05101930172134] },
      { name: "ASTFE 2026, Tempe AZ", coords: [33.423117434733776, -111.92745227008359] },
      { name: "MUFMECH 2025, Rochester IN", coords: [41.06446118348553, -86.21701802940963] },
      { name: "MUFMECH 2026, Cedar Lake IN", coords: [41.36416165394076, -87.44475850132815] }
    ];

    locations.forEach(function(loc) {
      L.marker(loc.coords).addTo(map).bindPopup("<b>" + loc.name + "</b>");
    });
  });
</script>

<div class="publications">
  {% include bib_search.liquid %}
  
  <h3>Peer-Reviewed Publications</h3>
  {% bibliography -f papers -q @article %}

  <h3>Conference & Poster Presentations</h3>
  {% bibliography -f papers -q @inproceedings %}

  <h3>Outreach & Invited Talks</h3>
  {% bibliography -f papers -q @misc %}
</div>
