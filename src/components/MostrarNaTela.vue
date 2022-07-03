<script setup>
const nome = "Nathan";
const idade = 29;
const generoMasculino = true;

function anoDoNascimento(fizAniversario = false) {
    if (fizAniversario) return new Date().getFullYear() - idade;
    else return new Date().getFullYear() - idade - 1;
}
</script>

<template>
    <h1>Meu nome é {{ nome }}</h1>
    <h1>{{ `Minha idade é ${idade} anos` }}</h1>
    <h1>Sou {{ generoMasculino ? "homem" : "mulher" }}</h1>
    <h1>Nasci no ano de {{ anoDoNascimento(false) }}</h1>
</template>

<style scoped lang="scss">
$minha-cor: #42b983;

h1 {
    color: $minha-cor;
}
</style>
