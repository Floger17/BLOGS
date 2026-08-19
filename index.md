---
layout: default
title: Inicio
---

<!-- Carga de Montserrat (Réplica exacta de Gotham para web) -->
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@400;600;700;800&display=swap" rel="stylesheet">

<style>
  /* Tipografía Gotham / Montserrat */
  h1, h2, h3, .post-title-link, .badge-topografia {
    font-family: 'Montserrat', 'Gotham', -apple-system, sans-serif !important;
  }

  /* Banner estilo Plano Topográfico */
  .topo-hero {
    background-color: #0f172a;
    background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='600' height='200' viewBox='0 0 600 200'%3E%3Cpath d='M-50,150 Q150,50 350,120 T750,80' fill='none' stroke='rgba(255,255,255,0.12)' stroke-width='1.5'/%3E%3Cpath d='M-50,120 Q150,20 350,90 T750,50' fill='none' stroke='rgba(255,255,255,0.08)' stroke-width='1'/%3E%3Cpath d='M-50,90 Q150,-10 350,60 T750,20' fill='none' stroke='rgba(255,255,255,0.05)' stroke-width='1'/%3E%3Cpath d='M-50,180 Q150,80 350,150 T750,110' fill='none' stroke='rgba(37,99,235,0.4)' stroke-width='2'/%3E%3C/svg%3E");
    background-size: cover;
    color: #ffffff;
    padding: 2.2rem 1.8rem;
    border-radius: 10px;
    margin-bottom: 2rem;
  }

  .topo-hero h1 {
    color: #ffffff !important;
    font-weight: 800;
    font-size: 2rem;
    margin: 0 0 0.4rem 0;
  }

  .badge-topografia {
    display: inline-block;
    background: rgba(37, 99, 235, 0.3);
    border: 1px solid rgba(147, 197, 253, 0.4);
    color: #93c5fd;
    font-size: 0.75rem;
    font-weight: 700;
    padding: 3px 10px;
    border-radius: 15px;
    text-transform: uppercase;
    letter-spacing: 1px;
    margin-bottom: 0.8rem;
  }

  .topo-hero p {
    color: #cbd5e1;
    margin: 0;
  }

  /* Grid de Tarjetas para las Entradas */
  .posts-grid {
    display: flex;
    flex-direction: column;
    gap: 1rem;
  }

  .post-card {
    background: #ffffff;
    border: 1px solid #e2e8f0;
    border-left: 5px solid #2563eb; /* Color azul plano */
    border-radius: 6px;
    padding: 1.2rem 1.4rem;
    transition: all 0.2s ease;
  }

  .post-card:hover {
    transform: translateY(-2px);
    box-shadow: 0 8px 15px rgba(0,0,0,0.06);
    border-left-color: #0f172a; /* Cambia a oscuro al pasar el ratón */
  }

  .post-meta-date {
    font-size: 0.8rem;
    color: #64748b;
    font-weight: 600;
    text-transform: uppercase;
    display: block;
    margin-bottom: 0.2rem;
  }

  .post-title-link {
    font-size: 1.25rem;
    font-weight: 700;
    color: #0f172a !important;
    text-decoration: none !important;
  }

  .post-title-link:hover {
    color: #2563eb !important;
  }
</style>

<!-- BANNER CON CURVAS DE NIVEL -->
<div class="topo-hero">
  <span class="badge-topografia">Geomática & Topografía</span>
  <h1>Cuaderno de Campo</h1>
  <p>Divulgación técnica, prácticas y reflexiones de un estudiante precolegiado.</p>
</div>

<h2>Publicaciones</h2>

<!-- LISTADO DE POSTS EN TARJETAS -->
<div class="posts-grid">
  {% for post in site.posts %}
    <div class="post-card">
      <span class="post-meta-date">{{ post.date | date: "%b %-d, %Y" }}</span>
      <a class="post-title-link" href="{{ post.url | relative_url }}">
        {{ post.title }}
      </a>
    </div>
  {% endfor %}
</div>
