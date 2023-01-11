<script setup>
import Logo from "./Logo.vue";
import Nav from "./Nav.vue";
import Icons from "./Icons.vue";
import Bars from "./Bars.vue";
import Sidebar from "./Sidebar.vue";

import { ref } from "vue";

const isActive = ref(false);

const handleSidebarSlider = () => {
    if (isActive.value) {
        isActive.value = false;
    } else {
        isActive.value = true;
    }
}

</script>
<template>
    <header>
        <div class="logo">
            <Logo />
        </div>
        <div class="nav">
            <Nav />
        </div>
        <div class="icons">
            <Icons />
        </div>
        <div class="bars">
            <Bars :do="handleSidebarSlider" />
        </div>
        <div class="sidebarslider" :class="{ activeSidebarSlider: isActive }" id="sidebarslider">
            <Sidebar :do="handleSidebarSlider" />
        </div>
    </header>
</template>
<style scoped lang="scss">
header {
    width: 100%;
    height: 5rem;
    border-bottom: 2px solid grey;
    display: flex;
    flex-direction: row;
    justify-content: space-evenly;
    align-items: center;
    background-color: white;
    position: fixed;
    top: 0;
    left: 0;
    z-index: 1;

    .logo {
        width: 10%;
        height: 80%;
    }

    .nav {
        width: 60%;
    }

    .icons {
        width: 15%;
    }

    .bars {
        display: none;
        width: 10%;
        height: 80%;
    }

    .sidebarslider {
        width: 100%;
        position: fixed;
        top: 5rem;
        left: -100%;
        transition: left 0.3s ease;
    }

    .activeSidebarSlider {
        left: 0;
    }

    @media all and (max-width: 830px) {
        .nav {
            display: none;

        }

        .icons {
            display: none;
        }

        .bars {
            display: block;
        }
    }
}
</style>