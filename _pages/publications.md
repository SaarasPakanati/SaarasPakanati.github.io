---
layout: page
permalink: /research/
title: research
nav: true
nav_order: 2
---

Please refer to my <a href="https://scholar.google.com/citations?user=N44aHPUAAAAJ&hl=en&oi=ao">Google Scholar</a> for an up-to-date publications list.

*\*Denotes equal contribution.* {% include bib_search.liquid %}

<div class="publications">

  <h3 class="mt-4 mb-3">Peer-Reviewed Publications</h3>
  {% bibliography -q @*[type=article]* %}

  <h3 class="mt-5 mb-3">Conference & Poster Presentations</h3>
  {% bibliography -q @*[type=inproceedings]* %}

  <h3 class="mt-5 mb-3">Outreach & Invited Talks</h3>
  {% bibliography -q @*[type=misc]* %}

</div>
