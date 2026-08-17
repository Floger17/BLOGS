---
layout: home
title: Inicio
---
<style>
/* Contenedor de iconos */
.social-icons-grid {
  display: flex;
  justify-content: center;
  align-items: center;
  gap: 1.2rem;
  margin-top: 1.2rem;
  flex-wrap: wrap;
}

/* Enlace individual */
.social-icon-link {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  transition: transform 0.25s ease, filter 0.25s ease;
}

/* REGLA CLAVE: Altura fija e imagen proporcional */
.social-icon-img {
  height: 38px !important;  /* Define la altura idéntica para todos los logos */
  width: auto !important;   /* El ancho se adapta solo para no deformar la imagen */
  object-fit: contain;      /* Mantiene la proporción perfecta */
}

/* Efecto hover al pasar el ratón */
.social-icon-link:hover {
  transform: scale(1.2);
  filter: brightness(1.2);
}
</style>

<!-- SECCIÓN DE REDES SOCIALES -->
<div class="social-icons-grid">

  <a href="https://www.linkedin.com/in/tu-perfil" target="_blank" title="LinkedIn" class="social-icon-link">
    <img src="{{ '/assets/img/linkedin.png' | relative_url }}" alt="LinkedIn" class="social-icon-img">
  </a>

  <a href="https://www.coigt.com/" target="_blank" title="Precolegiado COIGT" class="social-icon-link">
    <img src="{{ '/assets/img/colegio.png' | relative_url }}" alt="COIGT" class="social-icon-img">
  </a>

  <a href="https://github.com/floger17" target="_blank" title="GitHub" class="social-icon-link">
    <img src="{{ '/assets/img/github.png' | relative_url }}" alt="GitHub" class="social-icon-img">
  </a>

  <a href="https://www.instagram.com/tu-usuario" target="_blank" title="Instagram" class="social-icon-link">
    <img src="{{ '/assets/img/instagram.png' | relative_url }}" alt="Instagram" class="social-icon-img">
  </a>

</div>
