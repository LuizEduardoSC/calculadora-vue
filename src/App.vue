<script>
export default {
  data() {
    return {
      numero1: 0,
      numero2: 0,
      operacao: '+',
    };
  },
  computed: {
    resultado() {
      switch (this.operacao) {
        case '+':
          return this.numero1 + this.numero2;
        case '-':
          return this.numero1 - this.numero2;
        case '*':
          return this.numero1 * this.numero2;
        case '/':
          return this.numero2 !== 0 ? this.numero1 / this.numero2 : 'Erro: divisão por zero';
        default:
          return 0;
      }
    },
  },
};

</script>

<template>
  <div class="calculadora">
    <h1>Calculadora Aritmética</h1>

    <input type="number" v-model.number="numero1" placeholder="Número 1" />
    <input type="number" v-model.number="numero2" placeholder="Número 2" />

    <select v-model="operacao">
      <option value="+">Adição (+)</option>
      <option value="-">Subtração (-)</option>
      <option value="*">Multiplicação (*)</option>
      <option value="/">Divisão (/)</option>
    </select>

    <p>Resultado: {{ resultado }}</p>
  </div>

</template>

<style scoped>
.calculadora {
  max-width: 400px;
  margin: auto;
  text-align: center;
}

input,
select {
  margin: 10px;
  padding: 5px;
}
</style>
