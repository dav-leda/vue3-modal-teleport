
<template>
  <main>

    <h1>Ventana Modal con Vue 3 + Vite</h1>

    <button
      @click="showModal = true"
    >Abrir Modal</button>

    <ModalWindow
      :showModal="showModal" 
      @close-modal="showModal = false"
    >
      <template #header>
        <h2>Cómo cerrar una ventana modal</h2>
        <br>
        <p>Para cerrar esta ventana modal toque el botón que dice "Cerrar".</p>
        
        <img 
          src="./assets/images/vintage-touchscreen.jpg" 
          alt="vintage touchscreen"
        />
      </template>

      <template #footer>
        <button 
          @click="showModal = false"
          style="float:right;"
        >Cerrar</button>
      </template>

    </ModalWindow>

  </main>
</template>

<script setup lang="ts">

import ModalWindow from './components/ModalWindow.vue'

import { ref } from 'vue'

const showModal = ref<boolean>(false)

const openModal = () => showModal.value = true

</script>

<style scoped>

main {
  margin: 1rem;
  padding: 2rem;
  border: 1px solid;
  min-height: 95vh;
  text-align: center;
}

button {
  margin-top: 1rem;
  padding: 0.6rem 1.2rem;
  background-color: navy;
  color: snow;
  border-radius: 5px;
  border: none;
  cursor: pointer;
}

img {
  width: 20rem;
  border-radius: 5px;
  margin: 2rem auto;
}

</style>
