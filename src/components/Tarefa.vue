<script lang="ts">
import { defineComponent, PropType } from "vue";
import CronometroFix from "./Cronometro.vue";
import ITarefa from '../interfaces/ITarefa'
import BoxFix from './Box.vue'

export default defineComponent({
  name: "TarefaFix",
  components: {
    CronometroFix,
    BoxFix
  },
  props: {
    tarefa: {
      type: Object as PropType<ITarefa>,
      required: true
    }
  }
});
</script>


<template>
  <BoxFix>
    <div class="columns">
      <div class="column is-7">{{ tarefa.descricao || 'Tarefa sem descrição' }}</div>
      <div class="column">
        <CronometroFix :tempoEmSegundos="tarefa.duracaoEmSegundos"/>
      </div>
    </div>
  </BoxFix>
</template>

