<template>
    <div class="box">
      <h2>Asymptote Finder</h2>
      <label>m Value:</label>
      <input type="number" v-model="mValue" />
      <label>n Value:</label>
      <input type="number" v-model="nValue" />
      <button @click="findAsymptote">Find Asymptote</button>
      <p>{{ asymptoteResult }}</p>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        mValue: 0,
        nValue: 0,
        asymptoteResult: "",
      };
    },
    methods: {
      findAsymptote() {
        if (this.mValue === this.nValue) {
          this.asymptoteResult = "The asymptote is horizontal.";
        } else if (this.mValue < this.nValue) {
          this.asymptoteResult = "The asymptote is the x-axis.";
        } else {
          const difference = this.mValue - this.nValue;
          const names = ["Linear", "Quadratic", "Cubic", "Quartic", "Quintic"];
          this.asymptoteResult = `The asymptote is ${names[difference - 1]}`;
        }
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
  