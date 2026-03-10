<script setup>
import { ref, computed } from 'vue'

const price = ref(10)
const quantity = ref(1)

const total = computed(() => {
  return price.value * quantity.value
})
</script>

<template>
  <div>
    <h1>Computed Demo</h1>

    <label>Price</label>
    <input type="number" v-model="price">

    <label>Quantity</label>
    <input type="number" v-model="quantity">

    <h2>Total: {{ total }}</h2>
  </div>
</template>