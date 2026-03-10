<script setup>
import { ref } from "vue"

const count = ref(0)

function change(amount) {
  count.value += amount
}

function reset() {
  count.value = 0
}
</script>

<template>
  <main>
    <h1>Lab 06 — Events</h1>

    <h2>{{ count }}</h2>

    <button @click="change(-1)">-1</button>
    <button @click="change(1)">+1</button>
    <button @click="change(5)">+5</button>
    <button v-on:click="reset">reset</button>
  </main>
</template>