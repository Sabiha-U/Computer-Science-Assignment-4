<script setup>
import { ref } from 'vue';
import CosineLaw from './components/CosineLaw.vue';
import AsymptoteFinder from './components/AsymptoteFinder.vue';
import GregoryLeibnizPi from './components/GregoryLeibnizPi.vue';
</script>

<template>
  <div class="container">
    <h1>Assignment 4 - Vue Components</h1>

    <div class="box">
      <CosineLaw />
    </div>

    <div class="box">
      <AsymptoteFinder />
    </div>

    <div class="box">
      <GregoryLeibnizPi />
    </div>

  </div>
</template>

<style>
/* Main styling for layout and background */
body {
  font-family: 'Trebuchet MS', 'Lucida Sans Unicode', 'Lucida Grande', 'Lucida Sans', Arial, sans-serif;
  color: #000000;
  background-color: #d4e4f4;
  margin: 0;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  min-height: 100vh;
}

/* Container layout */
.container {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  /* 2 equal columns */
  gap: 20px;
  width: 80%;
  max-width: 900px;
  padding: 20px;
  border-radius: 20px;
}

/* Main title */
h1 {
  grid-column: span 2;
  text-align: center;
  margin: 0 0 20px;
  color: #000000;
  font-size: 2em;
  font-weight: bold;
}

/* Box style for individual sections */
.box {
  padding: 20px;
  background-color: #f7ecfb;
  border-radius: 10px;
  box-shadow: 0px 4px 8px rgba(0, 0, 0, 0.1);
  display: flex;
  flex-direction: column;
  align-items: center;
}
</style>
