<script setup>
import { ref } from "vue"

const count = ref(0)

function increase() {
  count.value++
}

function decrease() {
  count.value--
}
</script>

<template>
  <main class="wrap">
    <h1>Vue Bootcamp</h1>
    <p class="sub">Lab 02 — Reactivity</p>

    <h2>{{ count }}</h2>

    <div class="buttons">
      <button @click="decrease">-</button>
      <button @click="increase">+</button>
    </div>
  </main>
</template>

<style scoped>
.wrap {
  max-width: 720px;
  margin: 48px auto;
  padding: 0 16px;
  text-align: center;
}

.buttons {
  display: flex;
  justify-content: center;
  gap: 12px;
}

button {
  padding: 10px 16px;
  font-size: 18px;
}
</style>