<template>
  <main class="columns is-gapless is-multiline">
    <div class="column is-one-quarter">
      <BarraLateral/>
    </div>
    <div class="column is-three-quarter">
      <FormularioTask/>
      <div class="lista">
        <TarefaComp />
        <TarefaComp />
      </div>
    </div>

  </main>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import BarraLateral from './components/BarraLateral.vue';
import FormularioTask from './components/Formulario.vue';
import TarefaComp from './components/Tarefa.vue';

export default defineComponent({
    name: "App",
    components: { BarraLateral, FormularioTask, TarefaComp }
});
</script>

<style>
.lista {
  padding: 1.25rem;
}
</style>
