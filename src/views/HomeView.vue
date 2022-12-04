<script setup>
import { ref } from "vue"
import axios from "axios"

const email = ref("")
const pw = ref("")

const submit = async () => {
  try {
    const { data } = await axios.post(
      "http://localhost:4050/new",
      { name: "Abeer" },
      { withCredentials: true }
    )

    console.log(data)
  } catch (error) {
    console.log(error)
  }
}
</script>

<template>
  <input type="text" placeholder="email" v-model="email" />
  <input type="password" placeholder="password" v-model="pw" />
  <button @click="submit">Submit</button>
</template>

<style></style>
