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
import { defineProps } from 'vue'

const { primeminister } = defineProps({
  primeminister: {
    type: Object,
    required: true
  }
})
</script>

<style scoped>
</style>