<template>
  <div id="addSong" class="container mx-auto max-w-4xl pt-10 pb-20 px-6">
    <h3 class="text-gray-900 text-xl">Добавить песню</h3>
    <div class="bg-green-500 w-full h-1 mb-4"></div>

    <TextInput
    class=" mb-5"
      label="Назание"
      :label-color="true"
      placeholder="Классная новая песня"
      v-model:input="title"
      input-type="text"
      error="Это тестовая ошибка"
    />

    <div class="w-full mt-4">
      <label class="block uppercase tracking-wide text-gray-700 text-xs font-bold mb-2">
        Выбирите саундрек
      </label>
        <input
          id="image"
          ref="fileInput"
          @change="getUploadedImage"
          class="form-control block w-full text-base font-normal text-gray-700 bg-white bg-clip-padding border border-solid border-gray-400 rounded transition ease-in-out m-0 focus:text-gray-700 focus:bg-white focus:border-blue-600 focus:outline-none"
          type="file"
        />
    </div>
    <SubmitFormButton btn-text="Добавить песню"/>
  </div>
</template>

<script setup>
import SubmitFormButton from '../../components/UI/SubmitFormButton.vue';
import TextInput from '../../components/UI/TextInput.vue'
</script>

<style lang="scss" scoped></style>
