<script setup>
import { ref, reactive, watch } from 'vue'

let x = ref(10)
let string = ref('Hallo') // ref braucht man wenn man primitiv type hat ein string oder ein zahl
const state = reactive({
  //reactive braucht man wenn man referenz types hat
  count: 0, // wenn wir count über Atribut verändern wollen dann brauchen wir keine x.value mehr bei increase stattdessen:      state.count += value
  name: 'Lana'
})

//liste darstellen
const todos = [
  { desc: 'Programieren', done: false },
  { desc: 'HTML', done: false },
  { desc: 'JS', done: true }
]

const decrease = (value) => {
  x.value -= value
}
const increase = (value) => {
  state.count += value
}

// const LargerThen = computed(() => {
//   if (state.count > 10) {
//     return 'Larger'
//   } else {
//     return 'smaller'
//   }
// })
watch(
  () => state.count,
  (newvalue, oldvalue) => {
    console.log(newvalue, oldvalue)
  }
)
</script>

<template>
  <div>
    <h2>Hallo welt</h2>
    <button v-on:click="decrease(5)">Update --</button>
    <p>{{ x }}</p>
    <button v-on:click="increase(5)">Update ++</button>
    <p>{{ string }}</p>
    <p>{{ state.name }}</p>
    <p>{{ state.count }}</p>
    <P>{{ LargerThen }}</P>
    <p v-if="state.count > 10">Larger</p>
    <p v-else>smaller</p>

    <input type="text" v-model="string" />
    <hr />
    <div v-for="item in todos" :key="item.desc">
      <p>{{ item.desc }}</p>
    </div>
  </div>
</template>
