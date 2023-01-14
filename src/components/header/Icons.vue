<script setup>
import Icon from "../Icon.vue"
const itemsIcons = [
    { href: "https://www.facebook.com", classIcon: "fa fa-facebook" },
    { href: "https://www.twitter.com", classIcon: "fa fa-twitter" },
    { href: "https://www.instagram.com", classIcon: "fa fa-instagram" },
];
</script>

<template>
    <nav>
        <Icon v-for="item in itemsIcons" :href="item.href" :classIcon="item.classIcon" />
    </nav>
</template>

<style scoped>
nav {
    display: flex;
    flex-direction: row;
    justify-content: space-evenly;
    width: 100%;
}
</style>