<template>
    <div class="box">
      <h2>Gregory-Leibniz Pi Approximation</h2>
      <label>n Value:</label>
      <input type="number" v-model="nValue" />
      <button @click="calculatePi">Calculate Pi</button>
      <p>{{ piResult }}</p>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        nValue: 0,
        piResult: "",
      };
    },
    methods: {
      calculatePi() {
        let piApproximation = 0;
        for (let i = 0; i < this.nValue; i++) {
          piApproximation += (4 * (-1) ** i) / (2 * i + 1);
        }
        this.piResult = `Pi ≈ ${piApproximation.toFixed(5)}`;
      },
    },
  };
  </script>
  
  <style scoped>
  .box {
    padding: 10px;
    background: #f0f0f0;
    border-radius: 5px;
    text-align: center;
  }
  </style>
  
  