

<script lang="ts">
import { defineComponent, PropType } from 'vue';
import CronometroFix from "./Cronometro.vue";
import ITarefa from "../interfaces/ITarefa";

export default defineComponent({
  name: 'TarefaFix',
  components: {
    CronometroFix,
  },
  props: {
    tarefa: {
      type: Object as PropType<ITarefa>,
      required: true
    }
  },
  computed: {
    tempoGasto () : string {
      return new Date(this.tarefa.duracaoEmSegundos * 1000)
        .toISOString()
        .substr(11, 8)
    }
  }
});
</script>

<template>
  <Box>
    <div class="columns">
      <div class="column is-7">
        {{ tarefa.descricao || 'Tarefa sem descrição' }}
      </div>
      <div class="column">
        <CronometroFix :tempoEmSegundos="tarefa.duracaoEmSegundos"/>
      </div>
    </div>
  </Box>
</template>