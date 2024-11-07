<template>
    <div class="box">
      <h2>Cosine Law</h2>
      <label>Side A:</label>
      <input type="number" v-model="sideA" />
      <label>Side B:</label>
      <input type="number" v-model="sideB" />
      <label>Angle C:</label>
      <input type="number" v-model="angleC" />
      <button @click="calculateCosineLaw">Calculate Side C</button>
      <p>{{ cosineResult }}</p>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        sideA: 0,
        sideB: 0,
        angleC: 0,
        cosineResult: "",
      };
    },
    methods: {
      calculateCosineLaw() {
        const angleInRadians = (this.angleC * Math.PI) / 180;
        const c = Math.sqrt(
          this.sideA ** 2 + this.sideB ** 2 - 2 * this.sideA * this.sideB * Math.cos(angleInRadians)
        );
        this.cosineResult = `Side C: ${c.toFixed(2)}`;
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
  