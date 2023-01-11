<script setup></script>
<template>
    <section class="principal">
        <section class="portada">
            <div class="columna">
                <div class="foto izquierda lightbox">
                </div>
                <div class="texto">
                    <h2>Mejor Calidad</h2>
                    <p>
                        Lorem ipsum dolor sit arnet, consertetur adipisicing elit. Esse provident
                        asperiores, ipsa. In dicta vel, ipsa odio quasi perspicialist illo sint
                        reiciendis voluptatum incidunt excepturi doloremque nisi impedit rerum nam
                        expedita delectus molestiac voluptate, animi unde quia ex.
                    </p>
                </div>
                <div class="foto_full izquierda lightbox">
                </div>
            </div>
            <div class="columna">
                <div class="foto_full derecha lightbox">
                </div>
                <div class="foto derecha lightbox">
                </div>
                <div class="texto">
                    <h2>Mejor Sabor</h2>
                    <p>
                        Lorem ipsum dolor sit arnet, consertetur adipisicing elit. Quod incidunt doloremque
                        cumque, nobis possimus porro perferendis, suscipit. Laboriosam similique inventore
                        sequi rem velit consequuntor quasi laborum maxime maiores aspernatur voluptatum,
                        animi, aut atque alias sunt.
                    </p>
                </div>
            </div>
        </section>
    </section>
</template>
<style scoped lang="scss">
.principal {
    height: 80rem;

    .portada {
        display: flex;
        flex-wrap: wrap;
        justify-content: space-between;

        .columna {
            width: 50%;
            background: black;
            color: white;
            display: flex;
            flex-wrap: wrap;

            .foto {
                background-size: cover;
                background-position: center;
                width: 50%;
            }

            .izquierda {
                background-image: url('https://i.postimg.cc/Gh1Lz8Mn/portada1.jpg');
                background-position: left;
            }

            .derecha {
                background-image: url('https://i.postimg.cc/m2NbnLqz/portada2.jpg');
                opacity: 0.8
            }

            .texto {
                width: 50%;
                padding: 3.375rem;

                h2 {
                    font-size: 1.8125rem;
                    font-weight: 400;
                    line-height: 2.6875rem;
                    margin-bottom: 1.125rem;
                }

                p {
                    font-size: 0.9375rem;
                    line-height: 1.75rem;
                }
            }

            .foto_full {
                width: 100%;
                min-height: 15.25rem;
                background-size: cover;
                background-position: center;
            }

            .foto_full.izquierda {
                background-image: url('https://i.postimg.cc/HWMWQ49t/portada3.jpg');
                opacity: 0.8;
            }

            .foto_full.derecha {
                background-image: url('https://i.postimg.cc/W3kVwTg4/portada4.jpg');
                opacity: 0.8;
            }
        }
    }
}

@media all and (max-width: 1500px) {
    .principal .portada .columna .texto {
        padding-left: 2.25rem;
        padding-right: 2.25rem;
    }
}

@media all and (max-width: 1199px) {
    .principal .portada .columna .foto {
        display: none;
    }

    .principal .portada .columna .texto {
        width: 100%;
    }
}

@media all and (max-width: 800px) {


    .principal .portada .columna {
        width: 100%;
    }

    .principal .portada .columna .foto_full.izquierda {
        display: none;
    }

    .principal .portada .columna .texto h2 {
        text-align: center;
    }

    .principal .portada .columna .texto p {
        text-align: justify;
    }
}
</style>