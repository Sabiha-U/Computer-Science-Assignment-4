<script setup>
import {ref} from 'vue';

const sideA = ref(0);
const sideB = ref(0);
const angleC = ref(0);
const cosineResult = ref(0);

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
      <input type="number" :value="cosineResult.toFixed(2)" readonly /> 
      <button type="submit">Calculate Side C</button>
    </form>
  </template>

  <style scoped>
/* Button styling */
button {
    padding: 10px 20px;
    background-color: #bf90ca;
    color: white;
    border: none;
    border-radius: 6px;
    font-size: 16px;
    cursor: pointer;
    margin-top: 10px;
    transition: background-color 0.3s ease;
}

button:hover {
    background-color: #c454b1;
}

/* Styling for result or message paragraphs */
p {
    margin-top: 10px;
    color: #c454b1;
}

/* Style for text and number inputs */
input[type="number"], input[type="text"] {
    width: 91%;
    padding: 10px;
    margin: 5px 0;
    border: 1px solid #dfb8ee;
    border-radius: 5px;
    font-size: 14px;
    color: #000000;
    transition: border-color 0.3s ease;
}

/* Focus style for number inputs */
input[type="number"]:focus, input[type="text"]:focus {
    border-color: #bf90ca;
    outline: none;
}

/* Subtitle for each box */
h2 {
    color: #000000;
    margin-bottom: 15px;
    font-size: 1.5em;
    text-align: center;
}
  </style>
  