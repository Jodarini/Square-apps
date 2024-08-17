<script setup lang="ts">
import { computed } from 'vue'

const props = defineProps({
  color: String,
  id: String
})

const emit = defineEmits(['changeColor'])

function changeLocalColor() {
  const newColor = props.color === 'red' ? 'green' : 'red'
  emit('changeColor', { newColor, id: props.id })
}
const squareClass = computed(() => ({
  'red-square': props.color === 'red',
  'green-square': props.color === 'green'
}))
</script>

<template>
  <div @click="changeLocalColor" :class="squareClass"></div>
</template>

<style scoped>
div {
  width: 50px;
  height: 50px;
  background: green;
  color: red;
}

.red-square {
  background: red;
}

.green-square {
  background: green;
}
</style>
