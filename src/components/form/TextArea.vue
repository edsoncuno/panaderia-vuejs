<script setup>
import { ref } from 'vue';

const props = defineProps({
    field: String,
    error: Boolean,
    message: String,
    modelValue: String,
    isError: Boolean,
});

const emits = defineEmits(['update:modelValue']);

const isActive = ref(false);

const handlerFocus = () => {
    if (props.modelValue == "") {
        isActive.value = true;
    } else if (props.modelValue != "") {
        isActive.value = true;
    }
}

const handlerBlur = () => {
    if (props.modelValue == "") {
        isActive.value = false;
    } else if (props.modelValue != "") {
        isActive.value = true;
    }
}
</script>

<template>
    <div class="input">
        <label :class="{ active: isActive }">{{ field }}</label>
        <textarea :onfocus="handlerFocus" :onblur="handlerBlur" :value="modelValue"
            @input="$emit('update:modelValue', $event.target.value)"></textarea>
        <span v-if="isError">{{ message }}</span>
    </div>
</template>

<style scoped lang="scss">
.input {
    width: 100%;
    height: auto;
    position: relative;

    label {
        color: #777;
        position: absolute;
        top: 1rem;
        left: 0;
        margin-left: 1rem;
        transition: all 0.3s;
    }

    .active {
        top: -1.5rem;
        margin-left: 0;
        font-size: 0.75rem;
        line-height: 2rem;
    }

    textarea {
        width: 100%;
        height: 3rem;
        outline: none;
        border: none;
        font-size: 1.2rem;
    }

    textarea:focus {
        border-bottom: 2px solid gold;
    }

    span {
        color: rgb(255, 59, 59);
        font-size: 0.8rem;
    }
}
</style>