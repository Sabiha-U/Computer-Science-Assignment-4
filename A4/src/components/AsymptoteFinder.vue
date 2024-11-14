<script setup>
import {ref} from 'vue';

const mValue = ref(0);
const nValue = ref(0);
const asymptoteResult = ref("");

//this function determines the aysmptote type based on m and n values
function findAsymptote () {
  if (mValue.value === nValue.value) {  //chesk if m and n are equal for horizontal asymptote
    asymptoteResult.value = "The asymptote is horizontal."
  } else if (mValue.value < nValue.value) { //checks if m and n are similar for a vertical asymptote
    asymptoteResult.value = "The asymptote is the x-axis.";
  } else {
    const difference = mValue.value - nValue.value;
    const names = ["Linear", "Quadratic", "Cubic", "Quartc", "Quintic", "Sextic", "Septic", "Octic", "Nonic", "Decic"];
    asymptoteResult.value = "The asymptote is " + names[difference - 1];
  }
}
</script>

<template>
    <form @submit.prevent="findAsymptote">
      <h2>Asymptote Finder</h2>
      <label>m Value:</label>
      <input type="number" v-model="mValue" />
      <label>n Value:</label>
      <input type="number" v-model="nValue" />
      <label>Asymptote Result:</label>
      <input type="text" :value="asymptoteResult" readonly />
      <button type="submit">Find Asymptote</button>
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
  