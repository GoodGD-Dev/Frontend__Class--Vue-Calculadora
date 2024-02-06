<script setup>
    import { ref, computed } from 'vue';

  const num1 = ref(0);
  const num2 = ref(0);
  const operador = ref('+');

  const result = computed(() => {
    switch (operador.value) {
      case '+':
        return parseFloat(num1.value) + parseFloat(num2.value);
      case '-':
        return parseFloat(num1.value) - parseFloat(num2.value);
      case '*':
        return parseFloat(num1.value) * parseFloat(num2.value);
      case '/':
        return parseFloat(num1.value) / parseFloat(num2.value);
      default:
        return 0;
    }
  });
</script>

<template>
  <div class="container mt-5">
    <h1 class="mb-4">Calculadora</h1>
    <div class="row">
      <div class="col-md-4">
        <input type="number" class="form-control" v-model.number="num1" @input="calculate">
      </div>
      <div class="col-md-4">
        <select class="form-select" v-model="operador" @change="calculate">
          <option value="+">+</option>
          <option value="-">-</option>
          <option value="*">*</option>
          <option value="/">/</option>
        </select>
      </div>
      <div class="col-md-4">
        <input type="number" class="form-control" v-model.number="num2" @input="calculate">
      </div>
    </div>
    <div class="mt-3">
      <h2>Result: {{ result }}</h2>
    </div>
  </div>
</template>

<style scoped>
</style>