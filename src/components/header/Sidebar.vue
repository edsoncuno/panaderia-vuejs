<script setup>
import { RouterLink } from 'vue-router';
import Icon from "./Icon.vue";

const props = defineProps({
    do: Function
});

const itemsLinks = [
    { route: "/", name: "Inicio" },
    { route: "/nosotros", name: "Nosotros" },
    { route: "/nuestro-chef", name: "Nuestro Chef" },
    { route: "/menu", name: "Menu" },
    { route: "/contacto", name: "Contacto" },
]

const itemsIcons = [
    { href: "https://www.facebook.com", classIcon: "fa fa-facebook" },
    { href: "https://www.twitter.com", classIcon: "fa fa-twitter" },
    { href: "https://www.instagram.com", classIcon: "fa fa-instagram" },
];
</script>
<template>
    <nav>
        <div class="row" v-for="item in itemsLinks">
            <RouterLink :to="item.route" @click="props.do">
                {{ item.name }}
            </RouterLink>
        </div>
        <div class="row">
            <Icon v-for="item in itemsIcons" :href="item.href" :classIcon="item.classIcon" />
        </div>
    </nav>
</template>
<style scoped lang="scss">
nav {
    width: 100%;
    height: 100%;
    background-color: white;
    display: flex;
    flex-direction: column;

    .row {
        font-size: 1.5rem;
        text-align: center;
        border-bottom: 1px gray solid;
        display: flex;
        justify-content: space-around;

        a {
            text-decoration: none;
            color: black;
        }

        a:hover {
            color: #D3D3D3;
        }
    }
}
</style>