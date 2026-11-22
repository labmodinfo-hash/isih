---
layout: default
title: Academic Publications
permalink: /publications/
excerpt: "Peer-reviewed papers on semiotics of cultural heritage, cross-cultural studies, visual codes, and comparative mythology."
---
{% assign pubs = site.data.publications.publications | default: site.data.publications %}

<div class="page-header">
  <span class="eyebrow">Institutional Repository</span>
  <h1>Academic Publications</h1>
  <p>Peer-reviewed papers on semiotics of cultural heritage, cross-cultural studies, visual codes, and comparative mythology. Available for reading and citation.</p>
</div>

<div class="filters">
  <button class="filter-btn active" data-filter="all">All Works</button>
  <button class="filter-btn" data-filter="Indian & Cross-Cultural Studies">Indian & Cross-Cultural</button>
  <button class="filter-btn" data-filter="Japanese Visual Semiotics">Japanese Visual Semiotics</button>
  <button class="filter-btn" data-filter="Comparative Mythology">Comparative Mythology</button>
  <button class="filter-btn" data-filter="Theory & Methodology">Theory & Methodology</button>
  <button class="filter-btn" data-filter="Media & Communications">Media & Communications</button>
</div>

<div class="publications-list">
  {% for p in pubs %}
  <article class="pub-card" data-category="{{ p.category }}">
    <div class="pub-meta">
      <span class="pub-year">{{ p.year }}</span>
      <span class="pub-category">{{ p.category }}</span>
    </div>
    <h2>{% if p.pdf and p.pdf != "" %}<a href="{{ p.pdf }}">{{ p.title }}</a>{% else %}{{ p.title }}{% endif %}</h2>
    <p class="pub-authors">{{ p.authors }} // {{ p.source }}</p>
    {% if p.abstract %}
    <p class="pub-abstract">{{ p.abstract }}</p>
    {% endif %}
    <div class="pub-actions">
      {% if p.pdf and p.pdf != "" %}<a href="{{ p.pdf }}" class="btn">Open PDF</a>{% endif %}
      {% if p.cite and p.cite != "" %}<button class="btn-cite" data-cite="{{ p.cite | escape }}">Cite</button>{% endif %}
      {% if p.doi and p.doi != "" %}<a href="https://doi.org{{ p.doi }}" target="_blank" rel="noopener">DOI</a>{% endif %}
    </div>
  </article>
  {% endfor %}
</div>
