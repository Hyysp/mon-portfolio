<template>
  <div class="not-found">
    <h1>404</h1>
    <p>Oups ! Cette page n'existe pas.</p>
    <img src="../assets/404.png" alt="Erreur 404" />
  </div>
  <div>
    <RouterLink to="/" class="home-button">Retour à l'accueil</RouterLink>
  </div>
</template>

<script setup>
import { RouterLink } from 'vue-router'
</script>

<style scoped>
.not-found {
  text-align: center;
  padding: 5rem 1rem;
  color: white;
}
.home-button {
  display: inline-block;
  padding: 0.7rem 1.5rem;
  background-color: green;
  color: white;
  text-decoration: none;
  border-radius: 8px;
  transition: background 0.3s ease;
}
.home-button:hover {
  background-color: limegreen;
}
</style>
