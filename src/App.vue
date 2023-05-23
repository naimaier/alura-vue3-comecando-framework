<template>
  <main class="columns is-gapless is-multiline">
    <div class="column is-one-quarter">
      <BarraLateral/>
    </div>
    <div class="column is-three-quarter">
      <FormularioTask @aoSalvarTarefa="salvarTarefa"/>
      <div class="lista">
        <TarefaComp v-for="(tarefa, index) in tarefas" :key="index" :tarefa="tarefa"/>
        <BoxComp v-if="listaEstaVazia">
          Você nao esta muito produtivo hoje :(
        </BoxComp>
      </div>
    </div>

  </main>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import BarraLateral from './components/BarraLateral.vue';
import FormularioTask from './components/Formulario.vue';
import TarefaComp from './components/Tarefa.vue';
import ITarefa from './interfaces/ITarefa'
import BoxComp from './components/BoxComp.vue';

export default defineComponent({
    name: "App",
    components: { BarraLateral, FormularioTask, TarefaComp, BoxComp },
    data() {
      return {
        tarefas: [] as ITarefa[]
      }
    },
    computed: {
      listaEstaVazia() : boolean {
        return this.tarefas.length === 0
      }
    },
    methods: {
      salvarTarefa (tarefa: ITarefa) {
        this.tarefas.push(tarefa)
      }
    }
});
</script>

<style>
.lista {
  padding: 1.25rem;
}
</style>
