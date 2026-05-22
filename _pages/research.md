---
layout: page
permalink: /research/
title: research
nav: true
nav_order: 2
---
<style>
  header.post-header, .post-title { display: none !important; }
  
  .container { 
    max-width: 70% !important; 
    margin-left: auto !important;
    margin-right: auto !important;
  }
  
  .publications h3 { 
    font-weight: 500 !important; 
    margin-top: 2.5rem; 
    margin-bottom: 1rem; 
    border-bottom: 1px solid #eee;
    padding-bottom: 5px;
  }

  #talks-map {
    height: 350px;
    width: 100%;
    border-radius: 8px;
    border: 1px solid #ddd;
    margin-top: 10px;
    margin-bottom: 24px;
    z-index: 1;
  }

  .map-caption {
    font-size: 0.82rem;
    color: #888;
    margin-top: -18px;
    margin-bottom: 24px;
    font-style: italic;
  }

  @media (max-width: 768px) {
    .container { max-width: 95% !important; }
  }
</style>
<link rel="stylesheet" href="https://unpkg.com/leaflet@1.9.4/dist/leaflet.css" />
<script src="https://unpkg.com/leaflet@1.9.4/dist/leaflet.js"></script>

<div class="publications">
  <p>Please refer to my <a href="https://scholar.google.com/citations?user=N44aHPUAAAAJ&hl=en&oi=ao">Google Scholar</a> for an up-to-date publications list.</p>
  <p><i>*Denotes equal contribution.</i></p>
</div>

<div class="publications">
  {% include bib_search.liquid %}
  
  <h3>Peer-Reviewed Publications</h3>
  {% bibliography -f papers -q @article --sort_by year --order descending %}

  <h3>Conference & Poster Presentations</h3>
  <div id="talks-map"></div>
  <p class="map-caption">Pins mark conference and poster presentation venues.</p>
  {% bibliography -f papers -q @inproceedings --sort_by year --order descending %}

  <h3>Outreach & Invited Talks</h3>
  {% bibliography -f papers -q @misc --sort_by year --order descending %}
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
