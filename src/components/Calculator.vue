<template>
    <div class="container">
        <div>
    <h1>Calculadora Simples</h1>
    <div>
      <input v-model="num1" type="number" placeholder="Número 1" />
      <select v-model="operator">
        <option value="+">+</option>
        <option value="-">-</option>
        <option value="*">*</option>
        <option value="/">/</option>
      </select>
      <input v-model="num2" type="number" placeholder="Número 2" />
    </div>
    <div>
      <p>Resultado: {{ result }}</p>
    </div>
  </div>
    </div>
  </template>
  
  <script>
 export default {
  data() {
    return {
      num1: 0,
      num2: 0,
      operator: '+',
      result: 0,
    };
  },
  watch: {
    num1: 'calculate',
    num2: 'calculate',
    operator: 'calculate',
  },
  methods: {
    calculate() {
      const n1 = parseFloat(this.num1);
      const n2 = parseFloat(this.num2);

      switch (this.operator) {
        case '+':
          this.result = n1 + n2;
          break;
        case '-':
          this.result = n1 - n2;
          break;
        case '*':
          this.result = n1 * n2;
          break;
        case '/':
          this.result = n1 / n2;
          break;
        default:
          this.result = 0;
      }
    },
  },
};
  </script>
  
  <style scoped>
  
  </style>
  