---
layout: default
title: Appunti
permalink: /blog/
---

<section>
    <h2>Tutti gli appunti</h2>
    <div class="post-list" style="margin-top: 2rem;">
        {% for post in site.posts %}
        <a href="{{ post.url }}" class="post-item">
            <span class="post-date">
                {{ post.date | date: "%d.%m.%Y" }}
            </span>
            <span class="post-title-link">
                {{ post.title }}
            </span>
        </a>
        {% else %}
        <p class="text-block" style="color: var(--accent);">Nessun appunto pubblicato ancora.</p>
        {% endfor %}
    </div>
</section>

<style>
    /* Contenitore del singolo elemento della lista */
    .post-item {
        text-decoration: none;
        display: flex;
        align-items: baseline;
        margin-bottom: 1.5rem;
        transition: all 0.2s ease;
    }

    /* Stile della data (monospaziata per ordine visivo) */
    .post-date {
        font-size: 0.8rem;
        color: var(--accent);
        margin-right: 15px;
        font-family: monospace;
        flex-shrink: 0; /* Impedisce alla data di rimpicciolirsi su schermi piccoli */
    }

    /* Stile del titolo con sottolineatura elegante */
    .post-title-link {
        font-weight: 500;
        color: var(--fg);
        font-size: 1.1rem;
        text-decoration: underline;
        text-decoration-color: var(--border); /* Linea grigio chiaro */
        text-underline-offset: 4px; /* Distanza tra testo e linea */
        transition: all 0.2s ease;
    }

    /* Effetto al passaggio del mouse */
    .post-item:hover .post-title-link {
        text-decoration-color: var(--accent);
        color: var(--accent);
    }

    /* Adattamento per schermi molto piccoli */
    @media (max-width: 480px) {
        .post-item {
            flex-direction: column;
            gap: 0.3rem;
        }
        .post-date {
            margin-right: 0;
        }
    }
</style>
