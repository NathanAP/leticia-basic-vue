<script setup>
import { ref } from "vue";

const dadosInstagram = {
    seguidores: 550,
    segue: 250,
    fotos: 20,
};
</script>

<template>
    <h1>
        Meu nome é
        <slot name="nome" />
        !
    </h1>
    <h1>
        Tenho
        <slot name="idade" />
        anos!
    </h1>
    <h1>Um pouco sobre mim:</h1>
    <h1 class="cor-roxo">
        <slot class="cor-roxo" />
    </h1>

    <slot name="dadosInstagram" v-bind="dadosInstagram" />
</template>

<style scoped lang="scss">
.cor-roxo {
    color: purple;
}
</style>
