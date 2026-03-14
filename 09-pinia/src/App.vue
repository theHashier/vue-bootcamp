<script setup>
import { useCounterStore } from "./stores/counter"

const counter = useCounterStore()
</script>

<template>
  <main>
    <h1>Pinia Global Counter</h1>

    <h2>{{ counter.count }}</h2>

    <button @click="counter.increment()">+</button>
    <button @click="counter.decrement()">-</button>
  </main>
</template>

<style scoped>
main {
  max-width: 500px;
  margin: 40px auto;
  text-align: center;
  background: lightblue;
}

button {
  margin: 10px;
  padding: 10px 16px;
}
</style>