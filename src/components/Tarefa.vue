<template>
    <div class="box has-text-weight-bold">
        <div class="columns">
            <div class="column is-7">
                {{ tarefa.descricao }}
            </div>
            <div class="column">
                <CronometroComp :tempoEmSegundos="tarefa.duracaoEmSegundos"/>
            </div>
        </div>
    </div>
</template>

<script lang="ts">
import ITarefa from '@/interfaces/ITarefa';
import CronometroComp from './Cronometro.vue';
import { defineComponent, PropType } from 'vue';
export default defineComponent({
    name: 'TarefaComp',
    components: { CronometroComp },
    props: {
        tarefa: {
            type: Object as PropType<ITarefa>,
            required: true
        }
    }
}) 
</script>

<style scoped>
.box {
    background-color: #FAF0CA;
}
</style>