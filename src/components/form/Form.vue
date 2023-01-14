<script setup>
import Input from './Input.vue';
import Button from './Button.vue';
import TextArea from "./TextArea.vue";
import { ref } from 'vue';

const dataContacto = ref({
    nombre: "",
    email: "",
    mensaje: "",
})

const errorNombre = ref(false);
const errorEmail = ref(false);
const errorMensaje = ref(false);

const enviar = () => {
    if (dataContacto.value.nombre == "") {
        errorNombre.value = true;
    } else {
        errorNombre.value = false;
    }
    if (dataContacto.value.email == "") {
        errorEmail.value = true;
    } else {
        errorEmail.value = false;
    }
    if (dataContacto.value.mensaje == "") {
        errorMensaje.value = true;
    } else {
        errorMensaje.value = false;
    }
    if (errorNombre.value == false && errorEmail.value == false && errorMensaje.value == false) {
        dataContacto.value.nombre = "";
        dataContacto.value.email = "";
        dataContacto.value.mensaje = "";
    }
}

</script>

<template>
    <div class="form">
        <Input field="Nombre" message="Por favor llena el campo con tu nombre" v-model="dataContacto.nombre"
            :isError="errorNombre" />
        <Input field="Correo Electronico" message="Por favor llena el campo con tu email" v-model="dataContacto.email"
            :isError="errorEmail" />
        <TextArea field="Mensaje" message="Por favor llena el campo con tu mensaje" v-model="dataContacto.mensaje"
            :isError="errorMensaje" />
        <Button :do="enviar" />
    </div>
</template>

<style scoped lang="scss">
.form {
    width: 100%;
    height: 100%;
    background-color: white;
    display: flex;
    flex-wrap: wrap;
    padding: 2rem;
    border: 6px double gray;
    justify-content: center
}
</style>