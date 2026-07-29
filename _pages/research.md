<style>
  header.post-header, .post-title { display: none !important; }

  .container {
    max-width: 80% !important;
    margin-left: auto !important;
    margin-right: auto !important;
  }

  /* ---- Section headers: bold, larger, clearly separated ---- */
  .publications h3 {
    font-weight: 700 !important;
    font-size: 1.35rem;
    letter-spacing: 0.01em;
    margin-top: 3.5rem;
    margin-bottom: 1.5rem;
    padding-bottom: 8px;
    border-bottom: 2px solid var(--global-theme-color);
    color: #222;
  }

  .pub-meta-line {
    font-size: 0.82rem;
    color: #999;
    margin-bottom: 2rem;
    font-weight: 300;
  }
  .pub-meta-line a { color: var(--global-theme-color); }
  .pub-meta-line .divider { margin: 0 8px; color: #ddd; }

  .publications input[type="text"],
  .publications input[type="search"] {
    max-width: 400px;
    width: 100%;
    border: none;
    border-bottom: 1px solid #ddd;
    border-radius: 0;
    padding: 4px 2px;
  }

  /* ---- Kill Bootstrap's reserved preview column when there's no image ---- */
  .bibliography li .row {
    display: flex !important;
    flex-wrap: wrap;
    margin: 0 !important;
    align-items: flex-start;
  }
  .bibliography li .row > [class*="col-"] {
    width: auto;
    max-width: 100%;
    padding: 0 !important;
    flex: 1 1 100%;
  }
  /* Only reserve space for preview column if it actually contains an image */
  .bibliography li .row:has(.preview img) > .preview {
    flex: 0 0 110px;
    margin-right: 24px;
  }
  .bibliography li .row:has(.preview img) > [class*="col-"]:not(.preview):not(.abbr) {
    flex: 1 1 0;
  }
  .bibliography li .preview:not(:has(img)) {
    display: none !important;
  }
  .bibliography li .preview img {
    max-width: 110px;
    border-radius: 4px;
  }

  /* ---- Entry-level minimalism ---- */
  .bibliography { list-style: none; padding-left: 0; }
  .bibliography li {
    padding: 1.4rem 0;
    margin-bottom: 0;
    border-bottom: 1px solid #f0f0f0;
  }
  .bibliography li:first-of-type { padding-top: 0; }
  .bibliography li:last-child { border-bottom: none; }
  .bibliography .title {
    font-weight: 500;
    font-size: 0.98rem;
    color: #222;
    margin-bottom: 0.25rem;
  }
  .bibliography .author {
    font-size: 0.87rem;
    color: #666;
    font-weight: 300;
    margin-bottom: 0.15rem;
  }
  .bibliography .author > em {
    color: #222;
    font-style: normal;
    font-weight: 500;
  }
  .bibliography .periodical {
    font-size: 0.85rem;
    color: #999;
    font-style: italic;
    margin-bottom: 0.5rem;
  }
  .bibliography abbr.abbr {
    background: none !important;
    color: var(--global-theme-color) !important;
    border: 1px solid var(--global-theme-color);
    font-size: 0.7rem;
    padding: 1px 6px;
    border-radius: 3px;
    font-weight: 400;
  }
  .bibliography .links,
  .bibliography .links a.btn { margin-top: 0.4rem; }
  .bibliography .links a.btn {
    display: inline;
    background: none !important;
    border: none !important;
    box-shadow: none !important;
    color: #888 !important;
    font-size: 0.8rem;
    font-weight: 400;
    padding: 0;
    margin-right: 14px;
    text-transform: none;
    border-radius: 0;
  }
  .bibliography .links a.btn:hover {
    color: var(--global-theme-color) !important;
    text-decoration: underline;
  }
  .bibliography .abstract.hidden {
    border: none;
    background: #fafafa;
    font-size: 0.85rem;
    color: #555;
    padding: 10px 14px;
    margin-top: 8px;
    border-radius: 4px;
  }
  /* de-emphasize the floated year badge so it doesn't dominate */
  .bibliography li .year, .bibliography li abbr.badge {
    color: #ddd !important;
    font-weight: 300 !important;
  }

  /* ---- Map ---- */
  #talks-map {
    height: 350px;
    width: 100%;
    border-radius: 4px;
    border: 1px solid #eee;
    margin-top: 10px;
    margin-bottom: 24px;
    z-index: 1;
  }
  .map-caption {
    font-size: 0.8rem;
    color: #999;
    margin-top: -18px;
    margin-bottom: 24px;
    font-style: italic;
    font-weight: 300;
  }

  @media (max-width: 768px) {
    .container { max-width: 95% !important; }
  }
</style>  }
  .bibliography .author > em {
    color: #222;
    font-style: normal;
    font-weight: 500;
  }
  .bibliography .periodical {
    font-size: 0.85rem;
    color: #999;
    font-style: italic;
    margin-bottom: 0.5rem;
  }
  .bibliography abbr.abbr {
    background: none !important;
    color: var(--global-theme-color) !important;
    border: 1px solid var(--global-theme-color);
    font-size: 0.7rem;
    padding: 1px 6px;
    border-radius: 3px;
    font-weight: 400;
  }

  /* links row -> quiet text links instead of buttons */
  .bibliography .links,
  .bibliography .links a.btn {
    margin-top: 0.4rem;
  }
  .bibliography .links a.btn {
    display: inline;
    background: none !important;
    border: none !important;
    box-shadow: none !important;
    color: #888 !important;
    font-size: 0.8rem;
    font-weight: 400;
    padding: 0;
    margin-right: 14px;
    text-transform: none;
    border-radius: 0;
  }
  .bibliography .links a.btn:hover {
    color: var(--global-theme-color) !important;
    text-decoration: underline;
  }

  .bibliography .abstract.hidden {
    border: none;
    background: #fafafa;
    font-size: 0.85rem;
    color: #555;
    padding: 10px 14px;
    margin-top: 8px;
    border-radius: 4px;
  }

  /* ---- Map: hairline instead of card ---- */
  #talks-map {
    height: 350px;
    width: 100%;
    border-radius: 4px;
    border: 1px solid #eee;
    margin-top: 10px;
    margin-bottom: 24px;
    z-index: 1;
  }
  .map-caption {
    font-size: 0.8rem;
    color: #999;
    margin-top: -18px;
    margin-bottom: 24px;
    font-style: italic;
    font-weight: 300;
  }

  @media (max-width: 768px) {
    .container { max-width: 95% !important; }
  }
</style>
<link rel="stylesheet" href="https://unpkg.com/leaflet@1.9.4/dist/leaflet.css" />
<script src="https://unpkg.com/leaflet@1.9.4/dist/leaflet.js"></script>
<div class="publications">
  <p class="pub-meta-line">
    Full list on <a href="https://scholar.google.com/citations?user=N44aHPUAAAAJ&hl=en&oi=ao">Google Scholar ↗</a>
    <span class="divider">·</span>
    <i>* denotes equal contribution</i>
  </p>
  {% include bib_search.liquid %}
  <h3>Peer-Reviewed Publications</h3>
  {% bibliography -f papers -q @article --sort_by year --order descending %}
  <h3>Conference & Poster Presentations</h3>
  {% bibliography -f papers -q @inproceedings --sort_by year --order descending %}
  <h3>Invited Talks</h3>
  {% bibliography -f papers -q @misc --sort_by year --order descending %}
  <div id="talks-map"></div>
  <p class="map-caption">Pins mark conference, poster and invited presentation venues.</p>
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
