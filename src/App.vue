<script setup>
import MostrarNaTela from "./components/MostrarNaTela.vue";
import Contador from "./components/Contador.vue";
</script>

<template>
    <h1>MOSTRAR NA TELA</h1>
    <MostrarNaTela />
    <hr />
    <h1>CONTADOR</h1>
    <Contador />
</template>

<style lang="scss">
#app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
}
</style>
