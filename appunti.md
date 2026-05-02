---
layout: page
title: Archivio Appunti
permalink: /blog/
---

<div class="category-filter" style="margin-bottom: 3rem; font-family: var(--body-font);">
  <span style="opacity: 0.5; margin-right: 1rem; font-size: 0.9rem;">Filtra per:</span>
  <button class="filter-btn active" onclick="filterCategory('all')">Tutti</button>
  {% assign categories = site.posts | map: 'category' | uniq | compact %}
  {% for category in categories %}
    <button class="filter-btn" onclick="filterCategory('{{ category | slugify }}')">{{ category | capitalize }}</button>
  {% endfor %}
</div>

<div class="post-list">
  {% for post in site.posts %}
  <div class="post-item filterable-post" data-category="{{ post.category | slugify | default: 'none' }}">
    <span class="post-date">
      {{ post.date | date: "%-d" }}
      {% assign m = post.date | date: "%-m" | minus: 1 %}
      {% case m %}
        {% when 0 %}gennaio{% when 1 %}febbraio{% when 2 %}marzo{% when 3 %}aprile
        {% when 4 %}maggio{% when 5 %}giugno{% when 6 %}luglio{% when 7 %}agosto
        {% when 8 %}settembre{% when 9 %}ottobre{% when 10 %}novembre{% when 11 %}dicembre
      {% endcase %}
      {{ post.date | date: "%Y" }}
    </span>
    <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
  </div>
  {% else %}
  <p>In attesa del primo appunto.</p>
  {% endfor %}
</div>

<script>
function filterCategory(category) {
  // Aggiorna i bottoni
  document.querySelectorAll('.filter-btn').forEach(btn => {
    btn.classList.remove('active');
  });
  event.target.classList.add('active');

  // Filtra i post
  const posts = document.querySelectorAll('.filterable-post');
  posts.forEach(post => {
    if (category === 'all' || post.getAttribute('data-category') === category) {
      post.style.display = 'flex';
    } else {
      post.style.display = 'none';
    }
  });
}
</script>

<style>
  .filter-btn {
    background: none;
    border: none;
    color: var(--text-color);
    opacity: 0.5;
    cursor: pointer;
    margin-right: 1rem;
    font-size: 0.9rem;
    padding: 0;
    text-decoration: none;
    transition: opacity 0.2s;
  }
  .filter-btn:hover, .filter-btn.active {
    opacity: 1;
    text-decoration: underline;
    text-underline-offset: 4px;
  }
  .post-item {
    transition: all 0.3s ease;
  }
</style>
