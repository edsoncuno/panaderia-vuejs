<script setup>
import Form from "../components/form/Form.vue";

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
        </div>
        <div class="cards">
            <div class="card" v-for="item in itemsCards">
                <div class="title">{{ item.title }}</div>
                <div class="text">{{ item.text }}</div>
            </div>
        </div>
        <div class="containerform">
            <Form />
        </div>
    </div>
</template>
<style scoped lang="scss">
.container {
    width: 100%;
    height: 55rem;
    position: relative;

    .background {
        width: 100%;
        height: 100%;
        display: grid;
        grid-template-rows: 3fr 2.5fr;
        grid-template-columns: 1fr;

        .imagen {
            background-image: url('https://i.postimg.cc/d0DwD80r/contacto.jpg');
            background-size: cover;
            background-position: center;
        }
    }

    .cards {
        position: absolute;
        top: 10%;
        left: 0;
        display: flex;
        flex-wrap: wrap;
        justify-content: space-evenly;
        width: 100%;

        .card {
            width: 15rem;
            height: 10rem;
            margin: 1rem;
            background-color: white;
            color: black;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            border: 6px double gray;

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

    @media all and (max-width:815px) {
        .cards {
            top: 1%;
        }
    }

    .containerform {
        position: absolute;
        top: 40%;
        left: 25%;
        width: 50%;
        height: 30rem;
        background: greenyellow;
    }

    @media all and (max-width: 1250px) {
        .containerform {
            top: 40%;
            left: 15%;
            width: 70%;
        }
    }

    @media all and (max-width: 815px) {
        .containerform {
            top: 45%;
            left: 10%;
            width: 80%;
        }
    }

    @media all and (max-width: 543px) {
        .containerform {
            top: 53%;
            left: 10%;
            width: 80%;
        }
    }
}

@media all and (max-width: 815px) {
    .container {
        height: 60rem;
    }
}

@media all and (max-width: 543px) {
    .container {
        height: 70rem;
    }
}
</style>