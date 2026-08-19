---
layout: default
title: Inicio
---

<!-- Carga de Montserrat (Réplica exacta de Gotham para web) -->
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@400;600;700;800&display=swap" rel="stylesheet">

<style>
  /* FONDO DE PÁGINA CON CURVAS DE NIVEL */
  body {
    background-color: #f8fafc;
    background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='800' height='400' viewBox='0 0 800 400'%3E%3Cpath d='M-100,250 Q200,100 500,220 T1100,180' fill='none' stroke='rgba(148, 163, 184, 0.25)' stroke-width='1.5'/%3E%3Cpath d='M-100,200 Q200,50 500,170 T1100,130' fill='none' stroke='rgba(148, 163, 184, 0.18)' stroke-width='1'/%3E%3Cpath d='M-100,150 Q200,0 500,120 T1100,80' fill='none' stroke='rgba(148, 163, 184, 0.12)' stroke-width='1'/%3E%3Cpath d='M-100,300 Q200,150 500,270 T1100,230' fill='none' stroke='rgba(37, 99, 235, 0.2)' stroke-width='1.5'/%3E%3C/svg%3E");
    background-size: cover;
    background-attachment: fixed;
  }

  /* Tipografía Gotham / Montserrat */
  h1, h2, h3, .post-card-title, .badge-topografia {
    font-family: 'Montserrat', 'Gotham', -apple-system, sans-serif !important;
  }

  /* Banner Claro Estilo Informe Técnico */
  .topo-hero {
    background-color: #ffffff;
    background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='600' height='200' viewBox='0 0 600 200'%3E%3Cpath d='M-50,150 Q150,50 350,120 T750,80' fill='none' stroke='rgba(148,163,184,0.3)' stroke-width='1.5'/%3E%3Cpath d='M-50,120 Q150,20 350,90 T750,50' fill='none' stroke='rgba(148,163,184,0.2)' stroke-width='1'/%3E%3Cpath d='M-50,180 Q150,80 350,150 T750,110' fill='none' stroke='rgba(37,99,235,0.5)' stroke-width='2'/%3E%3C/svg%3E");
    background-size: cover;
    padding: 2.2rem 1.8rem;
    border-radius: 10px;
    margin-bottom: 2rem;
    border: 1px solid #cbd5e1;
    box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.03);
  }

  .topo-hero h1 {
    color: #0f172a !important;
    font-weight: 800;
    font-size: 2rem;
    margin: 0 0 0.4rem 0;
  }

  .badge-topografia {
    display: inline-block;
    background: rgba(37, 99, 235, 0.1);
    border: 1px solid rgba(37, 99, 235, 0.3);
    color: #2563eb;
    font-size: 0.75rem;
    font-weight: 700;
    padding: 3px 10px;
    border-radius: 15px;
    text-transform: uppercase;
    letter-spacing: 1px;
    margin-bottom: 0.8rem;
  }

  .topo-hero p {
    color: #475569;
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
    box-shadow: 0 12px 20px -5px rgba(15, 23, 42, 0.12);
    border-color: #2563eb;
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
