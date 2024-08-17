<script setup lang="ts">
import { computed } from 'vue'

const props = defineProps({
  color: String,
  id: String
})

const emit = defineEmits(['changeColor'])

function changeLocalColor() {
  emit('changeColor', { newColor: props.color, id: props.id })
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
}

.red-square {
  background: red;
}

.green-square {
  background: green;
}
</style>
