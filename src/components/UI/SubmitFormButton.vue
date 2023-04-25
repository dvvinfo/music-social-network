<template>
  <button
    @click="$emit('submit', true)"
    class="float-right mt-2 inline-block bg-green-500 hover:bg-green-700 font-bold text-white no-underline px-4 py-3"
  >
    {{ btnText }}
  </button>
</template>

<script setup>
import { toRefs } from 'vue'
const props = defineProps({
  btnText: {
    type: String
  }
})
const { btnText } = toRefs(props)
</script>

<style lang="scss" scoped></style>
