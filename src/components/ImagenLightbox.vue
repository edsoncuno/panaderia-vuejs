<script setup>
import { ref } from 'vue';

const props = defineProps({
    url: String,
    backgroundPosition: String
})

const isActiveLigthbox = ref(false);

const style = {
    minWidth: "100%",
    minHeight: "100%",
    backgroundSize: "cover",
    background: `url("${props.url}")`,
    backgroundPosition: props.backgroundPosition
}

const clickOnImagen = () => {
    if (isActiveLigthbox.value) {
        isActiveLigthbox.value = false;
    } else {
        isActiveLigthbox.value = true;
    }
}

</script>

<template>
    <div :style="style" @click="clickOnImagen">
        <div v-if="isActiveLigthbox" class="ligthbox">
            <img :src="props.url" logo="" alt="" />
        </div>
    </div>
</template>

<style scoped lang="scss">
.ligthbox {
    width: 100%;
    height: 100%;
    position: fixed;
    z-index: 99;
    background: rgba(0, 0, 0, 0.8);
    top: 0;
    left: 0;
    display: flex;
    justify-content: center;

    img {
        height: 100%;
    }
}
</style>