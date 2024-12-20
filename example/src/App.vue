
<script setup lang="ts">

import { ref } from 'vue'
import NumberFlip from 'vue-number-flip'

const value = ref(0.0)
const input = ref(0.0)

const set = () => {
  value.value = parseFloat(input.value as unknown as string)
}

</script>

<template>
  <NumberFlip class="flip" :value="value" :formatter="(n: Number) => n.toFixed(2)"/>
  <form @submit.prevent>
    <input v-model="input" autofocus />
    <button @click="set">Set Value</button>
  </form>
</template>

<style>
@import '../node_modules/vue-number-flip/dist/index.css';
</style>

<style scoped>
.flip {
  font-size: 2em;
}

form {
  margin-top: 1rem;
  border-top: 1px solid #ccc;
  padding-top: 0.5rem;
  display: flex;
  flex-direction: row;
  gap: .5rem;
}

</style>
