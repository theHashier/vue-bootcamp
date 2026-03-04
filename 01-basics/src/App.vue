<script setup>
import ProfileCard from "./components/ProfileCard.vue"
</script>

<template>
  <main class="wrap">
    <h1>Vue Bootcamp</h1>
    <p class="sub">Lab 01 — basics</p>

    <ProfileCard
      name="Eugen"
      title="Junior Frontend-Developer and AWS Architect"
      :skills="['AWS', 'Terraform', 'Docker', 'Linux', 'Vue.js', 'HTML', 'CSS', 'JavaScript', 'Python']"
    />
  </main>
</template>

<style scoped>
.wrap {
  max-width: 720px;
  margin: 48px auto;
  padding: 0 16px;
}
.sub {
  opacity: 0.7;
  margin-top: -8px;
}
</style>