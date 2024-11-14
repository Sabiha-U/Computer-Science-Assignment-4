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
  
  