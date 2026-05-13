<script lang="ts">
import { defineComponent } from "vue";
import TemporizadorFix from "./Temporizador.vue";

export default defineComponent({
  name: "FormularioFix",
  components: { TemporizadorFix },
  methods: {
    FinalizarTarefa(tempoDecorrido: number): void {
      console.log("Tarefa finalizada com tempo decorrido de: " + tempoDecorrido + " segundos")
    }
  }
});
</script>

<template>
  <div class="box">
    <div class="columns">
      <div class="column is-8" role="form" aria-label="Formulário para criação de uma nova tarefa">
        <input type="text" class="input" placeholder="Qual tarefa você deseja iniciar?" />
      </div>
      <div class="column">
        <TemporizadorFix @aoTemporizadorFinalizado="FinalizarTarefa" />
      </div>
    </div>
  </div>

</template>