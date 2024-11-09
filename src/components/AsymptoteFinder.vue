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
    const names = ["Linear", "Quadratic", "Cubic", "Quartic", "Quintic"];
    asymptoteResult.value = "The asymptote is" + names[difference - 1];
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
  /* Styling for the Asymptote component */
  .box {
    padding: 10px;
    background: #f0f0f0;
    border-radius: 5px;
    text-align: center;
  }
  </style>
  