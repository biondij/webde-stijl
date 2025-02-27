<script lang="ts" setup>
import { defineProps } from 'vue';

const props = defineProps({
  filtroAberto: Boolean
});
</script>

<template>
  <div class="greetings my-3">
    <div class="filtros">
      <div v-if="filtroAberto">
        <p class="mb-4">WebDe Stijl é meu primeiro projeto de Design Gráfico utilizando código! O título é uma brincadeira com WebDesign e De Stijl, o movimento artístico encabeçado por Mondrian e Theo van Doesburg que usei de inspiração para criar o mosaico. Meu professor de design de superfícies comentou que os dois artistas citados entraram em conflito sobre o uso da linha diagonal, e em homenagem à briga quis criar uma composição usando apenas elas. <br>
         <span class="amarelo"> A intenção é que você se divirta criando diferentes visuais ao clicar e passar o mouse sobre as linhas!</span>
        </p>
      </div>

    </div>
  </div>
</template>



<style scoped>
.greetings h4 {
  text-align: center;
  font-weight: 300;
}

.amarelo {
  background-color: #1E1CE5;
  color: #fff;
  font-weight: 500;
}


@media (min-width: 1024px) {
  .greetings h1,
  .greetings h3 {
    text-align: left;
  }
}
</style>
