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

  /* PROTECCIÓN GLOBAL DE IMÁGENES Y TEXTO */
  img, .logo-shield, .post-card-image-wrapper {
    -webkit-user-select: none !important;
    -moz-user-select: none !important;
    -ms-user-select: none !important;
    user-select: none !important;
    -webkit-user-drag: none !important;
  }

  /* BLOQUEO EN IMPRESIÓN Y PDF */
  @media print {
    html, body {
      display: none !important;
    }
  }

  /* CONTENEDOR Y ESCUDO PROTECTOR PARA EL LOGO */
  .logo-protected-container {
    position: relative;
    display: inline-block;
    flex-shrink: 0;
  }

  .logo-img-protected {
    height: 110px;
    width: auto; /* Mantiene la proporción original sin achatar */
    object-fit: contain;
    filter: drop-shadow(0 2px 4px rgba(0,0,0,0.1));
    display: block;
    pointer-events: none;
  }

  /* ESCUDO DE PROTECCIÓN Y MARCA DE AGUA SOBRE EL LOGO */
  .logo-shield {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background: rgba(255, 255, 255, 0.01); /* Transparente para interactividad */
    z-index: 10;
  }

  /* MARCA DE AGUA ANTI-CAPTURA EN EL LOGO */
  .logo-protected-container::after {
    content: "© FRA • NO COPIAR";
    position: absolute;
    bottom: 2px;
    right: 2px;
    font-size: 0.55rem;
    font-weight: 800;
    color: rgba(138, 73, 57, 0.6);
    background: rgba(255, 255, 255, 0.85);
    padding: 1px 4px;
    border-radius: 3px;
    pointer-events: none;
    letter-spacing: 0.5px;
    border: 1px solid rgba(138, 73, 57, 0.3);
    z-index: 11;
  }

  /* BANNER PRINCIPAL */
  .topo-hero {
    background-color: #ffffff;
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

<!-- BANNER CON LOGOTIPO Y CURVAS DE NIVEL -->
<div class="topo-hero">
  <div style="display: flex; align-items: center; justify-content: space-between; gap: 1.5rem; flex-wrap: wrap-reverse;">
    <div style="flex: 1; min-width: 250px;">
      <span class="badge-topografia">Geomática & Topografía</span>
      <h1>Cuaderno de Campo</h1>
      <p>Divulgación técnica, prácticas y reflexiones de un estudiante precolegiado.</p>
    </div>
    <div style="text-align: center;">
      <!-- ESTRUCTURA PROTEGIDA PARA TU LOGO CON PROPORCIONES ORIGINALES -->
      <div class="logo-protected-container">
        <img src="{{ '/assets/img/MARCA_PERSONAL_BYN.png' | relative_url }}" alt="Logo FRA" class="logo-img-protected" draggable="false">
        <div class="logo-shield"></div>
      </div>
    </div>
  </div>
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

<!-- SCRIPT DE SEGURIDAD GENERAL -->
<script>
  // Bloqueo de Clic Derecho
  document.addEventListener('contextmenu', function(e) {
    e.preventDefault();
  }, false);

  // Impedir inicio de arrastre de elementos
  document.addEventListener('dragstart', function(e) {
    e.preventDefault();
  }, false);

  // Bloqueo de Atajos Teclado (Ctrl+S, F12, Ctrl+U, etc.)
  document.addEventListener('keydown', function(e) {
    if (
      (e.ctrlKey || e.metaKey) && (e.key === 's' || e.key === 'u' || e.key === 'S' || e.key === 'U') ||
      e.key === 'F12' ||
      ((e.ctrlKey || e.metaKey) && e.shiftKey && (e.key === 'I' || e.key === 'i' || e.key === 'J' || e.key === 'j' || e.key === 'C' || e.key === 'c'))
    ) {
      e.preventDefault();
    }
  }, false);
</script>
