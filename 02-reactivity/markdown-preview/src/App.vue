<script setup>
import { ref } from "vue"

const text = ref(`# Hello

Type **Markdown** here...

- Vue
- Reactivity
- Live preview
`)
</script>

<template>
  <main class="wrap">
    <h1>Vue Bootcamp</h1>
    <p class="sub">Lab 02 — Markdown Live Preview</p>

    <div class="grid">
      <textarea v-model="text"></textarea>

      <div class="preview">
        <pre>{{ text }}</pre>
      </div>
    </div>
  </main>
</template>

<style scoped>
.wrap {
  max-width: 900px;
  margin: 40px auto;
  padding: 0 16px;
}

.grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 20px;
  margin-top: 20px;
}

textarea {
  min-height: 300px;
  padding: 12px;
  font-size: 14px;
}

.preview {
  border: 1px solid rgba(0,0,0,0.1);
  padding: 12px;
  border-radius: 8px;
}
</style>