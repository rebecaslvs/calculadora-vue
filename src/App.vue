<template>
  <div id="app">
    <h1>Calculadora Aritmética</h1>
    <div>
      <input type="number" v-model.number="number1" placeholder="Número 1" />
      <select v-model="operation">
        <option value="add">+</option>
        <option value="subtract">-</option>
        <option value="multiply">*</option>
        <option value="divide">/</option>
      </select>
      <input type="number" v-model.number="number2" placeholder="Número 2" />
    </div>
    <div>
      <h2>Resultado: {{ result }}</h2>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      number1: 0,
      number2: 0,
      operation: 'add'
    };
  },
  computed: {
    result() {
      switch (this.operation) {
        case 'add':
          return this.number1 + this.number2;
        case 'subtract':
          return this.number1 - this.number2;
        case 'multiply':
          return this.number1 * this.number2;
        case 'divide':
          return this.number2 !== 0 ? this.number1 / this.number2 : 'Erro: Divisão por zero';
        default:
          return 0; // Valor de fallback
      }
    }
  }
};
</script>

<style>
#app {
  text-align: center;
  margin-top: 50px;
}

input, select {
  margin: 10px;
  padding: 5px;
  font-size: 16px;
}
</style>
