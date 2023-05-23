<template>
    <BoxComp>
        <div class="columns">
            <div class="column is-7">
                {{ tarefa.descricao || 'Tarefa sem descricao' }}
            </div>
            <div class="column">
                <CronometroComp :tempoEmSegundos="tarefa.duracaoEmSegundos"/>
            </div>
        </div>
    </BoxComp>
</template>

<script lang="ts">
import ITarefa from '@/interfaces/ITarefa';
import CronometroComp from './Cronometro.vue';
import { defineComponent, PropType } from 'vue';
import BoxComp from './BoxComp.vue';
export default defineComponent({
    name: 'TarefaComp',
    components: { CronometroComp, BoxComp },
    props: {
        tarefa: {
            type: Object as PropType<ITarefa>,
            required: true
        }
    }
}) 
</script>