<script setup>
import { RouterLink, RouterView } from 'vue-router'


</script>

<template>
  <div class="container">
    <div class="row">
      <div class="col my-4 fs-5">
        <i class="bi bi-send-fill"></i>+62 814-550-952-74
      </div>
      <div class="col my-4 text-end fs-5">
        <i class="bi bi-facebook"></i>
        <i class="bi bi-instagram mx-3"></i>
        <i class="bi bi-twitter"></i>
        
      </div>
    </div>
  </div>
  <nav class="navbar navbar-expand-lg" data-bs-theme="dark">
    <div class="container-fluid">
      <a class="navbar-brand ms-5" href="#">
        <img src="/logo.png" alt="" width="200px">
      </a>
      <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNavAltMarkup" aria-controls="navbarNavAltMarkup" aria-expanded="false" aria-label="Toggle navigation">
        <span class="navbar-toggler-icon"></span>
      </button>
      <div class="collapse navbar-collapse" id="navbarNavAltMarkup">
        <div class="navbar-nav ms-auto me-3">
          <RouterLink :to="{ name: 'home' }" :class="[
            { 'active': $route.name === 'home','nav-link': true },]">Home</RouterLink>
          <RouterLink :to="{ name: 'about' }" :class="[
            { 'active': $route.name === 'about','nav-link me-4': true },]">About</RouterLink>
        </div>
      </div>
    </div>
  </nav>
  <RouterView />
</template>

<style scoped>
nav {
  background-color: rgb(0, 217, 255);
  font-weight: bold;
}
</style>
