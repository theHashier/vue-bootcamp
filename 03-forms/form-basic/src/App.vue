<script setup>
import { ref } from "vue"

const name = ref("")
const email = ref("")
const message = ref("")

const emailError = ref("")
const submitted = ref(false)

function validateEmail() {
  const regex = /^[^\s@]+@[^\s@]+\.[^\s@]+$/

  if (!regex.test(email.value)) {
    emailError.value = "Invalid email address"
  } else {
    emailError.value = ""
  }
}

function submitForm() {
  validateEmail()

  if (!name.value || !email.value || !message.value || emailError.value) {
    return
  }

  submitted.value = true

  console.log({
    name: name.value,
    email: email.value,
    message: message.value
  })
}
</script>

<template>
  <main class="wrap">
    <h1>Contact Form</h1>

    <form @submit.prevent="submitForm">

      <label>Name</label>
      <input v-model="name" type="text">

      <label>Email</label>
      <input v-model="email" type="email" @blur="validateEmail">

      <p class="error" v-if="emailError">{{ emailError }}</p>

      <label>Message</label>
      <textarea v-model="message"></textarea>

      <button type="submit">Send</button>

    </form>

    <p class="success" v-if="submitted">Form submitted successfully</p>
  </main>
</template>

<style scoped>
.wrap {
  max-width: 600px;
  margin: 40px auto;
}

form {
  display: flex;
  flex-direction: column;
  gap: 10px;
}

input, textarea, button {
  width: 100%;
  padding: 8px;
}

button {
  background: black;
  color: white;
  width: 50%;
  padding: 10px;
  margin: 15px auto 0;
  display: block;
  text-align: center;
  border: none;
  cursor: pointer;
}

.error {
  color: red;
}

.success {
  color: green;
}
</style>