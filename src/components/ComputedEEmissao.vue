<script setup>
import { computed } from "vue";

const props = defineProps({
    veiculo: { type: String, required: true },
    proprietario: { required: true },
    modelValue: { required: true },
});

const emit = defineEmits(["update:modelValue", "update:proprietario"]);

const proprietario = computed({
    get() {
        return props.proprietario;
    },
    set(novoProprietario) {
        console.log(novoProprietario);
        emit("update:proprietario", novoProprietario);
    },
});

const value = computed({
    get() {
        return props.modelValue;
    },
    set(novoValor) {
        emit("update:modelValue", novoValor);
    },
});

function dirigir() {
    const kmsRodados = Math.floor(Math.random() * 80);
    value.value += kmsRodados;
    console.log(kmsRodados);
}
</script>

<template>
    <h1>
        Veículo: <strong>{{ props.veiculo }}</strong>
    </h1>
    <h1>
        Proprietário:
        <strong>{{ proprietario }}</strong>
    </h1>
    <h1>
        KMs rodados:
        {{ value }}
    </h1>
    <input type="text" placeholder="Proprietário" v-model="proprietario" />
    <br />
    <input type="button" value="Dirigir" @click="dirigir" />
</template>

<style scoped lang="scss"></style>
