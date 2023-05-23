<template>
    <div class="is-flex is-align-items-center is-justify-content-space-between">
        <CronometroComp :tempoEmSegundos="tempoEmSegundos"/>
        <BotaoAction @clicked="iniciar" icon="fas fa-play" label="play" :disabled="cronometroRodando"/>
        <BotaoAction @clicked="finalizar" icon="fas fa-stop" label="stop" :disabled="!cronometroRodando"/>
    </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import CronometroComp from './Cronometro.vue';
import BotaoAction from './BotaoAction.vue';
export default defineComponent({
    name: "TemporizadorComp",
    emits: ['aoTemporizadorFinalizado'],
    data() {
        return {
            tempoEmSegundos: 0,
            cronometro: 0,
            cronometroRodando: false
        };
    },
    methods: {
        iniciar() {
            this.cronometroRodando = true,
            // o setInterval retorna um id que representa esse interval
            this.cronometro = setInterval(() => {
                this.tempoEmSegundos += 1; 
            }, 1000);
        },
        finalizar() {
            this.cronometroRodando = false,
            clearInterval(this.cronometro);
            this.$emit('aoTemporizadorFinalizado', this.tempoEmSegundos)
            this.tempoEmSegundos = 0 
        }
    },
    components: { CronometroComp, BotaoAction }
})
</script>