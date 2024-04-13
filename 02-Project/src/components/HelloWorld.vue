<script setup>
import { ref, reactive } from 'vue'
let x = ref(10)
let string = ref('Hallo')
const state = reactive({ count: 0, name: 'Lana' })

const decrease = (value) => {
  x.value -= value
}
const increase = (value) => {
  x.value += value
}
</script>

<template>
  <div>
    <h2>Hallo welt</h2>
    <button v-on:click="decrease(5)">Update --</button>
    <p>{{ x }}</p>
    <button v-on:click="increase(5)">Update ++</button>
    <p>{{ string }}</p>
    <p>{{ state.name }}</p>
    <input type="text" v-model="string" />
  </div>
</template>
