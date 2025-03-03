<template>
  <div>
    <!-- Кнопка для вывода даты по клику -->
    <button @click="showCurrentDate">Показать дату по клику</button>

    <!-- Кнопка для вывода даты по наведению -->
    <button @mouseover="showCurrentDate">Показать дату по наведению</button>
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

