<script setup lang="ts">
import { ref } from 'vue';
import IntroVue from './components/Intro.vue'
import TheGrid from './components/TheGrid.vue'

let filtroAberto = ref(false);

</script>

<template>
  <header>
    <div class="d-flex justify-content-between align-items-center">
      <h1 class="text-center">WebDe Stijl</h1>
    <button type="button" class="btn btn-dark rounded-circle btn-collapse-filtro"  @click="filtroAberto = !filtroAberto">
      <span v-if="filtroAberto">!</span>
      <span v-if="!filtroAberto">?</span>
      </button>
    </div>

    <div>
      <IntroVue :filtroAberto="filtroAberto"/>
    </div>
  </header>

  <main>
    <TheGrid />
  </main>
</template>

<style scoped>
header {
  line-height: 1.5;

  .btn-collapse-filtro {
    width: 2rem;
    height: 2rem;
    padding: 0;
    display: flex;
    align-items: center;
    justify-content: center;
    transition: all 0.15s ease-in-out;

    @media (max-width: 960px) {
      display: none;
    }
  }

  h1 {
    font-weight: 300;
  }
}
</style>
