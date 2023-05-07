
<template>
  <main>

    <h1>GitHub Pages CI/CD</h1>

    <button
      @click="showModal = true"
    >Abrir Modal</button>

    <ModalVue
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

    </ModalVue>

  </main>
</template>

<script setup lang="ts">

import ModalVue from './components/ModalVue.vue'

import { ref } from 'vue'

const showModal = ref<boolean>(false)

const openModal = () => showModal.value = true

// tsconfig.json
// "target": "ESNext",
// "types": ["vite/client"],
import.meta.env.DEV && console.log('dev')

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
}

img {
  width: 20rem;
  border-radius: 5px;
  margin: 2rem auto;
}

</style>
