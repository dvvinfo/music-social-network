<template>
  <div id="EditProfile" class="container max-w-4xl mx-auto pt-20 pb-20 px-6">
    <div class="text-gray-900 text-xl">Редактировать профиль</div>
    <div class="bg-green-500 w-full h-1"></div>
    <!-- Modal -->
    <CropperModal
      v-if="showModal"
      :min-aspect-ratio-prop="{ with: 8, height: 8 }"
      :max-aspect-ratio-prop="{ with: 8, height: 8 }"
      @croppedImageData="setCroppedImageData"
      @showModal="showModal = false"
    />

    <div class="flex flex-wrap mt-4 mb-6">
      <div class="w-full md:w-1/2 px-3">
        <TextInput
          label="Имя"
          :label-color="true"
          placeholder="Иван"
          v-model:input="firstName"
          input-type="text"
          :error="errors.first_name ? errors.first_name[0] : ''"
        />
      </div>
      <div class="w-full md:w-1/2 px-3">
        <TextInput
          label="Фамилия"
          :label-color="true"
          placeholder="Иванов"
          v-model:input="lastName"
          input-type="text"
          :error="errors.last_name ? errors.last_name[0] : ''"
        />
      </div>
    </div>
    <div class="flex flex-wrap mt-4 mb-6">
      <div class="w-full md:w-1/2 px-3">
        <TextInput
          label="Местоположение"
          :label-color="true"
          placeholder="Москва, Россия"
          v-model:input="location"
          input-type="text"
        />
      </div>
    </div>

    <div class="flex flex-wrap mt-4 mb-6">
      <div class="w-full md:w-1/2 px-3">
        <DisplayCropperButton
          @showModal="showModal = true"
          label="Изображение профиля"
          btn-text="Обновить изображение профиля"
        />
      </div>
    </div>

    <div class="flex flex-wrap mt-4 mb-6">
      <div class="w-full md:w-1/2 px-3">
        <CroppedImage label="Обрезанное изображение" :image="image" />
      </div>
    </div>

    <div class="flex flex-wrap mt-4 mb-6">
      <div class="w-full px-3">
        <TextArea
          label="Описание"
          placeholder="Пожалуйста, введите описание"
          v-model:description="description"
        />
      </div>
    </div>
    <div class="flex flex-wrap mt-8 mb-6">
      <div class="w-full px-3">
        <SubmitFormButton @click="updateUser" btn-text="Обновить профиль" />
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref, onMounted } from 'vue'
import { useRouter } from 'vue-router'
import axios from 'axios'
import { useUserStore } from '../../stores/user-store'
import TextInput from '../../components/UI/TextInput.vue'
import DisplayCropperButton from '../../components/UI/DisplayCropperButton.vue'
import TextArea from '../../components/UI/TextArea.vue'
import SubmitFormButton from '../../components/UI/SubmitFormButton.vue'
import CropperModal from '../../components/UI/CropperModal.vue'
import CroppedImage from '../../components/UI/CroppedImage.vue'

const userStore = useUserStore()
const router = useRouter()

const firstName = ref(null)
const lastName = ref(null)
const location = ref(null)
const description = ref(null)
const showModal = ref(false)
// const ImageData = ref(null)
const image = ref(null)
const errors = ref([])

onMounted(() => {
  firstName.value = userStore.firstName || null
  lastName.value = userStore.lastName || null
  location.value = userStore.location || null
  description.value = userStore.description || null
  image.value = userStore.image || null
})

const setCroppedImageData = (data) => {
  // ImageData = data
  image.value = data.imageUrl
}

const updateUser = async () => {
  errors.value = []

  let data = new FormData()
  data.append('first_name', firstName.value || '')
  data.append('last_name', lastName.value || '')
  data.append('location', location.value || '')
  data.append('description', description.value || '')

  try {
    await axios.post('/api/users/' + userStore.id + '?_method=PUT', data)
    await userStore.fetchUser()

    router.push('/account/profile')
  } catch (err) {
    errors.value = err.response.data.errors
  }
}
</script>

<style lang="scss" scoped></style>
