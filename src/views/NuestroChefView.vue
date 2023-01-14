<script setup>
import { onMounted, onUnmounted } from 'vue'

const titulo = 'Nuestro Chef';
const parrafo = 'Lorem ipsum dolor sit amet, consectetur adipisicing elit. Temporibus, fuga. Blanditiis assumenda odit, sunt voluptatibus molestiae iure, beatae placeat laudantium non explicabo earum nesciunt nostrum adipisci consequatur amet';

function mover() {
    let elementSlider = document.getElementsByClassName("slider")[0];
    elementSlider.style.transition = 'all 0.5s ease';
    elementSlider.style.marginLeft = '-100%';
    setTimeout(function () {
        elementSlider.appendChild(elementSlider.firstElementChild);
        elementSlider.style.transition = 'all 0s';
        elementSlider.style.marginLeft = 'unset';
    }, 1000)
}

let intervalId;

onMounted(() => {
    intervalId = setInterval(mover, 3000);
});

onUnmounted(() => {
    clearInterval(intervalId);
});

</script>
<template>
    <div class="container">
        <div class="columna izquierda">
            <div class="slider">
                <div class="slide foto1"></div>
                <div class="slide foto2"></div>
                <div class="slide foto3"></div>
            </div>
        </div>
        <div class="columna derecha">
            <div class="titulo">{{ titulo }}</div>
            <div class="parrafo">{{ parrafo }}</div>
        </div>
    </div>
</template>
<style scoped lang="scss">
.container {
    width: 100%;
    padding: 3rem;
    background: black;
    display: flex;
    flex-wrap: wrap;

    .columna {
        width: 50%;
    }

    .izquierda {
        overflow: hidden;

        .slider {
            width: 300%;
            display: flex;

            .slide {
                width: 100%;
                height: 25rem;
                background-size: cover;
                background-position: center;
            }

            .foto1 {
                background-image: url('https://i.postimg.cc/VkfYPyQ7/chef1.jpg');
            }

            .foto2 {
                background-image: url('https://i.postimg.cc/0yV98t99/chef2.jpg');
            }

            .foto3 {
                background-image: url('https://i.postimg.cc/q7Y0KztY/chef3.jpg');
            }
        }
    }

    .derecha {
        display: flex;
        flex-direction: column;
        justify-content: center;
        padding-left: 2rem;

        .titulo {
            color: white;
            font-size: 3rem;
            font-style: italic;
            margin-bottom: 2rem;
        }

        .parrafo {
            color: grey;
            font-size: 1rem;
            line-height: 2rem;
        }
    }

    @media all and (max-width: 622px) {
        .columna {
            width: 100%;
        }

        .derecha {
            align-items: center;

            .titulo {
                margin-top: 2rem;
            }
        }
    }
}
</style>