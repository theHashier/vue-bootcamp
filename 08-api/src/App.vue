<script setup>
import { ref } from "vue"

const username = ref("")
const user = ref(null)

async function fetchUser() {
  const res = await fetch(`https://api.github.com/users/${username.value}`)
  const data = await res.json()
  user.value = data
}
</script>

<template>
  <main>
    <h1>GitHub User Viewer</h1>

    <input v-model="username" placeholder="Enter GitHub username" />

    <button @click="fetchUser">
      Load User
    </button>

    <div v-if="user">
      <img :src="user.avatar_url" width="100" />
      <h2>{{ user.login }}</h2>
      <p>Followers: {{ user.followers }}</p>
      <p>Repos: {{ user.public_repos }}</p>
    </div>
  </main>
</template>

<style scoped>
main {
  max-width: 500px;
  margin: 40px auto;
  text-align: center;
}

input {
  padding: 8px;
  margin-right: 10px;
}
</style>