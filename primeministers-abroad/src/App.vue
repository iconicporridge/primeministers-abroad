<script setup>
import { ref } from 'vue'
import Primeminister from './components/Primeminister.vue'
import Timeline from './components/Timeline.vue'
import primeministers from './primeministers.json'

const selectedPrimeminister = ref(primeministers[0])

function updatePrimeminister(primeminister) {
  selectedPrimeminister.value = primeminister
}
</script>

<template>
  <Primeminister :primeminister="selectedPrimeminister" class="container" />
  <Timeline @primeMinisterSelected="updatePrimeminister" />
</template>
