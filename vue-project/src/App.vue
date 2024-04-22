<template>
  <div>
    <input type="number" v-model="num1" @input="calculate">
    <select v-model="operator" @change="calculate">
      <option value="+">+</option>
      <option value="-">-</option>
      <option value="*">*</option>
      <option value="/">/</option>
    </select>
    <input type="number" v-model="num2" @input="calculate">
    <p>Resultado: {{ result }}</p>
  </div>
</template>

<script setup lang="ts">
import { ref, computed } from 'vue';

const num1 = ref(0);
const num2 = ref(0);
const operator = ref('+');

const result = computed(() => {
  switch (operator.value) {
    case '+':
      return num1.value + num2.value;
    case '-':
      return num1.value - num2.value;
    case '*':
      return num1.value * num2.value;
    case '/':
      return num1.value / num2.value;
    default:
      return 0;
  }
});

function calculate() {
  result.value;
}
</script>

<style scoped>

</style>
