---
layout: page
title: Appunti
permalink: /blog/
---

<section>
    <h2>Tutti gli appunti</h2>
    <div class="post-list" style="margin-top: 2rem;">
        {% for post in site.posts %}
        <div style="margin-bottom: 0.8rem; display: flex; align-items: baseline;">
            <span style="opacity: 0.5; font-size: 0.9rem; margin-right: 1.5rem; min-width: 95px; flex-shrink: 0; font-family: system-ui, -apple-system, sans-serif;">
                {{ post.date | date: "%d.%m.%Y" }}
            </span>
            <a href="{{ post.url | relative_url }}" style="font-weight: 400; text-decoration: none;" class="post-link">
                {{ post.title }}
            </a>
        </div>
        {% else %}
        <p style="opacity: 0.6;">Nessun appunto pubblicato ancora.</p>
        {% endfor %}
    </div>
</section>

<style>
    .post-link:hover {
        text-decoration: underline !important;
        text-decoration-thickness: 0.1ex !important;
        text-underline-offset: 0.3ex !important;
    }

    @media (max-width: 480px) {
        .post-list > div {
            flex-direction: column !important;
            margin-bottom: 1.2rem !important;
        }
        .post-list span {
            margin-bottom: 0.2rem;
            min-width: auto !important;
        }
    }
</style>
