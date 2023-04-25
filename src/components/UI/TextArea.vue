<template>
  <label class="block uppercase tracking-wide text-gray-900 text-xs font-bold mb-2">
    {{ label }}
  </label>
  <textarea
    v-model="descriptionComputed"
    class="appearance-none block w-full bg-white text-gray-700 border border-gray-400 rounded py-3 px-4 leading-tight focus:outline-none focus:bg-white focus:border-gray-500"
    cols="30"
    rows="10"
    :placeholder="placeholder"
  ></textarea>
  <span v-if="error" class="text-red-500">{{ error }}</span>
</template>

<script setup>
import { toRefs, computed } from 'vue'
const props = defineProps({
  label: {
    type: String
  },
  btnText: {
    type: String
  },
  description: {
    type: String
  },
  placeholder: {
    type: String,
    default: ''
  },
  error: {
    type: String
  }
})
const { label, description, placeholder, error } = toRefs(props)
const emit = defineEmits(['update:description'])

const descriptionComputed = computed({
  get: () => description.value,
  set: (val) => emit('update:description', val)
})
</script>

<style lang="scss" scoped></style>
