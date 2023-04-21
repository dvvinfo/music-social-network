<template>
  <div>
    <div class="mx-auto py-4">
      <div class="flex flex-wrap font-bold text-gray-100">
        <div class="text-gray-900 text-xl">Youtube видео</div>
        <div class="bg-green-500 w-full h-1"></div>
        <div class="w-full mt-4">
          <RouterLinkButton
            class="ml-2"
            btn-text="Удалить youtube видео"
            color="blue"
            url="/account/delete-youtube-video"
          />
          <RouterLinkButton
            btn-text="Добавить youtube видео"
            color="green"
            url="/account/add-youtube-video"
          />
        </div>
      </div>
      <div class="flex flex-wrap mb-4">
        <div class="my-1 px-1 w-full md:w-1/2 lg:w-1/2">
          <h3 class="text-xl text-gray-900">Название видео</h3>
          <iframe
            class="w-full h-60"
            src="https://www.youtube.com/embed/oMwPYcKT0w8"
            title="YouTube video player"
            frameborder="0"
            allowfullscreen
            >" frameborder="0"></iframe
          >
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import RouterLinkButton from '../../UI/RouterLinkButton.vue'
</script>

<style lang="scss" scoped></style>
