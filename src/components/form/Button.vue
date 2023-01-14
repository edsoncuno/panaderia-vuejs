<script setup>
let props = defineProps({
    do: Function
});
</script>

<template>
    <button @click="props.do">Enviar</button>
</template>

<style scoped>
button {
    border: none;
    font-size: 1rem;
    width: 7rem;
    height: 3rem;
    background-color: goldenrod;
    color: white;
    transition: all 0.3s;
}

button:hover {
    background-color: white;
    color: goldenrod;
    border: 1px solid goldenrod;
}
</style>