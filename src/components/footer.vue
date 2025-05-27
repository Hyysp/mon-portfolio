<template>
  <footer class="footer">
    <p>© {{ currentYear }} - Mon Portfolio. Tous droits réservés.</p>
    <div class="social-links">
      <a href="https://github.com/Hyysp" target="_blank" aria-label="GitHub">
        <img src="../assets/github.svg" alt="GitHub" />
      </a>
      <a
        href="https://www.linkedin.com/in/enzo-ragel-06a884202/"
        target="_blank"
        aria-label="LinkedIn"
      >
        <img src="../assets/linkedin.svg" alt="LinkedIn" />
      </a>
    </div>
  </footer>
</template>
<script setup>
import { ref } from 'vue'

// Obtenir l'année actuelle dynamiquement
const currentYear = ref(new Date().getFullYear())
</script>

<style scoped>
.footer {
  background: #1e1e1e;
  color: white;
  text-align: center;
  padding: 1rem 0;
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 10px;
}

.social-links {
  display: flex;
  gap: 15px;
}

.social-links img {
  width: 30px;
  height: 30px;
  transition: transform 0.3s ease-in-out;
}

.social-links img:hover {
  transform: scale(1.2);
}
</style>
