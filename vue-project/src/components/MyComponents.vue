<template>
  <div>
    <!-- Задача 1: Вывод каждого элемента массива в отдельном абзаце -->
    <div>
      <p v-for="(item, index) in arr" :key="index">{{ item }}</p>
    </div>

    <!-- Задача 2: Вывод суммы элементов массива -->
    <p>Сумма элементов массива: {{ sum }}</p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      arr: [1, 2, 3], // Массив для обеих задач
    };
  },
  computed: {
    // Вычисляем сумму элементов массива
    sum() {
      return this.arr.reduce((acc, curr) => acc + curr, 0);
    },
  },
};
</script>

