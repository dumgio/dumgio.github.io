---
layout: default
title: Appunti
permalink: /blog/
---

<section>
    <h2>Tutti gli appunti</h2>
    <div class="post-list" style="margin-top: 2rem;">
        {% for post in site.posts %}
        <a href="{{ post.url }}" class="post-item" style="text-decoration: none; display: block; margin-bottom: 1.5rem;">
            <span class="post-date" style="font-size: 0.8rem; color: var(--accent); margin-right: 15px; font-family: monospace;">
                {{ post.date | date: "%d.%m.%Y" }}
            </span>
            <strong style="color: var(--fg); font-size: 1.1rem;">{{ post.title }}</strong>
        </a>
        {% else %}
        <p class="text-block" style="color: var(--accent);">Nessun appunto pubblicato ancora.</p>
        {% endfor %}
    </div>
</section>
