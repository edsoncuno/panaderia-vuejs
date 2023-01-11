<script setup>
import { RouterLink } from 'vue-router';

const itemsLinks = [
    { route: "/", name: "Inicio" },
    { route: "/nosotros", name: "Nosotros" },
    { route: "/nuestro-chef", name: "Nuestro Chef" },
    { route: "/menu", name: "Menu" },
    { route: "/contacto", name: "Contacto" },
]

</script>

<template>
    <nav>
        <RouterLink v-for="item in itemsLinks" :to="item.route">
            {{ item.name }}
        </RouterLink>
    </nav>
</template>

<style scoped lang="scss">
nav {
    display: flex;
    width: 100%;
    justify-content: space-evenly;

    a {
        text-decoration: none;
        color: black;
    }

    a:hover {
        color: #D3D3D3;
    }
}
</style>