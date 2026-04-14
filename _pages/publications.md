---
layout: page
permalink: /research/
title: research
nav: true
nav_order: 2
---

Please refer to my <a href="https://scholar.google.com/citations?user=N44aHPUAAAAJ&hl=en&oi=ao">Google Scholar</a> for an up-to-date publications list.

*\*Denotes equal contribution.*

<link rel="stylesheet" href="https://unpkg.com/leaflet@1.9.4/dist/leaflet.css" />
<script src="https://unpkg.com/leaflet@1.9.4/dist/leaflet.js"></script>

<div class="publications mt-4">
  <h3 class="font-weight-bold mb-3">Where my work has been presented (as far as I am aware)</h3>
  <div id="talks-map" style="height: 300px; width: 100%; border-radius: 8px;" class="z-depth-1"></div>
</div>

<script>
  // Initialize the map centered on the US
  var map = L.map('talks-map').setView([39.8283, -98.5795], 4);

  L.tileLayer('https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png', {
    attribution: '© OpenStreetMap'
  }).addTo(map);

  // Add your talk locations here
  // Format: [Latitude, Longitude]
  var locations = [
    { name: "University of Cincinnati (Multiple Talks), Cincinnati OH", coords: [39.1329, -84.5150] },
    { name: "ASME IMECE 2025, Memphis TN", coords: [35.15200281608736, -90.05101930172134] },
    { name: "ASTFE 2026, Tempe AZ", coords: [33.423117434733776, -111.92745227008359] },
    { name: "MUFMECH 2025, Rochester IN", coords: [41.06446118348553, -86.21701802940963] },
    { name: "MUFMECH 2026, Cedar Lake IN", coords: [41.36416165394076, -87.44475850132815] },
    // Add more here, e.g., { name: "Conference Name, City", coords: [lat, lng] }
  ];

  locations.forEach(function(loc) {
    L.marker(loc.coords).addTo(map).bindPopup("<b>" + loc.name + "</b>");
  });
</script>

<div class="publications">
  {% include bib_search.liquid %}
</div>

<div class="publications">

  <h3 class="mt-4 mb-3">Peer-Reviewed Publications</h3>
  {% bibliography -f papers -q @article %}

  <h3 class="mt-5 mb-3">Conference & Poster Presentations</h3>
  {% bibliography -f papers -q @inproceedings %}

  <h3 class="mt-5 mb-3">Outreach & Invited Talks</h3>
  {% bibliography -f papers -q @misc %}

</div>
