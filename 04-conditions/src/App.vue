<script setup>
import { ref } from "vue"

const showSecret = ref(false)
const loggedIn = ref(false)
const showMenu = ref(false)
const loading = ref(true)

function toggleSecret() {
  showSecret.value = !showSecret.value
}

function login() {
  loggedIn.value = true
}

function logout() {
  loggedIn.value = false
}

function toggleMenu() {
  showMenu.value = !showMenu.value
}

setTimeout(() => {
  loading.value = false
}, 2000)
</script>

<template>
  <main class="wrap">
    <h1>Vue Bootcamp</h1>
    <p class="sub">Lab 04 — Conditions</p>

    <section>
      <h2>1. Toggle Content (v-if)</h2>
      <button @click="toggleSecret">Toggle Secret</button>

      <p class="panic" v-if="showSecret">
        Secret content visible...Oh no!!!
        Self destruct in 3...2...1...
      </p>
    </section>

    <section>
      <h2>2. Login Simulation (v-if / v-else)</h2>

      <div v-if="loggedIn">
        <p>You are logged in</p>
        <button @click="logout">Logout</button>
      </div>

      <div v-else>
        <button @click="login">Login</button>
      </div>
    </section>

    <section>
      <h2>3. Menu Toggle (v-show)</h2>
      <button @click="toggleMenu">Toggle Menu</button>

      <div v-show="showMenu">
        <p>Menu item 1</p>
        <p>Menu item 2</p>
        <p>Menu item 3</p>
      </div>
    </section>

    <section>
      <h2>4. Loading State</h2>

      <p v-if="loading">
        Loading data...
      </p>

      <p class="succes" v-else>
        Data loaded successfully...Oh yes!!!
      </p>
    </section>

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
  }

  section {
    margin-top: 32px;
  }

  .panic {
    margin-top: 24px;
    padding: 16px;
    background-color: #ff0000;
    color: #fff;
    font-weight: bold;
    font-size: xx-large;
  }

  .succes {
    margin-top: 24px;
    padding: 16px;
    background-color: #00ff00;
    color: #000;
    font-weight: bold;
    font-size: xx-large;
  }

  button  {
    background: #000;
    color: #fff;
    border: none;
    padding: 8px 16px;
    font-size: large;
    cursor: pointer;
  }
</style>