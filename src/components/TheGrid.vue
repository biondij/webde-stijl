<template>
  <div class="the-grid my-3">
    <div v-for="row in 9" :key="'row-' + row" class="row mx-0">
      <div v-for="col in 20" :key="'col-' + row + '-' + col" class="col px-0">
        <GridItem />
      </div>
    </div>


  </div>
  <div class="mobile text-start">
    <img src="../assets/artediagonal.jpg">
    <h5 class="mt-4">Essa experiência foi pensada pra ser vivida no desktop! Me faz uma visita no seu computador sz</h5></div>
</template>

<script setup lang="ts">
import GridItem from './GridItem.vue'
</script>

<style scoped>
.the-grid {
  display: flex;
  flex-direction: column;
}

.row {
  display: flex;
  justify-content: center;
}

.mobile {
  display: none;

  h5 {
  font-weight: 300;}

  img {
    max-width: 100%;
  }
}

.col {
  width: 50px;
  aspect-ratio: 1 / 1;
  display: flex;
  align-items: center;
  justify-content: center;
}

@media (max-width: 768px) {
  .the-grid {
    display: none;
  }

  .mobile {
    display: block;
  }
  }
</style>
