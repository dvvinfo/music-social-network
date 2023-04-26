<template>
  <div>
    <button
      @click="open = !open"
      class="bg-transparent hover:bg-green-400 text-white font-semibold hover:text-white py-1 px-2 hover:border-transparent rounded"
    >
      <i class="fa-solid fa-bars fa-xl"></i>
    </button>
    <div
      v-show="open"
      class="bg-rgba fixed w-full h-full top-0 left-0 flex justify-center backdrop-blur-sm bg-black z-10"
    >
      <div class="bg-black absolute h-full"></div>
      <div class="my-auto fixed border-white w-80 pt-16">
        <p class="text-2xl text-center text-white font-bold mb-2">Menu</p>
        <RouterLinkButton
          class="w-full text-white text-center text-lg"
          btn-text="Профиль"
          color="green"
          url="/account/profile"
        />
        <RouterLinkButton
          @click="open = !open"
          class="w-full text-white text-center text-lg mt-4"
          btn-text="Закрыть"
          color="blue"
        />
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue'
import RouterLinkButton from '../UI/RouterLinkButton.vue'

const open = ref(false)
</script>

<style lang="scss" scoped>
.bg-rgba {
  background-color: rgba(0, 0, 0, 0.6);
}
</style>
