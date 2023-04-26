<template>
  <label class="block uppercase tracking-wide text-xs font-bold mb-2 text-gray-900">
    {{ label }}
  </label>
  <img class="rounded w-full border-solid border-4 border-green-500" :src="image" alt="" />
</template>

<script setup>
import { toRefs } from 'vue'

const props = defineProps({
  label: {
    type: String
  },
  image: {
    type: String
  }
})

const { label, image } = toRefs(props)
</script>

<style lang="scss" scoped></style>
