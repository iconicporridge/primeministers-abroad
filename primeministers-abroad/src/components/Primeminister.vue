<template>
  <div>
    <h1>{{ primeminister.name }}</h1>
    <p>Entered Office: {{ primeminister.enteredOffice }}</p>
    <p>Left Office: {{ primeminister.leftOffice }}</p>
    <p>UK Description: {{ primeminister.ukDescription }}</p>
    <p>Foreign Perspectives: {{ primeminister.foreignPerspectives }}</p>
  </div>
</template>

<script setup>
import { ref } from 'vue'
import primeministers from '../primeministers.json'
const primeminister = ref(primeministers[0])
</script>

<style scoped>
</style>