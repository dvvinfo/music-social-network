<template>
  <div class="register">
    <div class="w-full p-6 flex justify-center items-center">
      <div class="w-full max-w-xs">
        <div class="bg-black p-8 shadow rounded mb-6">
          <h1 class="mb-6 text-lg text-gray-100 font-thin">Давайте зажигать!</h1>
          <div class="mb-4">
            <textInput
              label="Email"
              :label-color="false"
              placeholder="ivanov@mail.ru"
              v-model:input="email"
              input-type="email"
              :error="errors.email ? errors.email[0] : ''"
            />
          </div>
          <div class="mb-4">
            <TextInput
              label="Пароль"
              :label-color="false"
              placeholder="password123?"
              v-model:input="password"
              input-type="password"
              :error="errors.password ? errors.password[0] : ''"
            />
          </div>
          <button
            @click="login"
            class="block w-full bg-green-500 text-white rounded-sm py-3 text-sm tracking-wide"
          >
            Авторизоваться
          </button>
        </div>
        <p class="text-center text-md text-gray-900">
          У вас еще нет учетной записи?
          <router-link to="register" class="text-blue-500 no-underline hover:underline">
            Зарегистрироваться
          </router-link>
        </p>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue'
import axios from 'axios'
import {useUserStore} from '../stores/user-store'
import TextInput from '../components/UI/TextInput.vue'

const userStore = useUserStore()

const email = ref(null)
const password = ref(null)
const errors = ref([])

const login = async () => {
  errors.value = []

  try {
    let res = await axios.pots('login', {
      email: email.value,
      password: password.value
    })
    console.log(res)

    userStore.setUserDetails(res)
  } catch (err) {
    errors.value = err.response.data.errors
  }
}
</script>

<style lang="scss" scoped></style>
