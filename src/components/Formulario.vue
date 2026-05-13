<script lang="ts">
import { defineComponent } from "vue";
import TemporizadorFix from "./Temporizador.vue";

export default defineComponent({
  name: "FormularioFix",
  components: { TemporizadorFix }
});
</script>

<template>
  <div class="box">
    <div class="columns">
      <TemporizadorFix />
    </div>
  </div>
</template>