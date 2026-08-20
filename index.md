---
layout: default
title: Inicio
---

<!-- Carga de Montserrat (Réplica exacta de Gotham para web) -->
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@400;600;700;800&display=swap" rel="stylesheet">

<style>
  /* FONDO DE PÁGINA: ESTILO FIEL AL MANUAL DE MARCA COIGT */
  body {
    background-color: #ffffff; /* Fondo blanco limpio como la papelería del COIGT */
    /* Masa densa de isolíneas orgánicas (ladera/cumbre) naciendo en la esquina superior derecha */
    background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='1000' height='1000' viewBox='0 0 1000 1000'%3E%3Cg fill='none' stroke='%238a4939' stroke-width='1.2' opacity='0.28'%3E%3Cpath d='M1000,120 C950,110 920,80 1000,40'/%3E%3Cpath d='M1000,180 C910,160 860,110 1000,60'/%3E%3Cpath d='M1000,240 C870,210 800,140 1000,80'/%3E%3Cpath d='M1000,300 C830,260 740,170 1000,100' stroke-width='1.8' opacity='0.4'/%3E%3Cpath d='M1000,360 C790,310 680,200 1000,120'/%3E%3Cpath d='M1000,420 C750,360 620,230 1000,140'/%3E%3Cpath d='M1000,480 C710,410 560,260 1000,160'/%3E%3Cpath d='M1000,540 C670,460 500,290 1000,180' stroke-width='1.8' opacity='0.4'/%3E%3Cpath d='M1000,600 C630,510 440,320 1000,200'/%3E%3Cpath d='M1000,660 C590,560 380,350 1000,220'/%3E%3Cpath d='M1000,720 C550,610 320,380 1000,240'/%3E%3Cpath d='M1000,780 C510,660 260,410 1000,260' stroke-width='1.8' opacity='0.4'/%3E%3Cpath d='M1000,840 C470,710 200,440 1000,280'/%3E%3Cpath d='M1000,900 C430,760 140,470 1000,300'/%3E%3Cpath d='M1000,960 C390,810 80,500 1000,320'/%3E%3C/g%3E%3C/svg%3E");
    background-repeat: no-repeat;
    background-position: top right;
    background-size: 850px auto;
    background-attachment: fixed;
  }

  /* Tipografía Gotham / Montserrat */
  h1, h2, h3, .post-card-title, .badge-topografia {
    font-family: 'Montserrat', 'Gotham', -apple-system, sans-serif !important;
  }

  /* BANNER PRINCIPAL */
  .topo-hero {
    background-color: #ffffff;
    /* Isolíneas suaves de ladera coordinadas en el banner */
    background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='800' height='250' viewBox='0 0 800 250'%3E%3Cg fill='none' stroke='%238a4939' stroke-width='1' opacity='0.18'%3E%3Cpath d='M-50,220 C150,180 300,100 500,20 T850,-20'/%3E%3Cpath d='M-50,250 C170,200 330,120 530,30 T850,-10' stroke-width='1.5' opacity='0.28'/%3E%3Cpath d='M-50,280 C190,220 360,140 560,40 T850,0'/%3E%3C/g%3E%3C/svg%3E");
    background-size: cover;
    background-position: center;
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
