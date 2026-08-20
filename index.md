---
layout: default
title: Inicio
---

<!-- Carga de Montserrat (Réplica exacta de Gotham para web) -->
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@400;600;700;800&display=swap" rel="stylesheet">

<style>
  /* FONDO DE PÁGINA: ESTILO OFICIAL COIGT (Curvas en esquina superior derecha) */
  body {
    background-color: #fcfbf9; /* Tono papel técnico cálido del COIGT */
    /* Vector SVG denso naciendo desde la esquina superior derecha */
    background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='1000' height='1000' viewBox='0 0 1000 1000'%3E%3Cg fill='none' stroke='%238a4939' stroke-width='1.2' opacity='0.22'%3E%3Cpath d='M1000,0 C980,50 970,100 1000,150'/%3E%3Cpath d='M1000,0 C950,70 930,140 1000,200'/%3E%3Cpath d='M1000,0 C920,90 890,180 1000,260'/%3E%3Cpath d='M1000,0 C880,120 840,220 1000,320'/%3E%3Cpath d='M1000,0 C840,150 790,260 1000,380'/%3E%3Cpath d='M1000,0 C800,180 740,300 1000,440' stroke-width='1.8' opacity='0.35'/%3E%3Cpath d='M1000,0 C750,210 680,350 1000,500'/%3E%3Cpath d='M1000,0 C700,250 620,400 1000,570'/%3E%3Cpath d='M1000,0 C640,290 550,460 1000,640'/%3E%3Cpath d='M1000,0 C580,330 480,520 1000,720'/%3E%3Cpath d='M1000,0 C510,380 400,590 1000,810' stroke-width='1.8' opacity='0.35'/%3E%3Cpath d='M1000,0 C440,430 310,670 1000,910'/%3E%3Cpath d='M1000,0 C360,490 210,760 1000,1000'/%3E%3C/g%3E%3C/svg%3E");
    background-repeat: no-repeat;
    background-position: top right; /* Anclado a la esquina superior derecha */
    background-size: 750px auto; /* Tamaño equilibrado para no invadir el texto */
    background-attachment: fixed;
  }

  /* Tipografía Gotham / Montserrat */
  h1, h2, h3, .post-card-title, .badge-topografia {
    font-family: 'Montserrat', 'Gotham', -apple-system, sans-serif !important;
  }

  /* BANNER PRINCIPAL */
  .topo-hero {
    background-color: #ffffff;
    /* Curvas suaves siena en el hero para coordinar con el fondo */
    background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='800' height='250' viewBox='0 0 800 250'%3E%3Cg fill='none' stroke='%238a4939' stroke-width='1' opacity='0.15'%3E%3Cpath d='M-50,150 Q150,50 350,120 T750,80'/%3E%3Cpath d='M-50,120 Q150,20 350,90 T750,50'/%3E%3Cpath d='M-50,180 Q150,80 350,150 T750,110' stroke-width='1.5' opacity='0.25'/%3E%3C/g%3E%3C/svg%3E");
    background-size: cover;
    background-position: center;
    padding: 2.2rem 1.8rem;
    border-radius: 12px;
    margin-bottom: 2rem;
    border: 1px solid #e2e8f0; 
    box-shadow: 0 10px 15px -3px rgba(15, 23, 42, 0.04), 0 4px 6px -2px rgba(15, 23, 42, 0.02);
  }

  .topo-hero h1 {
    color: #1e293b !important;
    font-weight: 800;
    font-size: 2rem;
    margin: 0 0 0.4rem 0;
  }

  /* Badge adaptado a los tonos siena/topográficos */
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
