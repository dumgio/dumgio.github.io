---
layout: page
title: Appunti
permalink: /blog/
---

<section>
    <div class="post-list">
        {% for post in site.posts %}
        <div class="archive-item">
            <span class="archive-date">{{ post.date | date: "%d.%m.%Y" }}</span>
            <a href="{{ post.url | relative_url }}" class="post-link">{{ post.title }}</a>
        </div>
        {% else %}
        <p class="archive-empty">Nessun appunto pubblicato ancora.</p>
        {% endfor %}
    </div>
</section>
