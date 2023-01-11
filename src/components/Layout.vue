<script setup>
import Header from "./header/Header.vue";
import { RouterView } from 'vue-router'
</script>

<template>
    <Header />
    <main>
        <RouterView />
    </main>
</template>
<style scoped>
main {
    margin-top: 5rem;
}
</style>