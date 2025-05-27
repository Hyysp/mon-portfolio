<script setup>
import Header from './components/headercomponent.vue'
import Footer from './components/footer.vue'
import { RouterView } from 'vue-router'
</script>
<template>
  <Header />
  <main>
    <RouterView />
  </main>
  <Footer />
</template>
<style scoped>
main {
  background-color: rgb(0, 0, 0);
}

body {
  margin: 0%;
  padding: 0%;
  box-sizing: border-box;
}

html {
  scroll-behavior: smooth;
}
</style>
