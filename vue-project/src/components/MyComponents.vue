<template>
  <div>
    <!-- Вывод суммы элементов объекта -->
    <p>Сумма элементов объекта: {{ sum }}</p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      obj: { x: 1, y: 2, z: 3 }, // Объект с числами
    };
  },
  computed: {
    // Вычисляем сумму значений объекта
    sum() {
      return Object.values(this.obj).reduce((acc, curr) => acc + curr, 0);
    },
  },
};
</script>


