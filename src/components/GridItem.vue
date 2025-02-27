<template>
  <div class="grid-item" @mouseenter="proximaCor" @click="alternarEstado">
    <div
      v-if="estado === 0 || estado === 2"
      class="linha-diagonal"
      :style="{ backgroundColor: cores[corAtual], transform: 'translate(-50%, -50%) rotate(45deg)' }"
    ></div>
    <div
      v-if="estado === 1 || estado === 2"
      class="linha-diagonal"
      :style="{ backgroundColor: cores[corAtual], transform: 'translate(-50%, -50%) rotate(135deg)' }"
    ></div>
    <div
      v-if="estado === 2"
      class="linha-horizontal"
      :style="{ backgroundColor: cores[corAtual] }"
    ></div>
    <div
      v-if="estado === 2"
      class="linha-vertical"
      :style="{ backgroundColor: cores[corAtual] }"
    ></div>
  </div>
</template>

<script setup lang="ts">
import { ref } from 'vue';

const content = ref('Item');

const cores = ['#000', '#1E1CE5', '#DF1719', '#F6F71E'];

const corAtual = ref(0);

const estado = ref(0);

const proximaCor = () => {
  corAtual.value = (corAtual.value + 1) % cores.length;
};

const alternarEstado = () => {
  estado.value = (estado.value + 1) % 3;
};
</script>

<style scoped>
.grid-item {
  width: 50px;
  height: 50px;
  display: flex;
  align-items: center;
  justify-content: center;
  font-weight: bold;
  position: relative;
  cursor: pointer;
}

.linha-diagonal {
  content: '';
  position: absolute;
  width: 75px;
  height: 4px;
  background-color: black;
  top: 50%;
  left: 50%;
  transition: background-color 0.15s ease-in-out, transform 0.15s ease-in-out;
}

.linha-horizontal {
  content: '';
  position: absolute;
  width: 50px;
  height: 4px;
  background-color: black;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  transition: background-color 0.15s ease-in-out, transform 0.15s ease-in-out;
}

.linha-vertical {
  content: '';
  position: absolute;
  width: 4px;
  height: 50px;
  background-color: black;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  transition: background-color 0.15s ease-in-out, transform 0.15s ease-in-out;
}
</style>
