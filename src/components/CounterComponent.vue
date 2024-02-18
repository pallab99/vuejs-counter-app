<template>
  <main class="main-wrapper">
    <div class="main-content">
      <h1 class="title">{{ title }}</h1>
      <p>This is a simple example of a Vue.js component.</p>
      <h1>{{ count }}</h1>
      <div class="button-div">
        <button @click="subtractByOne()">-</button>
        <button @click="incrementByOne()">+</button>
        <button @click="increamentByValue(value)">{{ value }}</button>
      </div>
    </div>
  </main>
</template>

<script setup>
defineProps({
  title: {
    type: String,
    required: true
  }
})

import { ref } from 'vue'

const count = ref(0)
const value = ref(10)

const incrementByOne = () => {
  count.value++
}
const subtractByOne = () => {
  if (count.value > 0) count.value--
}
const increamentByValue = () => {
  count.value += value.value
}
</script>
<style scoped>
.main-wrapper {
  width: 100dvw;
  height: 100dvh;
  background-color: aliceblue;
  display: grid;
  place-items: center;
}
.main-content {
  text-align: center;
}
.title {
  margin-bottom: 1vw;
}
.button-div {
  display: flex;
  gap: 2vw;
  justify-content: center;
}
button {
  height: 50px;
  width: 60px;
}
</style>
