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
  piResult.value = 'Pi ≈ ${piApproximation.toFixed(5)}';
}
</script>

<template>
    <form @submit.prevent="calculatePi()">
      <h2>Gregory-Leibniz Pi Approximation</h2>
      <label>n Value:</label>
      <input type="number" v-model="nValue" />
      <lable>Pi Approximation (Result):</lable>
      <input text="number" :value="piResult" readonly />
      <button type="submit">Calculate Pi</button>
      <p>{{ piResult }}</p>
    </form>
  </template>
  
  <style scoped>
  /* Styling for the piApproximation component */
  .box {
    padding: 10px;
    background: #f0f0f0;
    border-radius: 5px;
    text-align: center;
  }
  </style>
  
  