<script setup lang="ts">
import { ref } from 'vue'
import SquareComp from './components/SquareComp.vue'

const squares = ref([
  {
    id: crypto.randomUUID(),
    color: 'green'
  },
  {
    id: crypto.randomUUID(),
    color: 'red'
  },
  {
    id: crypto.randomUUID(),
    color: 'red'
  },
  {
    id: crypto.randomUUID(),
    color: 'green'
  }
])

const updateSquareColor = (id: string, newColor: string) => {
  const square = squares.value.find((s) => s.id === id)
  if (square) {
    square.color = newColor
  }
}
</script>

<template>
  <main>
    <SquareComp
      v-for="square in squares"
      :key="square.id"
      :id="square.id"
      :color="square.color"
      @changeColor="updateSquareColor(square.id, $event)"
    ></SquareComp>
  </main>
</template>

<style scoped>
header {
  line-height: 1.5;
}

main {
  display: flex;
  flex-direction: column;
  gap: 2rem;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}
</style>
