<template>
    <div class="box has-text-weight-bold">
        <div class="columns">
            <div class="column is-7">
                Tarefa
            </div>
            <div class="column">
                <CronometroComp tempoEmSegundos="15"/>
            </div>
        </div>
    </div>
</template>

<script lang="ts">
import CronometroComp from './Cronometro.vue';
import { defineComponent } from 'vue';
export default defineComponent({
    name: 'TarefaComp',
    components: { CronometroComp }
}) 
</script>

<style scoped>
.box {
    background-color: #FAF0CA;
}
</style>