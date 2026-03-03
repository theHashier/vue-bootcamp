<script setup>
import ProfileCard from "./components/ProfileCard.vue"
</script>

<template>
  <main class="wrap">
    <h1>Vue Bootcamp</h1>
    <p class="sub">Lab 01 — basics</p>

    <ProfileCard
      name="Eugen"
      title="Junior DevOps / Cloud"
      :skills="['AWS', 'Terraform', 'Docker', 'Linux']"
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