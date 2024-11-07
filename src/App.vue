<template>
  <div class="container">
    <h1>Assignment 4 - Vue Components</h1>
    <CosineLaw />
    <AsymptoteFinder />
    <GregoryLeibnizPi />
  </div>
</template>

<script>
import CosineLaw from './components/CosineLaw.vue';
import AsymptoteFinder from './components/AsymptoteFinder.vue';
import GregoryLeibnizPi from './components/GregoryLeibnizPi.vue';

export default {
  components: {
    CosineLaw,
    AsymptoteFinder,
    GregoryLeibnizPi,
  },
};
</script>

<style>
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
.container {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 20px;
    width: 60%;
    max-width: 900px;
    padding: 20px;
    background-color: #d4e4f4;
    border-radius: 20px;
}
.box {
    padding: 20px;
    background: rgb(250, 243, 250);
    border-radius: 10px;
    box-shadow: 0px 4px 8px rgba(0, 0, 0, 0.1);
    display: flex;
    flex-direction: column;
    align-items: center;
}
h1 {
    grid-column: span 2;
    text-align: center;
    margin: 0 0 20px;
    color: #000000;
}
h2 {
    color: #000000;
    margin-bottom: 15px;
}
input[type="number"] {
    width: 80%;
    padding: 8px;
    margin: 5px 0;
    border: 1px solid #dfb8ee;
    border-radius: 5px;
    font-size: 14px;
}
button {
    padding: 8px 17px;
    background-color: #bf90ca;
    color: white;
    border: none;
    border-radius: 6px;
    font-size: 16px;
    cursor: pointer;
    margin-top: 10px;
}
button:hover {
    background-color: #c454b1;
}
p {
    margin-top: 10px;
    color: #c454b1;
}
</style>
