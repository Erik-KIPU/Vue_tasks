<template>
  <div>
    <!-- Кнопка для вызова метода -->
    <button @click="showSum">Показать сумму</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      num1: 1, // Первое число
      num2: 2, // Второе число
    };
  },
  methods: {
    // Метод для вывода суммы чисел через alert
    showSum() {
      const sum = this.num1 + this.num2; // Вычисляем сумму
      alert(`Сумма чисел: ${sum}`); // Выводим сумму в alert
    },
  },
  // Вызов метода при создании компонента (опционально)
  mounted() {
    this.showSum();
  },
};
</script>