<template>
    <div class="is-flex is-align-items-center is-justify-content-space-between">
        <CronometroComp :tempoEmSegundos="tempoEmSegundos"/>
        <button class="button" @click="iniciar">
            <span class="icon">
                <i class="fas fa-play"></i>
            </span>
            <span>play</span>
        </button>
        <button class="button" @click="finalizar">
            <span class="icon">
                <i class="fas fa-stop"></i>
            </span>
            <span>stop</span>
        </button>
    </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import CronometroComp from './Cronometro.vue';
export default defineComponent({
    name: "TemporizadorComp",
    data() {
        return {
            tempoEmSegundos: 0,
            cronometro: 0
        };
    },
    methods: {
        iniciar() {
            // o setInterval retorna um id que representa esse interval
            this.cronometro = setInterval(() => {
                this.tempoEmSegundos += 1; 
            }, 1000);
        },
        finalizar() {
            clearInterval(this.cronometro);
        }
    },
    components: { CronometroComp }
})
</script>