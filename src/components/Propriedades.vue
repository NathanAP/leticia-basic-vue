<script setup>
import { toRef } from "vue";

const props = defineProps({
    nome: { type: String, required: true },
    idade: { type: Number, required: true },
    irmaos: { type: Array, default: [] },
    caracteristicas: { type: Object },
});

const outroCaracteristicas = toRef(props, "caracteristicas");
</script>

<template>
    <input type="text" v-model="outroCaracteristicas.corDoCabelo" />
    <h1>O valor acima é {{ outroCaracteristicas.corDoCabelo }}</h1>
    <input type="text" v-model="props.nome" />
    <h1>O valor acima é {{ props.nome }}</h1>
</template>

<style scoped lang="scss"></style>
