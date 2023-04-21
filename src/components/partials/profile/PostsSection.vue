<template>
  <div>
    <div class="mx-auto py-4">
      <div class="flex flex-wrap font-bold text-gray-100">
        <div class="text-gray-900 text-xl">Youtube видео</div>
        <div class="bg-green-500 w-full h-1"></div>
        <div class="w-full mt-4">
          <RouterLinkButton btn-text="Создать пост" color="green" url="/account/create-post" />
        </div>
      </div>
      <div class="flex flex-wrap mb-4">
        <div class="border rounded-lg">
          <a href="#">
            <img class="rounded-t-lg" src="https://via.placeholder.com/500x300" alt="" />
          </a>
          <div class="p-2 md:p-4">
            <div class="text-lg">
              <router-link to="" class="text-blue-500 hover:text-blue-600">
                Тестовое название
              </router-link>
            </div>
            <p class="py-2">Местоположение: Тестовое Местоположение</p>
            <p class="text-gray-900 text-md">
              Lorem ipsum dolor, sit amet consectetur adipisicing elit. Adipisci tempore aut porro
              velit atque ullam recusandae itaque, corrupti, repudiandae, tenetur modi nulla
              repellendus quas! Obcaecati id minus voluptas at officia.
            </p>
            <div class="mt-2 flex items-center justify-end">
              <router-link
                to=""
                class="mr-3 bg-blue-500 hover:bg-blue-700 text-white text-sm font-bold py-1 px-3 rounded-full"
              >
                Редактировать пост
              </router-link>
              <button
                class="bg-red-500 hover:bg-red-700 text-white text-sm font-bold py-1 px-3 rounded-full"
              >
                Удалить
              </button>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import RouterLinkButton from '../../UI/RouterLinkButton.vue'
</script>

<style lang="scss" scoped></style>
