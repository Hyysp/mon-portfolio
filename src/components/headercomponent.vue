<template>
  <header class="header">
    <nav class="navbar">
      <a href="#home" class="hover:text-green-400">HOME</a>
      <a href="#about" class="hover:text-green-400">À PROPOS DE MOI</a>
      <a href="#contact" class="hover:text-green-400">CONTACT</a>
    </nav>
  </header>
</template>

<script setup>
// plus besoin de RouterLink ici
</script>

<style scoped>
.navbar {
  display: flex;
  justify-content: space-around;
  align-items: center;
}
.navbar a {
  color: rgb(41, 202, 20);
  text-decoration: none;

  padding: 10px 20px;
  transition: color 0.3s ease;
}
.navbar a:hover {
  color: #38b2ac;
}

.header {
  background-color: #1e1e1e;
  width: 100%;
  padding: 10px 0;
  color: white;
  font-size: 1.2em;
}
.navbar {
  text-decoration: underline;
  padding: 10px 20px;
  color: rgb(41, 202, 20);
}
</style>
