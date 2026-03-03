<script setup>
const props = defineProps({
  name: { type: String, required: true },
  title: { type: String, required: true },
  skills: { type: Array, required: true }
})
</script>

<template>
  <section class="card">
    <div class="top">
      <div class="avatar">{{ name.slice(0, 1).toUpperCase() }}</div>
      <div>
        <h2>{{ name }}</h2>
        <p class="title">{{ title }}</p>
      </div>
    </div>

    <h3>Skills</h3>
    <ul class="skills">
      <li v-for="s in skills" :key="s">{{ s }}</li>
    </ul>
  </section>
</template>

<style scoped>
.card {
  margin-top: 24px;
  border: 1px solid rgba(0, 0, 0, 0.12);
  border-radius: 14px;
  padding: 16px;
}
.top {
  display: flex;
  flex-direction: column;
  gap: 12px;
  align-items: center;
  margin-bottom: 12px;
}
.avatar {
  width: 44px;
  height: 44px;
  border-radius: 999px;
  border: 1px solid rgba(0, 0, 0, 0.12);
  display: grid;
  place-items: center;
  font-weight: 700;
}
.title {
  opacity: 0.75;
  margin: 4px 0 0;
}
.skills {
  display: flex;
  flex-wrap: wrap;
  gap: 8px;
  padding: 0;
  list-style: none;
}
.skills li {
  border: 1px solid rgba(0, 0, 0, 0.12);
  border-radius: 999px;
  padding: 6px 10px;
}
</style>