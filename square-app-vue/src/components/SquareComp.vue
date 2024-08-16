<script setup lang="ts">
import { ref } from 'vue'

const isRed = ref('red')
</script>

<template>
  <div :class="{ red: isRed }"></div>
</template>

<style scoped>
div {
  width: 50px;
  height: 50px;
  background: green;
}

.red {
  background: red;
}

.green {
  background: green;
}
</style>
