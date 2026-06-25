<template>
  <div>
    <h2>Timeline</h2>
    <div class="timeline-bar">
      <div v-for="(primeminister, index) in primeministers" :key="primeminister.name" :style="{ width: calculateBarWidth(primeminister), backgroundColor: index % 2 === 0 ? '#ffffff' : '#cccccc' }" :title="primeminister.name + ' (' + primeminister.enteredOffice + ' - ' + primeminister.leftOffice + ')' " @click="$emit('primeMinisterSelected', primeminister)"></div>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue'
import primeministers from '../primeministers.json'

const primeministersData = ref(primeministers)

const totalDuration = () => {
  const firstPrimeminister = primeministers[0]
  const firstDate = Date.parse(firstPrimeminister.enteredOffice)
  const now = Date.now()
  return now - firstDate
}

function calculateBarWidth(primeminister) {
  const enteredDate = Date.parse(primeminister.enteredOffice)
  let leftDate
  if (primeminister.leftOffice === 'present') {
    leftDate = Date.now()
  } else {
    leftDate = Date.parse(primeminister.leftOffice)
  }
  const duration = leftDate - enteredDate
  return (duration / totalDuration()) * 100 + '%'
}
</script>

<style scoped>
.timeline-bar {
  display: flex;
  width: 100%;
  height: 20px;
  border: 1px solid #ddd;
}

.timeline-bar div {
  height: 100%;
}
</style>