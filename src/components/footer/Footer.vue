<script setup>
import Icon from "../Icon.vue";
const derechos = "Todos los derechos reservados";
const itemsIcons = [
    { href: "https://www.facebook.com", classIcon: "fa fa-facebook" },
    { href: "https://www.twitter.com", classIcon: "fa fa-twitter" },
    { href: "https://www.instagram.com", classIcon: "fa fa-instagram" },
];
</script>
<template>
    <footer>
        <div class="derechos">{{ derechos }}</div>
        <div class="icons">
            <Icon v-for="item in itemsIcons" :href="item.href" :classIcon="item.classIcon" />
        </div>
    </footer>
</template>
<style scoped lang="scss">
footer {
    background: black;
    height: 9rem;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;

    .derechos {
        margin-bottom: 1rem;
        color: white;
    }

    .icons {
        display: flex;
        flex-direction: row;
        justify-content: space-evenly;
        width: 30%;
    }
}
</style>