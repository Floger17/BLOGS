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
  h1, h2, h3, .post-card-title, .badge-topografia {
    font-family: 'Montserrat', 'Gotham', -apple-system, sans-serif !important;
  }

 /* BANNER PRINCIPAL */
  .topo-hero {
    background-color: #ffffff;
    /* Red de isolíneas orgánicas densas en color siena (#8a4939) */
    background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='900' height='300' viewBox='0 0 900 300'%3E%3Cg fill='none' stroke='%238a4939' stroke-width='1.2' opacity='0.25'%3E%3Cpath d='M900,0 C820,30 780,90 900,140'/%3E%3Cpath d='M900,0 C760,50 710,120 900,180'/%3E%3Cpath d='M900,0 C700,70 640,150 900,220' stroke-width='1.8' opacity='0.4'/%3E%3Cpath d='M900,0 C640,90 570,180 900,260'/%3E%3Cpath d='M900,0 C580,110 500,210 900,300'/%3E%3Cpath d='M900,0 C520,130 430,240 850,300'/%3E%3Cpath d='M900,0 C460,150 360,270 750,300' stroke-width='1.8' opacity='0.4'/%3E%3Cpath d='M900,0 C400,170 290,290 650,300'/%3E%3Cpath d='M900,0 C340,190 220,300 550,300'/%3E%3Cpath d='M900,0 C280,210 150,300 450,300'/%3E%3Cpath d='M900,0 C220,230 80,300 350,300' stroke-width='1.8' opacity='0.4'/%3E%3Cpath d='M900,0 C160,250 10,300 250,300'/%3E%3C/g%3E%3C/svg%3E");
    background-repeat: no-repeat;
    background-position: top right;
    background-size: contain;
    padding: 2.2rem 1.8rem;
    border-radius: 12px;
    margin-bottom: 2rem;
    border: 1px solid #e2e8f0; 
    box-shadow: 0 10px 15px -3px rgba(15, 23, 42, 0.04), 0 4px 6px -2px rgba(15, 23, 42, 0.02);
  }

  .topo-hero h1 {
    color: #0f172a !important;
    font-weight: 800;
    font-size: 2rem;
    margin: 0 0 0.4rem 0;
  }

  /* Badge adaptado a la estética topográfica siena */
  .badge-topografia {
    display: inline-block;
    background: #fdf6f0;
    border: 1px solid #f5d0c5;
    color: #8a4939;
    font-size: 0.75rem;
    font-weight: 700;
    padding: 3px 10px;
    border-radius: 15px;
    text-transform: uppercase;
    letter-spacing: 1px;
    margin-bottom: 0.8rem;
  }

  .topo-hero p {
    color: #334155;
    margin: 0;
  }

  /* REJILLA DE TARJETAS (GRID) */
  .posts-grid {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 1.5rem;
    margin-top: 1rem;
  }

  @media screen and (max-width: 650px) {
    .posts-grid {
      grid-template-columns: 1fr !important;
    }
  }

  /* DISEÑO DE CADA TARJETA */
  .post-card {
    background: #ffffff;
    border: 1px solid #e2e8f0;
    border-radius: 10px;
    overflow: hidden;
    display: flex;
    flex-direction: column;
    text-decoration: none !important;
    transition: transform 0.25s ease, box-shadow 0.25s ease, border-color 0.25s ease;
  }

  .post-card:hover {
    transform: translateY(-5px);
    box-shadow: 0 12px 20px -5px rgba(15, 23, 42, 0.1);
    border-color: #8a4939;
  }

  .post-card-image-wrapper {
    width: 100%;
    height: 180px;
    overflow: hidden;
    background-color: #0f172a;
    position: relative;
  }

  .post-card-image {
    width: 100%;
    height: 100%;
    object-fit: cover;
    transition: transform 0.3s ease;
  }

  .post-card:hover .post-card-image {
    transform: scale(1.05);
  }

  .post-card-body {
    padding: 1.2rem;
    display: flex;
    flex-direction: column;
    flex-grow: 1;
    justify-content: space-between;
  }

  .post-card-date {
    font-size: 0.75rem;
    color: #64748b;
    font-weight: 700;
    text-transform: uppercase;
    letter-spacing: 0.5px;
    margin-bottom: 0.4rem;
  }

  .post-card-title {
    font-size: 1.15rem;
    font-weight: 700;
    color: #0f172a;
    margin: 0;
    line-height: 1.35;
  }
</style>

<!-- BANNER CON CURVAS DE NIVEL -->
<div class="topo-hero">
  <span class="badge-topografia">Geomática & Topografía</span>
  <h1>Cuaderno de Campo</h1>
  <p>Divulgación técnica, prácticas y reflexiones de un estudiante precolegiado.</p>
</div>

<h2>Publicaciones</h2>

<!-- REJILLA DE TARJETAS CON FOTO -->
<div class="posts-grid">
  {% for post in site.posts %}
    <a href="{{ post.url | relative_url }}" class="post-card">
      <div class="post-card-image-wrapper">
        {% if post.image %}
          <img src="{{ post.image | relative_url }}" alt="{{ post.title }}" class="post-card-image">
        {% else %}
          <img src="https://images.unsplash.com/photo-1524661135-423995f22d0b?auto=format&fit=crop&w=600&q=80" alt="Topografía" class="post-card-image">
        {% endif %}
      </div>
      <div class="post-card-body">
        <div>
          <span class="post-card-date">{{ post.date | date: "%b %-d, %Y" }}</span>
          <h3 class="post-card-title">{{ post.title }}</h3>
        </div>
      </div>
    </a>
  {% endfor %}
</div>
