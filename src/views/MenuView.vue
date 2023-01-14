<script setup>
import { ref } from "vue";

const categoria = ref("postres");

const cambiarClases = (e) => {
    const collection = document.getElementsByClassName("categoria-activo");
    for (let i = 0; i < collection.length; i++) {
        collection[i].className = 'categoria';
    }
    e.target.className = 'categoria categoria-activo';
}

const seleccionarPostres = (e) => {
    cambiarClases(e);
    categoria.value = "postres";
    items.value = itemsPostres;
}
const seleccionarCafes = (e) => {
    cambiarClases(e);
    categoria.value = "cafes";
    items.value = itemsCafes;
}

const titulo = "Nuestro menú";

const itemsPostres = [
    {
        nombre: 'Lorem ipsum dolor.',
        descripcion: 'Lorem ipsum dolor sit amet, consectetur adipisicing elit. Voluptates, nostrum.',
        precio: '15'
    },
    {
        nombre: 'Donec placerat dignissim.',
        descripcion: 'Maecenas iaculis aliquam lectus, in sodales ligula. Nulla facilisis magna.',
        precio: '17'
    },
    {
        nombre: 'Nulla vestibulum.',
        descripcion: 'Nulla facilisis magna in malesuada dictum. Donec condimentum metus eros.',
        precio: '21'
    },
    {
        nombre: 'Sed semper.',
        descripcion: 'Vestibulum euismod neque id est ultricies pretium. Sed rutrum risus at congue suscipit.',
        precio: '20'
    },
]
const itemsCafes = [
    {
        nombre: 'Cafe ipsum dolor.',
        descripcion: 'Maecenas iaculis aliquam lectus, in sodales ligula. Nulla facilisis magna.',
        precio: '4'
    },
    {
        nombre: 'Late dignissim.',
        descripcion: 'Vestibulum euismod neque id est ultricies pretium. Sed rutrum risus at congue suscipit.',
        precio: '6'
    },
    {
        nombre: 'Cappuccino vestibulum.',
        descripcion: 'Etiam aliquet at mi in aliquet. Duis in arcu sodales, gravida lorem quis.',
        precio: '5'
    },
    {
        nombre: 'Cafe semper.',
        descripcion: 'Praesent ac pellentesque urna, ut lacinia erat. Donec in euismod erat. Mauris eu.',
        precio: '8'
    },
]

const items = ref(itemsPostres);
</script>
<template>
    <div class="container">
        <div class="title">{{ titulo }}</div>
        <div class="categorias">
            <div class="categoria categoria-activo" @click="seleccionarPostres">POSTRES</div>
            <div class="categoria" @click="seleccionarCafes">CAFÉS</div>
        </div>
        <div class="items">
            <div class="item" v-for="(item, index) in items">
                <hr v-if="index != 0">
                <div class="columnleft">
                    <div class="nombre">{{ item.nombre }}</div>
                    <div class="descripcion">{{ item.descripcion }}</div>
                </div>
                <div class="columnright">
                    <div class="precio">${{ item.precio }}</div>
                </div>
            </div>
        </div>
    </div>
</template>
<style scoped lang="scss">
.container {
    display: flex;
    flex-wrap: wrap;
    padding: 3rem;
    justify-content: center;

    .title {
        width: 100%;
        font-size: 2.5rem;
        font-style: italic;
        font-weight: bold;
        text-align: center;
        align-items: center;
        justify-content: center;
    }

    .categorias {
        width: 100%;
        display: flex;
        flex-direction: row;
        justify-content: center;
        align-items: center;
        margin: 1rem 0rem;

        .categoria {
            margin: 0rem 0.5rem;
            text-decoration: none;
            font-weight: bold;
            cursor: pointer; //hacer que al colocar el mouse sobre el cambie el icono a una dedo
            transition: all .3s ease;
            color: black;
        }

        .categoria:hover {
            color: gold;
        }

        .categoria-activo {
            color: gold;
        }
    }

    .items {
        width: 70%;
        border: 0.5rem double gray;
        padding: 1.5rem;

        .item {
            width: 100%;
            display: flex;
            flex-wrap: wrap;

            hr {
                width: 100%;
                margin: 3% 0;
            }

            .columnleft {
                width: 80%;
                display: flex;
                flex-direction: column;

                .nombre {
                    font-size: 1.5rem;
                }

                .descripcion {
                    color: gray;
                    margin-top: 1%;
                }
            }

            .columnright {
                width: 20%;
                display: flex;
                align-items: center;
                justify-content: center;
                font-size: 2rem;
            }

            @media all and (max-width:612px) {
                .columnleft {
                    width: 100%;
                }

                .columnright {
                    width: 100%;
                    margin-top: 5%;
                }
            }
        }
    }
    @media all and (max-width: 612px) {
        .items{
            width: 90%;
        }
    }
    @media all and (max-width: 350px) {
        .items{
            width: 100%;
        }
    }
}
</style>