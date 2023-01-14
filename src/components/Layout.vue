<script setup>
import Header from "./header/Header.vue";
import { RouterView } from 'vue-router'
import Footer from "./footer/Footer.vue";
</script>

<template>
    <Header />
    <main>
        <RouterView />
    </main>
    <Footer />
</template>
<style scoped>
main {
    margin-top: 5rem;
}
</style>