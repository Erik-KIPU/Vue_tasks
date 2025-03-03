<template>
  <div>
    <!-- Кнопка для вызова метода -->
    <button @click="showCurrentDate">Показать текущую дату</button>
  </div>
</template>

<script>
export default {
  methods: {
    // Метод для вывода текущей даты через alert
    showCurrentDate() {
      const currentDate = new Date().toLocaleDateString(); // Получаем текущую дату
      alert(`Текущая дата: ${currentDate}`); // Выводим дату в alert
    },
  },
};
</script>

