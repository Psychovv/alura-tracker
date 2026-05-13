<script lang="ts">
import { defineComponent } from 'vue';
import BarraLateral from './components/BarraLateral.vue'
import FormularioFix from './components/Formulario.vue'

export default defineComponent({
  name: 'App',
  components: {
    BarraLateral,
    FormularioFix
  }
});
</script>

<template>
  <main class="columns is-gapless is-multiline">
    <div class="column is-one-quarter">
      <BarraLateral />
    </div>
    <div class="column is-three-quarter">
      <FormularioFix />
      <!-- sera implementado mais tarde -->
    </div>
  </main>
</template>



<style>

</style>