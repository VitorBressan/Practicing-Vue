<template>
    <div>
        <app-botao label="Botão 1" />
        <app-botao label="Botão 2" />
        <app-botao label="Botão 3" />
        <app-botao label="Botão 4" :onclick="clicado" />
    </div>
</template>

<script setup lang="ts">
const clicado = () => {
    alert('Botão clicado!')
}
</script>

<style scoped>

</style>