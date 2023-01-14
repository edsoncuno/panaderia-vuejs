<script setup></script>
<template>
    <div class="container">
        <div class="columnleft">
            <div class="titulo">
                <p>Nosotros</p>
                <h2>Conocenos</h2>
            </div>
        </div>
        <div class="columnright">
            <div class="texto">
                <p>
                    Lorem ipsum dolor sit amet, consectetur adipisicing elit. Quam, facere
                    itaque voluptatibus in quasi aliquid reiciendis quidem quo. Laborum
                    temporibus aut, velit soluta. Cum nostrum quam ipsam nisi. Aperiam
                    cum ea beatae sit sapiente animi soluta adipisci vel suscipit voluptatem.
                    Blanditiis assumenda odit, sunt voluptatibus molestiae iure, beatae placeat
                    laudantium non explicabo earum nesciunt nostrum adipisci consequatur amet,
                    voluptatum laborum aspernatur autem architecto quae dicta rem quisquam nemo
                    repellat. Explicabo eaque magni asperiores libero ut expedita, voluptatibus
                    cum ipsum harum a, molestiae hic! Debitis ab perspiciatis sequi, unde,
                    ducimus, dolorum voluptates expedita commodi nisi, quos excepturi consectetur
                    cupiditate odit cum.
                </p>
            </div>
        </div>
    </div>
</template>
<style scoped lang="scss">
.container {
    display: flex;
    flex-wrap: wrap;
    min-height: 80vh;
    //height: 70vh;
    padding: 5%;

    .columnleft {
        width: 30%;
        border-right: 1px solid grey;
        display: flex;
        align-items: center;
        padding-right: 5%;
        justify-content: right;
        P {
            font-size: 2rem;
        }
        h2 {
            font-size: 3rem;
        }
    }

    .columnright {
        width: 70%;
        padding-left: 5%;
        display: flex;
        align-items: center;
        text-align: left;

        p {
            font-size: 1.125rem;
            line-height: 1.75rem;
            color: #777;
        }
    }
    @media all and (max-width: 1066px) {
        .columnleft{
            padding-right: 1%;
        }
        .columnright{
            padding-left: 1%;
        }
    }

    @media all and (max-width: 940px) {
        .columnleft {
            width: 100%;
            justify-content: center;
            text-align: center;
            border: none;
            border-bottom: 1px solid grey;
            padding: 0;
        }

        .columnright {
            width: 100%;
            padding: 0;
            text-align: justify;
        }
    }
}
</style>