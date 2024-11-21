<script setup></script>

<template>
  <nav class="navbar bg-dark" data-bs-theme="dark">
    <div class="container-fluid">
      <a class="navbar-brand text-primary fw-bold">TheBoyWhoLivedAPI</a>
      <ul class="navbar-nav flex-row gap-4 align-items-center">
        <li class="nav-item">
          <a class="nav-link active" aria-current="page" href="#">Home</a>
        </li>
        <li class="nav-item">
          <a class="nav-link" href="#">Documentation</a>
        </li>
        <li class="nav-item">
          <a class="nav-link fs-4 link-primary" href="#"><i class="bi bi-github"></i></a>
        </li>
      </ul>
    </div>
  </nav>
</template>

<style scoped>
.nav-item .nav-link.active {
  text-decoration: underline;
  text-decoration-color: #eeba30;
  text-underline-offset: 4px;
}
.hover-underline-animation {
  display: inline-block;
  position: relative;
}

.hover-underline-animation::after {
  content: '';
  position: absolute;
  width: 100%;
  transform: scaleX(0);
  height: 0.125rem;
  bottom: 12%;
  left: 0;
  background-color: #2a623d;
  transform-origin: bottom right;
  transition: transform 0.25s ease-out;
}

.hover-underline-animation:hover::after {
  transform: scaleX(1);
  transform-origin: bottom left;
}
</style>
