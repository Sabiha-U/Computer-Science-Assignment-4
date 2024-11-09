<script setup>
import {ref} from 'vue';

const sideA = ref(0);
const sideB = ref(0);
const angleC = ref(0);
const cosineResult = ref("");

//the function to calculate side C using the cosine law formula
function calculateCosineLaw() {
const angleInRadians = (angleC.value * Math.Pi) / 180;
const c = Math.sqrt (sideA**2 + sideB**2 - 2 * sideA.value * sideB.value * Math.cos(angleInRadians));
}
</script>

<template>
    <form @submit.prevent="calculateCosineLaw()">
      <h2>Cosine Law</h2>
      <label>Side A:</label>
      <input type="number" v-model="sideA" />
      <label>Side B:</label>
      <input type="number" v-model="sideB" />
      <label>Angle C:</label>
      <input type="number" v-model="angleC" />
      <button @click="calculateCosineLaw">Calculate Side C</button>
      Side C: {{ cosineResult.value.toFixed(2)}}
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
  