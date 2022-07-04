<script setup>
import { ref, watch } from "vue";

import MostrarNaTela from "./components/MostrarNaTela.vue";
import Contador from "./components/Contador.vue";
import Propriedades from "./components/Propriedades.vue";
import ComputedEEmissao from "./components/ComputedEEmissao.vue";
import Slots from "./components/Slots.vue";
import SlotsAvancados from "./components/SlotsAvancados.vue";

const pessoa = ref({
    nome: "Nathan",
    idade: 29,
    irmaos: ["Joao", "Maria"],
    caracteristicas: {
        corDoCabelo: "Preto",
    },
});

const veiculo = ref("Ford Ka");
const proprietario = ref("Nathan");
const kmsRodados = ref(18000);

watch(kmsRodados, (novoValor) => console.log("estou no watch"));
</script>

<template>
    <!-- AULA 1 -->
    <h1>MOSTRAR NA TELA</h1>
    <MostrarNaTela />

    <hr />

    <h1>CONTADOR</h1>
    <Contador />

    <!-- AULA 2 -->
    <Propriedades
        :nome="pessoa.nome"
        :idade="pessoa.idade"
        :irmaos="pessoa.irmaos"
        :caracteristicas="pessoa.caracteristicas"
    />

    <hr />

    <ComputedEEmissao
        :veiculo="veiculo"
        v-model:proprietario="proprietario"
        v-model="kmsRodados"
    />

    <hr />

    <!-- AULA 3 -->
    <Slots></Slots>
    <Slots>Eu tenho algo escrito</Slots>
    <Slots>Eu também</Slots>

    <hr />

    <SlotsAvancados>
        <template #nome>
            <strong class="texto-vermelho"> {{ pessoa.nome }}</strong>
        </template>
        <template #idade>
            <strong class="fundo-vermelho"> {{ pessoa.idade }}</strong>
        </template>

        <p class="fundo-vermelho">Gosto de gatos!</p>

        <template #dadosInstagram="{ seguidores, segue, fotos }">
            <h1>Eu sigo {{ segue }} pessoas!</h1>
            <h1>Eu tenho {{ seguidores }} seguidores!</h1>
            <h1>Eu publiquei {{ fotos }} fotos!</h1>
        </template>
    </SlotsAvancados>
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

.texto-vermelho {
    color: red;
}

.fundo-vermelho {
    background-color: red;
}
</style>
