---
layout: post
title: "Completare la sequenza"
date: 2026-06-01
permalink: /appunti/completare-la-sequenza/
---
Di recente Andrej Karpathy, uno dei ricercatori più noti nel campo dell'intelligenza artificiale, ha pubblicato un codice di circa duecento righe che implementa da zero un modello linguistico. Nessuna libreria, nessun framework: solo la logica essenziale di come funziona un sistema come ChatGPT.

Il principio è semplice: il modello impara quali lettere tendono a seguire altre lettere. Niente parole, niente significati. Solo probabilità.

Eppure il risultato è linguaggio, o qualcosa che gli assomiglia abbastanza da ingannare.

La domanda che quel codice lascia aperta è scomoda: se il linguaggio si riduce a sequenze di probabilità, quanto spesso anche noi parliamo così? Per abitudine, per inerzia, per quello che viene naturalmente dopo nella sequenza?

La differenza è che noi possiamo fermarci. Cercare la parola giusta, o non dirla. La macchina no. Deve sempre completare.

---
Riferimento: Andrej Karpathy, <em>microGPT</em> — <a href="https://gist.github.com/karpathy/8627fe009c40f57531cb18360106ce95">gist.github.com/karpathy</a>