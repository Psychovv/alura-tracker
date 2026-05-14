<script lang="ts">
import { defineComponent } from 'vue';
import BarraLateral from './components/BarraLateral.vue'
import FormularioFix from './components/Formulario.vue'
import TarefaFix from './components/Tarefa.vue'
import BoxFix from './components/Box.vue'
import ITarefa from './interfaces/ITarefa'

export default defineComponent({
  name: 'App',
  components: {
    BarraLateral,
    FormularioFix,
    TarefaFix,
    BoxFix
  },
  data () {
    return {
      tarefas: [] as ITarefa[],
      modoEscuroAtivo: false
    }
  },
  computed: {
    listaEstaVazia () : boolean {
      return this.tarefas.length === 0
    }
  },
  methods: {
    salvarTarefa (tarefa: ITarefa) {
      this.tarefas.push(tarefa)
    },
    trocarTema (modoEscuro: boolean) {
      this.modoEscuroAtivo = modoEscuro
    }
  }
});
</script>


<template>
  <main :class="['columns is-gapless is-multiline', { 'modo-escuro': modoEscuroAtivo }]">
    <div class="column is-one-quarter">
      <BarraLateral @aoTemaAlterado="trocarTema" />
    </div>
    <div class="column is-three-quarter conteudo">
      <FormularioFix @aoSalvarTarefa="salvarTarefa"/>
      <div class="lista">
        <TarefaFix v-for="(tarefa, index) in tarefas" :key="index" :tarefa="tarefa"/>
        <BoxFix v-if="listaEstaVazia">
          Você não está muito produtivo hoje :(
        </BoxFix>
      </div>
    </div>
  </main>
</template>



<style>
.lista {
  padding: 1.25rem;
}
main {
  --bg-primario: #fff;
  --texto-primario: #000;
}
main.modo-escuro {
  --bg-primario: #2b2d42;
  --texto-primario: #ddd;
}
.conteudo {
  background-color: var(--bg-primario);
}
</style>