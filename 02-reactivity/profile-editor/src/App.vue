<script setup>
import { ref } from "vue"

const name = ref("Eugen")
const title = ref("Junior Cloud / DevOps Engineer")
</script>

<template>
  <main class="wrap">
    <h1>Vue Bootcamp</h1>
    <p class="sub">Lab 02 — Profile Editor</p>

    <div class="form">
      <input v-model="name" placeholder="Your name" />
      <input v-model="title" placeholder="Your title" />
    </div>

    <section class="card">
      <h2>{{ name }}</h2>
      <p>{{ title }}</p>
    </section>
  </main>
</template>

<style scoped>
.wrap {
  max-width: 720px;
  margin: 48px auto;
  padding: 0 16px;
}

.form {
  display: flex;
  flex-direction: column;
  gap: 12px;
  margin-top: 20px;
}

input {
  padding: 10px;
  font-size: 16px;
}

.card {
  margin-top: 24px;
  border: 1px solid rgba(0,0,0,0.12);
  padding: 16px;
  border-radius: 10px;
}
</style>