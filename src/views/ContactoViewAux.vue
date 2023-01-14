<script setup>
//import Form from "./Form.vue";

const itemsCards = [
    { text: "correo@correo.com", title: "Escríbenos" },
    { text: "Calle 123 #27-27 Ciudad X", title: "Visítanos" },
    { text: "Martes a Domingo 11am - 9pm", title: "Horario" }
]
</script>

<template>
    <div class="container">
        <div class="background">
            <div class="imagen"></div>
            <div class="relleno"></div>
        </div>
        <div class="cards">
            <div class="card" v-for="item in itemsCards">
                <div class="title">{{ item.title }}</div>
                <div class="text">{{ item.text }}</div>
            </div>
        </div>
        <!--<div class="containerform"></div>-->
    </div>
</template>
<style scoped lang="scss">
.container {
    //border: 1px green solid; // se utilizo para ver el espacio que se crea al usar media query
    width: 100%;
    position: relative;
    height: 50rem;
    overflow: hidden;// usar media query se agrega espacio, con esto se controla.
    .background {
        width: 100%;
        height: 100%;

        .imagen {
            background: url("https://i.postimg.cc/d0DwD80r/contacto.jpg");
            background-size: cover;
            background-position: center;
            width: 100%;
            height: 60%;
        }

        .relleno {
            width: 100%;
            height: 40%;
        }
    }

    .cards {
        display: flex;
        flex-direction: row;
        width: 100%;
        height: auto;
        position: absolute;
        top: 5rem;
        bottom: 0;
        justify-content: space-around;

        .card {
            background-color: white;
            width: 25%;
            height: 25%;
            border: 6px double gray;
            color: black;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;

            .title {
                font-size: 1.5rem;
                border-bottom: 1px gray solid;
                padding-bottom: 0.5rem;
            }

            .text {
                color: gray;
                padding: 0rem 2rem;
                text-align: center;
                margin-top: 1rem;
            }
        }
    }

    @media all and (max-width: 830px) {
        .cards {
            flex-direction: column;
            height: 50%;
            top: 0;
            //left: 15%;
            left: 15%;
            .card{
                width: 70%;
                height: 30%;
            }
        }
    }

    /*
    .containerform {
        width: 50%;
        position: absolute;
        top: 23rem;
        background-color: red;
    }*/
}
</style>