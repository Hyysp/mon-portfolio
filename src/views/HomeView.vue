<template>
  <section id="home" class="section">
    <img src="../assets/chemise.jpg" alt="Photo de profil" class="profile-image" />
    <p class="text">Bienvenue sur mon portfolio</p>
  </section>

  <section id="about" class="about-section">
    <h2>À propos de moi</h2>
    <p>
      Je m'appelle <strong>Enzo Ragel</strong> et j'étudie le <strong>développement web</strong> au
      <strong>Centre Européen de Formation</strong>.<br /><br />
      Passionné d'informatique depuis toujours, j’ai choisi cette voie car elle allie logique,
      créativité et innovation des aspects qui me motivent chaque jour à progresser.<br /><br />
      Je suis quelqu’un de <strong>ponctuel</strong>, <strong>curieux</strong>,
      <strong>créatif</strong>, et particulièrement <strong>pointilleux</strong> sur la qualité de
      ce que je produis. J’accorde beaucoup d’importance au détail et à la cohérence de mes
      projets.<br /><br />
      Mon objectif est de travailler dans le domaine du développement web, et continuer à évoluer
      dans un environnement stimulant.<br /><br />
      En dehors du code, je suis un grand passionné de <strong>jeux vidéo</strong>, de
      <strong>musculation</strong> et de <strong>football</strong>, qui m’apportent équilibre,
      discipline et esprit d’équipe.
    </p>
  </section>

  <section class="projects">
    <h2>Mes réalisations</h2>

    <div class="project" @click="openModal('cahier')">
      <h3>Cahier des charges</h3>
      <img src="/src/assets/projet1.jpg" alt="projet1" />
    </div>

    <div class="project" @click="openModal('commentaire')">
      <h3>Dynamiser un espace commentaire</h3>
      <img src="/src/assets/projet2.jpg" alt="projet2" />
    </div>
  </section>

  <!-- Modale -->
  <div v-if="activeModal" class="modal-overlay" @click.self="closeModal">
    <div class="modal-content">
      <h2>{{ modalTitle }}</h2>
      <p>{{ modalText }}</p>
      <button @click="closeModal">Fermer</button>
    </div>
  </div>

  <section id="contact" class="contact-section">
    <h2>Contactez-moi</h2>
    <form @submit.prevent="submitForm" class="contact-form">
      <input type="text" v-model="name" placeholder="Votre nom" required />
      <input type="email" v-model="email" placeholder="Votre e-mail" required />
      <textarea v-model="message" placeholder="Votre message" required></textarea>
      <button type="submit">Envoyer</button>
    </form>
  </section>
</template>

<script setup lang="ts">
import { ref, computed } from 'vue'

const activeModal = ref<string | null>(null)

function openModal(name: string) {
  activeModal.value = name
}

function closeModal() {
  activeModal.value = null
}

const modalTitle = computed(() => {
  switch (activeModal.value) {
    case 'cahier':
      return 'Cahier des charges'
    case 'commentaire':
      return 'Dynamiser un espace commentaire'
    default:
      return ''
  }
})

const modalText = computed(() => {
  switch (activeModal.value) {
    case 'cahier':
      return 'Ce projet consistait à créer un cahier des charges complet pour un site e-commerce fictif.'
    case 'commentaire':
      return 'Ce projet avait pour but de rendre interactif un système de commentaires avec JavaScript.'
    default:
      return ''
  }
})

const name = ref('')
const email = ref('')
const message = ref('')

function submitForm() {
  alert(`Merci ${name.value}, votre message a bien été envoyé !`)
  // Optionnel : choisir un service d'envoi de formulaire ici
  name.value = ''
  email.value = ''
  message.value = ''
}
</script>

<style scoped>
.profile-image {
  width: 150px;
  height: 150px;
  object-fit: cover;
  border-radius: 50%; /* rend l'image ronde */
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.5); /* ombre autour de l'image */
  margin-top: -50px; /* déplace l'image vers le haut */
}
.section {
  display: flex;
  flex-direction: column;
  align-items: center;
  padding: 4rem 0;
}
.text {
  color: rgb(41, 202, 20);
  margin-top: 1rem;
  font-size: 1.2rem;
}

.about-section {
  background-color: #111;
  color: rgb(41, 202, 20);
  padding: 4rem 2rem;
  max-width: 800px;
  margin: 4rem auto;
  text-align: left;
  border-radius: 10px;
  line-height: 1.7;
  font-size: 1.1rem;
  box-shadow: 0 0 15px rgba(0, 0, 0, 0.4);
}

.about-section h2 {
  font-size: 2rem;
  margin-bottom: 1.5rem;
  color: #42b883;
  text-align: center;
}

.about-section h2 {
  font-size: 2rem;
  margin-bottom: 1rem;
  color: #42b883;
}

.about-section p {
  font-size: 1.1rem;
  line-height: 1.6;
}
</style>

<style>
.modal {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.6);
  display: flex;
  justify-content: center;
  align-items: center;
}
.modal-content {
  background: white;
  padding: 20px;
  border-radius: 10px;
}

.projects {
  text-align: center;
  padding: 2rem;
}

.project {
  cursor: pointer;
  margin-bottom: 1rem;
}

.project img {
  width: 300px;
  transition: transform 0.3s;
}
.project img:hover {
  transform: scale(1.05);
}

.modal-overlay {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.7);
  display: flex;
  justify-content: center;
  align-items: center;
  z-index: 999;
}

.modal-content {
  background: #1e1e1e;
  color: rgb(41, 202, 20);
  padding: 2rem;
  border-radius: 10px;
  width: 90%;
  max-width: 500px;
  text-align: left;
}

.modal-content button {
  margin-top: 1rem;
  padding: 0.5rem 1rem;
  background: rgb(41, 202, 20);
  border: none;
  color: rgb(0, 0, 0);
  border-radius: 5px;
  cursor: pointer;
}

.contact-section {
  text-align: center;
  padding: 3rem 2rem;
  background-color: #111;
  color: white;
}

.contact-form {
  display: flex;
  flex-direction: column;
  max-width: 500px;
  margin: 0 auto;
  gap: 1rem;
}

.contact-form input,
.contact-form textarea {
  padding: 0.8rem;
  border-radius: 6px;
  border: none;
  background: #222;
  color: white;
}

.contact-form button {
  background-color: green;
  color: white;
  padding: 0.7rem;
  border: none;
  border-radius: 6px;
  cursor: pointer;
  transition: background 0.3s ease;
}

.contact-form button:hover {
  background-color: limegreen;
}

.project img {
  width: 300px;
  transition: box-shadow 0.3s ease;
}

.project img:hover {
  box-shadow: 5px 5px 15px rgb(255, 255, 255); /* bas + droite */
}
</style>
