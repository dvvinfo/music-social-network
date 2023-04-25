<template>
    <label class="block uppercase tracking-wide text-gray-900 text-xs font-bold">
        {{ label }}
    </label>
    <button
      @click="$emit('showModal', true)"
      class=" mt-2 inline-block bg-green-500 hover:bg-green-700 font-bold text-white no-underline px-4 py-3"
    >
      {{ btnText }}
    </button>
  </template>
  
  <script setup>
  import { toRefs } from 'vue'
  const props = defineProps({
    btnText: {
      type: String
    },
    label: {
      type: String
    },
  })
  const { btnText,label } = toRefs(props)
  </script>
  
  <style lang="scss" scoped></style>
  