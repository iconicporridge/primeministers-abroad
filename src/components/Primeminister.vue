<template>
  <div class="card">
    <h1>{{ primeminister.name }}</h1>
    <p>Entered Office: {{ primeminister.enteredOffice }}</p>
    <p>Left Office: {{ primeminister.leftOffice }}</p>
    <p>UK Description: {{ primeminister.ukDescription }}</p>
    <p>Foreign Perspectives:</p>
    <div class="card-deck">
      <div
        v-for="perspective of primeminister.foreignPerspectives"
        :key="perspective"
        class="card"
      >
        <div class="card-body">
          <p class="card-text">{{ perspective }}</p>
        </div>
      </div>
    </div>
  </div>
</template>
<script setup>
import { defineProps } from "vue";

const { primeminister } = defineProps({
  primeminister: {
    type: Object,
    required: true,
  },
});
</script>

<style scoped></style>
