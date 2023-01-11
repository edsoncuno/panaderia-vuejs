<script setup>
defineProps({
    href: String,
    classIcon: String
})
</script>

<template>
    <a :href="href" :class="classIcon" target="_blank"></a>
</template>

<style scoped >
@import url(https://cdnjs.cloudflare.com/ajax/libs/font-awesome/4.7.0/css/font-awesome.min.css);

.fa {
    font-size: 3rem;
    text-decoration: none;
}

.fa:hover {
    opacity: 0.7;
}

.fa-facebook {
    color: #3B5998;
}

.fa-twitter {
    color: #55ACEE;
}

.fa-instagram {
    color: #125688;
}
</style>