<script setup>
import {ref} from 'vue';

const nValue = ref(0);
const piResult = ref("");

//Calculate Pi approximation 
function calculatePi () {
  let piApproximation = 0;
  for (let i = 0; i < nValue.value; i++) {
    piApproximation += (4 * (-1) ** i) / (2 * i + 1);
  }
  piResult.value = "Pi ≈ " + piApproximation.toFixed(5);
}
</script>

<template>
    <form @submit.prevent="calculatePi">
      <h2>Gregory-Leibniz Pi Approximation</h2>
      <label>n Value:</label>
      <input type="number" v-model="nValue" />
      <label>Pi Approximation (Result): </label>
      <input type="text" :value="piResult" readonly/>
      <button type="submit">Calculate Pi</button>
    </form>
  </template>
  
  <style scoped>

  </style>
  
  