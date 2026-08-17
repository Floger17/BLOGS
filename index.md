---
layout: home
title: Inicio
---
<style>
/* Contenedor de iconos al final de la página */
.social-icons-grid {
  display: flex;
  justify-content: center;
  align-items: center;
  gap: 1.2rem;
  margin-top: 2.5rem;    /* Espacio respecto al contenido de arriba */
  margin-bottom: 1.5rem; /* Margen inferior de cortesía */
  flex-wrap: wrap;
}

/* Enlace individual */
.social-icon-link {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  transition: transform 0.25s ease, filter 0.25s ease;
}

/* Altura fija idéntica para todos los logos */
.social-icon-img {
  height: 38px !important;
  width: auto !important;
  object-fit: contain;
}

/* Efecto hover al pasar el ratón */
.social-icon-link:hover {
  transform: scale(1.2);
  filter: brightness(1.2);
}
</style>

<!-- SECCIÓN DE REDES SOCIALES Y CONTACTO -->
<div class="social-icons-grid">

  <!-- 1. LINKEDIN -->
  <a href="https://www.linkedin.com/in/tu-perfil" target="_blank" title="Perfil Profesional en LinkedIn" class="social-icon-link">
    <img src="{{ '/assets/img/linkedin.png' | relative_url }}" alt="LinkedIn" class="social-icon-img">
  </a>

  <!-- 2. GITHUB -->
  <a href="https://github.com/floger17" target="_blank" title="Repositorio GitHub" class="social-icon-link">
    <img src="{{ '/assets/img/github.png' | relative_url }}" alt="GitHub" class="social-icon-img">
  </a>

  <!-- 3. PRECOLEGIADO / VÍNCULO PROFESIONAL (Icono neutro de topografía) -->
  <a href="https://www.coigt.com/" target="_blank" title="Precolegiado COIGT" class="social-icon-link">
    <img src="{{ '/assets/img/topography.png' | relative_url }}" alt="Precolegiado COIGT" class="social-icon-img">
  </a>

  <!-- 4. INSTAGRAM (Opcional) -->
  <a href="https://www.instagram.com/tu-usuario" target="_blank" title="Instagram" class="social-icon-link">
    <img src="{{ '/assets/img/instagram.png' | relative_url }}" alt="Instagram" class="social-icon-img">
  </a>

</div>
