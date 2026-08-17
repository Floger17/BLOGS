---
layout: home
title: Inicio
---

<!-- ESTILOS DE LOS ICONOS -->
<style>
.social-icons-grid {
  display: flex;
  justify-content: center;
  align-items: center;
  gap: 1.2rem;
  margin-top: 1.5rem;
  margin-bottom: 2.5rem;
  flex-wrap: wrap;
}

.social-icon-link {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  transition: transform 0.25s ease, filter 0.25s ease;
}

.social-icon-img {
  height: 38px !important;
  width: auto !important;
  object-fit: contain;
}

.social-icon-link:hover {
  transform: scale(1.2);
  filter: brightness(1.2);
}
</style>

<!-- SECCIÓN DE REDES SOCIALES Y CONTACTO -->
<div class="social-icons-grid">
  <a href="https://www.linkedin.com/in/fabio-regolf-ari%C3%B1o-a58305328/" target="_blank" title="LinkedIn" class="social-icon-link">
    <img src="{{ '/assets/img/linkedin.png' | relative_url }}" alt="LinkedIn" class="social-icon-img">
  </a>
  <a href="https://github.com/floger17" target="_blank" title="GitHub" class="social-icon-link">
    <img src="{{ '/assets/img/github.png' | relative_url }}" alt="GitHub" class="social-icon-img">
  </a>
  <a href="https://www.coigt.com/profesional/PR00205" target="_blank" title="Precolegiado COIGT" class="social-icon-link">
    <img src="{{ '/assets/img/topography.png' | relative_url }}" alt="COIGT" class="social-icon-img">
  </a>
  <a href="https://www.instagram.com/tu-usuario" target="_blank" title="Instagram" class="social-icon-link">
    <img src="{{ '/assets/img/instagram.png' | relative_url }}" alt="Instagram" class="social-icon-img">
  </a>
</div>
