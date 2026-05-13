<script lang="ts">
import { defineComponent } from "vue";
import CronometroFix from './Cronometro.vue';
export default defineComponent({
  name: "TarefaFix",
  components: { CronometroFix },
})
</script>







<template>
  <div class="box has-text-weight-bold">
    <div class="column lista">
      <div class="column is-7">Descricao da Tarefa</div>
      <div class="column">
        <CronometroFix :tempoEmSegundos="15" />
      </div>
    </div>
  </div>
</template>

<style scoped>
.box {
  background: rgba(228, 221, 120, 0.667);
  
  }
</style>