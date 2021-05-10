<template>
  <div class="hello">
    <input v-model.number="operand1"/>
    <input v-model.number="operand2"/>
    = {{ result }}
    <div>
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

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
