<script lang="ts">
import { defineComponent } from 'vue';
import BarraLateral from './components/BarraLateral.vue'
import FormularioFix from './components/Formulario.vue'
import TarefaFix from './components/Tarefa.vue'

export default defineComponent({
  name: 'App',
  components: {
    BarraLateral,
    FormularioFix,
    TarefaFix,
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
      <div class="item">
        <TarefaFix />
        <TarefaFix />
        <TarefaFix />
      </div>

    </div>
  </main>
</template>



<style>
.item{
  padding: 1.25rem;
}
</style>