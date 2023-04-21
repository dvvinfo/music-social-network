<template>
  <div>
    <div class="mx-auto py-4">
      <div class="flex flex-wrap font-bold text-gray-100">
        <div class="text-gray-900 text-xl">Песни</div>
        <div class="bg-green-500 w-full h-1"></div>
        <div class="w-full mt-4">
          <RouterLinkButton class="ml-2" btn-text="Удалить песню" color="blue" url="/account/delete-song" />
          <RouterLinkButton btn-text="Добавить песню" color="green" url="/account/add-song" />
        </div>
      </div>
      <div class="pb-4">
        <SongPlayer />
      </div>
    </div>
  </div>
</template>

<script setup>
import RouterLinkButton from '../../UI/RouterLinkButton.vue'
import SongPlayer from './SongPlayer.vue';
</script>

<style lang="scss" scoped></style>
