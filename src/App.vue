<script>
  export default {
  data() {
    return {
      input1: '',
      input2: '',
      operacao: '+'
    };
  },
  computed: {
    resultado() {
      switch (this.operacao) {
        case '+':
          return this.input1 + this.input2;
        case '-':
          return this.input1 - this.input2;
        case '*':
          return this.input1 * this.input2;
        case '/':
          return this.input2 === 0 ? `não é possivel dividir ${this.input1} por 0` : this.input1 / this.input2;
      }
    }
  }
};
</script>

<template>
  <div class="container">
    <header class="p-5 mb-4 mt-4 bg-dark rounded-3 text-center extra-large text-warning">
      <h1>Calculadora Aritmética</h1>
      <p>
        Realize seus cálculos
      </p>
    </header>
    <form>
      <div class="row">
        <p class="p-5 h2 pb-2 mb-4 fs-4 text-warning text-center">Digite o primeiro número, escolha o operador e digite o segundo número</p>
        <br/>
        <div class="col-3 p-5 h2 pb-2 mb-4 position-absolute top-50 start-50 translate-middle">
          <input v-model.number="input1" type="number" class="form-control text-center border border-warning">
          <div class="col">
            <select v-model="operacao" class="form-control text-center mb-4 mt-4">
              <option value="+">+</option>
              <option value="-">-</option>
              <option value="*">*</option>
              <option value="/">/</option>
            </select>
          </div>
          <input v-model.number="input2" type="number" class="form-control text-center border border-warning">
        </div>
      </div>
      <p class="position-absolute bottom-0 w-auto p-3 h2 pb-2 text-dark border-bottom border-warning">
        Resultado: <span> {{ resultado }}</span>
      </p>
    </form>
  </div>
</template>

<style scoped>
  .container {
    height: 800px;
    width:  1024px;
  }
</style>
