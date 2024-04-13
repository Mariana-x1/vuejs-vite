<script setup>
import { ref } from 'vue'
let x = ref(10)

const decrease = () => {
  x.value -= 1
}
const increase = () => {
  x.value += 1
}
</script>

<template>
  <div>
    <h2>Hallo welt</h2>
    <button v-on:click="decrease">Update --</button>
    <p>{{ x / 2 }}</p>
    <button v-on:click="increase">Update ++</button>
  </div>
</template>
