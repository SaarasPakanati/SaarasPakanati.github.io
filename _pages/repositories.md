---
layout: page
permalink: /repositories/
title: repositories
description: Open-source contributions and personal projects.
nav: true
nav_order: 4
---
<style>
  .container { max-width: 80% !important; }
</style>
<p class="mt-3" style="max-width: 640px;">
  My open-source contributions are attached below. Some are fun, and others are even more fun.
  All source codes are on <a href="https://github.com/saaraspakanati" target="_blank">GitHub</a>.
</p>
<div id="repo-grid" style="
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
  gap: 1rem;
  margin-top: 2rem;
">
  <p id="repo-loading" style="color: gray; font-size: 0.9rem;">Loading repositories…</p>
</div>
<script>
(async () => {
  const grid = document.getElementById('repo-grid');
  const loading = document.getElementById('repo-loading');

  const pinnedFirst = [
    'SaarasPakanati.github.io',
    'One-Dimensional-Heat-Transfer-FDM-Code',
    'W04-Droplet-Evaporation-Simulator',
  ];

  const allowlist = [
    'SaarasPakanati.github.io',
    'One-Dimensional-Heat-Transfer-FDM-Code',
    'W04-Droplet-Evaporation-Simulator',
  ];

  const externalPinned = [
    'https://api.github.com/repos/UC-Lab-For-Interfacial-Dynamics/EMEM',
  ];

  const descriptions = {
    'EMEM': 'CFD solver for evaporating menisci in cryogenic systems, developed by the University of Cincinnati Lab for Interfacial Dynamics.',
    'SaarasPakanati.github.io': 'The source code for the website you are currently using!',
    'One-Dimensional-Heat-Transfer-FDM-Code': 'MATLAB Analysis of the Stability and Application of Finite Difference Methods in Heat Transfer Problems',
    'W04-Droplet-Evaporation-Simulator': 'PI Control for Maintaining Constant Droplet Size During Evaporation Using MATLAB',
  };

  try {
    const [personalRes, ...externalRes] = await Promise.all([
      fetch('https://api.github.com/users/saaraspakanati/repos?per_page=50&sort=updated'),
      ...externalPinned.map(url => fetch(url)),
    ]);

    const personalRepos = await personalRes.json();
    const externalRepos = await Promise.all(externalRes.map(r => r.json()));

    if (!Array.isArray(personalRepos)) throw new Error('Bad response');

    const sorted = [
      ...externalRepos,
      ...personalRepos.filter(r => pinnedFirst.includes(r.name)),
      ...personalRepos.filter(r => allowlist.includes(r.name) && !pinnedFirst.includes(r.name)),
    ];

    loading.remove();

    const langColors = {
      MATLAB: '#e16737', Python: '#3572A5', JavaScript: '#f1e05a',
      'C++': '#f34b7d', HTML: '#e44b23', Shell: '#89e051',
    };

    sorted.forEach(repo => {
      const color = langColors[repo.language] || '#888';
      const card = document.createElement('div');
      card.style.cssText = `
        background: var(--global-bg-color, #fff);
        border: 1px solid var(--global-divider-color, #e0e0e0);
        border-radius: 8px;
        padding: 1rem 1.1rem;
        display: flex;
        flex-direction: column;
        gap: 0.5rem;
      `;
      card.innerHTML = `
        <div>
          <a href="${repo.html_url}" target="_blank" rel="noopener"
             style="font-weight: 600; font-size: 0.95rem; text-decoration: none;">
            ${repo.name}
          </a>
        </div>
        <p style="font-size: 0.82rem; color: var(--global-text-color-light, #555); margin: 0; flex: 1;">
          ${descriptions[repo.name] || repo.description || '<em style="opacity:0.5">No description</em>'}
        </p>
        <div style="display: flex; align-items: center; gap: 1rem; font-size: 0.78rem; color: var(--global-text-color-light, #777); margin-top: 0.25rem;">
          ${repo.language ? `
            <span style="display:flex; align-items:center; gap: 4px;">
              <span style="width:10px; height:10px; border-radius:50%; background:${color}; display:inline-block;"></span>
              ${repo.language}
            </span>` : ''}
          ${repo.stargazers_count > 0 ? `<span>★ ${repo.stargazers_count}</span>` : ''}
          ${repo.forks_count > 0 ? `<span>⑂ ${repo.forks_count}</span>` : ''}
        </div>
      `;
      grid.appendChild(card);
    });

  } catch (e) {
    loading.textContent = 'Could not load repositories. Visit github.com/saaraspakanati directly.';
  }
})();
</script>
