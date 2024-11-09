<script setup>
import {ref} from 'vue';

const sideA = ref(0);
const sideB = ref(0);
const angleC = ref(0);
const cosineResult = ref("");

//the function to calculate side C using the cosine law formula
function calculateCosineLaw() {
  const angleInRadians = (angleC.value * Math.PI) / 180;
  cosineResult.value = Math.sqrt (sideA.value**2 + sideB.value**2 - 2 * sideA.value * sideB.value * Math.cos(angleInRadians));
}
</script>

<template>
    <form @submit.prevent="calculateCosineLaw">
      <h2>Cosine Law</h2>
      <label>Side A:</label>
      <input type="number" v-model="sideA" />
      <label>Side B:</label>
      <input type="number" v-model="sideB" />
      <label>Angle C:</label>
      <input type="number" v-model="angleC" />
      <label> Side C (Result): </label>
      <p> Side C: {{ cosineResult.toFixed(2) }}</p> <!---displays cosine result--->
      <button type="submit">Calculate Side C</button>
    </form>
  </template>

  <style scoped>
  /* Styling for the Cosine Law component */
  .box {
    padding: 10px;
    background: #f0f0f0;
    border-radius: 5px;
    text-align: center;
  }
  </style>
  