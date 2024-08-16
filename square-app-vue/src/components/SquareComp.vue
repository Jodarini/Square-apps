<script setup lang="ts">
import { ref } from 'vue'
const props = defineProps({
  color: String
})

const isRed = ref(props.color === 'red')
</script>

<template>
  <div :class="{ red: isRed }"></div>
</template>

<style scoped>
div {
  width: 50px;
  height: 50px;
  background: green;
  color: red;
}

.red {
  background: red;
}

.green {
  background: green;
}
</style>
