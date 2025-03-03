<template>
  <div>
    <!-- Задача 1: Квадрат числа num -->
    <p>Квадрат числа {{ num }}: {{ square }}</p>

    <!-- Задача 2: Сумма чисел num1, num2 и num3 -->
    <p>Сумма чисел {{ num1 }}, {{ num2 }} и {{ num3 }}: {{ sum }}</p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      num: 5, // Задача 1
      num1: 1, // Задача 2
      num2: 2, // Задача 2
      num3: 3, // Задача 2
    };
  },
  computed: {
    // Вычисляем квадрат числа num
    square() {
      return this.num ** 2;
    },
    // Вычисляем сумму чисел num1, num2 и num3
    sum() {
      return this.num1 + this.num2 + this.num3;
    },
  },
};
</script>
