<template>
  <div id="CreatePost" class="container max-w-4xl mx-auto pt-20 pb-20 px-6">
    <div class="text-gray-900 text-xl">Создать пост</div>
    <div class="bg-green-500 w-full h-1"></div>
    <!-- Modal -->
    <CropperModal
      v-if="showModal"
      :min-aspect-ratio-prop="{ with: 16, height: 9 }"
      :max-aspect-ratio-prop="{ with: 16, height: 9 }"
      @croppedImageData="setCroppedImageData"
      @showModal="showModal = false"
    />

    <div class="flex flex-wrap mt-4 mb-6">
      <div class="w-full md:w-1/2 px-3">
        <TextInput
          label="Название поста"
          :label-color="true"
          placeholder="Классный пост"
          v-model:input="title"
          input-type="text"
          error="Это тестовая ошибка"
        />
      </div>
      <div class="w-full md:w-1/2 px-3">
        <TextInput
          label="Местоположение"
          :label-color="true"
          placeholder="Москва, Россия"
          v-model:input="location"
          input-type="text"
          error="Это тестовая ошибка"
        />
      </div>
    </div>

    <div class="flex flex-wrap mt-4 mb-6">
      <div class="w-full md:w-1/2 px-3">
        <DisplayCropperButton
          @showModal="showModal = true"
          label="Изображение поста"
          btn-text="Добавить изображение поста"
        />
      </div>
    </div>

    <div class="flex flex-wrap mt-4 mb-6">
      <div class="w-full  px-3">
        <CroppedImage
          label="Обрезанное изображение"
        :image="image"
        />
      </div>
    </div>

    <div class="flex flex-wrap mt-4 mb-6">
      <div class="w-full px-3">
        <TextArea
          label="Описание"
          placeholder="Пожалуйста, введите описание"
          v-model="description"
          error="Это тестовая ошибка"
        />
      </div>
    </div>
    <div class="flex flex-wrap mt-8 mb-6">
      <div class="w-full px-3">
        <SubmitFormButton btn-text="Создать пост" />
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue'
import TextInput from '../../components/UI/TextInput.vue'
import DisplayCropperButton from '../../components/UI/DisplayCropperButton.vue'
import TextArea from '../../components/UI/TextArea.vue'
import SubmitFormButton from '../../components/UI/SubmitFormButton.vue'
import CropperModal from '../../components/UI/CropperModal.vue'
import CroppedImage from '../../components/UI/CroppedImage.vue'

const title= ref(null)
const location = ref(null)
const description = ref(null)
const showModal = ref(false)
// const ImageData = ref(null)
const image = ref(null)

const setCroppedImageData = (data) =>{
  // ImageData = data
  image.value = data.imageUrl
}
</script>

<style lang="scss" scoped></style>
