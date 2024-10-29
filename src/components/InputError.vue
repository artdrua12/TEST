<template>
    <div class="wrapper">
        <slot></slot>
        <div class="error"><span v-show="isError">{{ errorMessage }}</span></div>
    </div>

</template>

<script setup>
const props = defineProps({
    errorMessage: {
        type: String,
        default: 'Не валидное значение'
    }
})
const isError = defineModel({ type: Boolean })

</script>

<style scoped>
.wrapper {
    display: flex;
    flex-direction: column;
}

.error {
    height: 17px;
    overflow: hidden;
    text-overflow: ellipsis;
}

span {
    font-size: 14px;
    color: rgb(135, 5, 5);
    font-weight: 700;
    text-overflow: ellipsis;
}
</style>