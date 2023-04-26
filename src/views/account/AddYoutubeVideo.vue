<template>
  <div id="addSong" class="container mx-auto max-w-4xl pt-10 pb-20 px-6">
    <h3 class="text-gray-900 text-xl">Добавить видео с ютуб</h3>
    <div class="bg-green-500 w-full h-1 mb-4"></div>

    <TextInput
      class="mb-5"
      label="Назание"
      :label-color="true"
      placeholder="Классное новое видео"
      v-model:input="title"
      input-type="text"
      error="Это тестовая ошибка"
    />
    <div class="mt-2">
      <TextInput
        class="mb-2"
        label="URL адрес видео"
        :label-color="true"
        placeholder="2vnYXKwneUQ"
        v-model:input="videoCode"
        input-type="text"
        error="Это тестовая ошибка"
      />
    </div>

    <SubmitFormButton btn-text="Добавить видео" />
  </div>
</template>

<script setup>
import SubmitFormButton from '../../components/UI/SubmitFormButton.vue'
import TextInput from '../../components/UI/TextInput.vue'
</script>

<style lang="scss" scoped></style>
