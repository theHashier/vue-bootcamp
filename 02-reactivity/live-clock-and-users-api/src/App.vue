<script setup>
import { ref, onMounted } from "vue"

const time = ref("")
const users = ref([])

function updateClock() {
  const now = new Date()
  time.value = now.toLocaleTimeString()
}

async function loadUsers() {
  const res = await fetch("https://jsonplaceholder.typicode.com/users")
  users.value = await res.json()
}

onMounted(() => {
  updateClock()
  setInterval(updateClock, 1000)
  loadUsers()
})
</script>

<template>
  <main class="wrap">
    <h1>Vue Bootcamp</h1>
    <p class="sub">Lab 02 — Live Reactivity</p>

    <section class="clock">
      <h2>Current Time</h2>
      <p class="time">{{ time }}</p>
    </section>

    <section class="users">
      <h2>Users from API</h2>
      <ul>
        <li v-for="u in users" :key="u.id">
          {{ u.name }} — {{ u.email }}
        </li>
      </ul>
    </section>
  </main>
</template>

<style scoped>
.wrap {
  max-width: 720px;
  margin: 40px auto;
  padding: 0 16px;
}

.clock {
  margin-top: 20px;
}

.time {
  font-size: 28px;
  font-weight: bold;
}

.users {
  margin-top: 30px;
}
</style>