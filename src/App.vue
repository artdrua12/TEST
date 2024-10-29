<template>
  <div class="app">
    <p>Кнопка для открытия модального окна <button @click="isOpen = !isOpen">Open Modal</button> </p>

    <p>Форма</p>
    <HelloWorld />
    <ModalWindows v-model="isOpen" title="Заголовок для модального окна" icon="mdi-exit-to-app">
      <h1>Текст для модального окна</h1>
    </ModalWindows>

  </div>
</template>

<script setup>
import { ref } from 'vue'
import ModalWindows from './components/ModalWindows.vue';
import HelloWorld from './components/HelloWorld.vue'

const isOpen = ref(false) // модальное окно "Настройки"

</script>

<style lang="scss">
@import './assets/style.scss'
</style>