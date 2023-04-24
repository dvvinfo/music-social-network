<template>
  <RouterLink
    :to="url"
    class="float-right bg-transparent text-gray-900 font-semibold hover:text-white py-2 px-4 border hover:border-transparent rounded  border-green-500"
    :class="[color ? 'hover:bg-' + color + '-500 border-' + color + '-500' : '']"
  >
    {{ btnText }}
  </RouterLink>
</template>

<script setup>
import { toRefs } from 'vue'
const props = defineProps({
  btnText: {
    type: String
  },
  url: {
    type: String,
    default: ''
  },
  color: {
    type: String
  },
})
const { btnText,url } = toRefs(props)
</script>

<style lang="scss" scoped></style>
