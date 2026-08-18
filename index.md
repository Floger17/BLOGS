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
  <a href="https://www.instagram.com/tu-usuario" target="_blank" title="Instagram" class="social-icon-link">
    <img src="{{ '/assets/img/instagram.png' | relative_url }}" alt="Instagram" class="social-icon-img">
  </a>
</div>
