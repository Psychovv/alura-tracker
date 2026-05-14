<script lang="ts">
import { defineComponent } from "vue";
import TemporizadorFix from "./Temporizador.vue";

export default defineComponent({
  name: "FormularioFix",
  emits: ['aoSalvarTarefa'],
  components: {
    TemporizadorFix,
  },
  data () { 
    return {
      descricao: ''      
    }
  },
  methods: {
    salvarTarefa (tempoEmSegundos: number) : void {    
      this.$emit('aoSalvarTarefa', {
        duracaoEmSegundos: tempoEmSegundos,
        descricao: this.descricao
      })
      this.descricao = ''
    }
  }
});
</script>

<template>
  <div class="box">
    <div class="columns">
      <div class="column is-7" role="form" aria-label="Formulário para iniciar uma nova tarefa">
        <input
          class="input"
          type="text"
          placeholder="Qual tarefa você deseja iniciar?"
          v-model="descricao"
        />
      </div>
      <div class="column">
        <TemporizadorFix @aoFinalizarTarefa="salvarTarefa"/>
      </div>
    </div>
  </div>
</template>


<style scoped>
.button {
  margin-left: 8px;
}
.box {
  background-color: var(--bg-primario);
  color: var(--texto-primario);
}
</style>