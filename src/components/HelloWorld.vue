<template>

  <form class="form">


    <input-error v-model="isNameError" error-message="Поле не может быть пустым">
      <input type="text" v-model="name" class="form-control" :class="{ 'form-error': isNameError }" placeholder=" Имя">
    </input-error>

    <input-error v-model="isEmailError">
      <input type="text" v-model="email" class="form-control" :class="{ 'form-error': isEmailError }"
        placeholder="Email">
    </input-error>

    <input-error v-model="isPhoneError" error-message="Поле не может быть пустым">
      <input type="text" v-model="phone" class="form-control" :class="{ 'form-error': isPhoneError }"
        v-maska="'+375 (##) ###-##-##'" placeholder="+375(**) ***-**-**">
    </input-error>


    <input-error v-model="isTextError" error-message="Поле не может быть пустым">
      <textarea rows="3" v-model="text" class="form-control" name="text" :class="{ 'form-error': isTextError }"
        placeholder="Cooбщение"></textarea>
    </input-error>




    <input type="submit" class="form-control" @click="handleClick">

  </form>

</template>

<script setup>
import { ref, computed } from 'vue'
import { vMaska } from "maska/vue"
import InputError from './InputError.vue';

const name = ref(null);
const email = ref(null);
const phone = ref(null);
const text = ref(null);

const isNameError = computed(() => {
  return Boolean(name.value !== null && !name.value)
})
const isEmailError = computed(() => {
  return email.value !== null && !/^\w+@[a-zA-Z]{2,}\.[a-zA-Z]{2,7}$/.test(email.value)
})
const isPhoneError = computed(() => {
  return Boolean(phone.value !== null && !phone.value && phone.value.length != 3)
})
const isTextError = computed(() => {
  return Boolean(text.value !== null && !text.value)
})

function handleClick(event) {
  console.log('document');

}

const count = ref(0)
</script>


<style lang="scss">
@import '../assets/form.scss'
</style>
