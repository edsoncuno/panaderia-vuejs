<script setup>
const props = defineProps({
    do: Function
});
</script>

<template>
    <div @click="props.do">
        <i class="fa fa-bars" aria-hidden="true"></i>
    </div>
</template>
<style scoped>
@import url(https://cdnjs.cloudflare.com/ajax/libs/font-awesome/4.7.0/css/font-awesome.min.css);
div{
    display: flex;
    height: 100%;
    align-items: center;
    justify-content: center;
}
.fa {
    font-size: 3rem;
}
</style>