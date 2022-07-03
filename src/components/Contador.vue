<script setup>
import { ref, watch } from "vue";

const contador = ref(0);
const contadorWatch = ref(0);
const classe = ref("menorQue10");

const nome = ref("Nathan");

watch(contador, function (novoValor) {
    console.log("Estou no watch");
    contadorWatch.value = novoValor * -1;
    if (novoValor > 10) classe.value = "maiorQue10";
    else classe.value = "menorQue10";
});
</script>

<template>
    <input type="button" value="* 2" @click="contador *= 2" />
    <input type="button" value="+ 1" @click="contador += 1" />
    <input type="button" value="- 1" @click="contador -= 1" />
    <input type="button" value="/ 2" @click="contador /= 2" />
    <h1 :class="classe">O número atual é {{ contador }}</h1>
    <h1 :class="classe">O número invertido atual é {{ contadorWatch }}</h1>
    <input v-model="nome" />
    <h1>{{ nome }}</h1>
</template>

<style scoped lang="scss">
.maiorQue10 {
    color: blue;
}

.menorQue10 {
    color: red;
}
</style>
