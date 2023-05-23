<template>
    <button class="button" @click="clicked" :disabled="disabled">
        <span class="icon">
            <i :class="icon"></i>
        </span>
        <span>{{ label }}</span>
    </button>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
export default defineComponent({
    name: 'BotaoAction',
    emits: [ 'clicked' ],
    props: {
        disabled: {
            type: Boolean
        },
        icon: {
            type: String,
            required: true
        },
        label: {
            type: String,
            required: true
        }
    },
    methods: {
        clicked() : void {
            this.$emit('clicked')
        }
    }
})
</script>