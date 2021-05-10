<template>
  <div class="main">
    <div class="calculator">
      <input v-model.number="operand1"/>
      <input v-model.number="operand2"/>
      <span class="result">= {{ result }}</span>
    </div>
    <div class="function">
      <button @click="calculator($event)">-</button>
      <button @click="calculator($event)">+</button>
      <button @click="calculator($event)">/</button>
      <button @click="calculator($event)">*</button>
      <button @click="calculator($event)">**</button>
    </div>
  </div>
</template>

<script>
export default {
  data: () => ({
    operand1: 0,
    operand2: 0,
    result: 0
  }),
  props: {
  },
  methods: {
    calculator (op) {
      const mark = op.target.innerText;
      switch (mark) {
        case '-':
          this.result = this.operand1 - this.operand2;
          break;
        case '+':
          this.result = this.operand1 + this.operand2;
          break;
        case '*':
          this.result = this.operand1 * this.operand2;
          break;
        case '/':
          this.result = this.operand1 / this.operand2;
          break;
        case '**':
          this.result = this.operand1 ** this.operand2;
          break;
      }
    }
  },
}
</script>

<style scoped>
  .main {
    display: flex;
    flex-direction: column;
  }
  .calculator {
    margin-bottom: 10px;
    display: flex;
    justify-content: center;
    gap: 10px;
  }
  .result {
    border: black solid 1px;
    padding: 2px 4px; 
    border-radius: 4px;
  }
  .function {
    display: flex;
    justify-content: center;
    gap: 6px;
    
  }
</style>
