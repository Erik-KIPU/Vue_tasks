<template>
  <div>
    <!-- Задача 1: Вывод элементов массива в тегах div -->
    <div v-for="(item, index) in items" :key="index">
      {{ item }}
    </div>

    <!-- Задача 2: Вывод квадратов элементов массива в тегах div -->
    <div v-for="(item, index) in items" :key="index">
      {{ item * item }}
    </div>

    <!-- Задача 3: Вывод элементов массива в виде списка ul -->
    <ul>
      <li v-for="(item, index) in items" :key="index">
        {{ item }}
      </li>
    </ul>

    <!-- Задача 4: Вывод ключей массива в виде списка ul -->
    <ul>
      <li v-for="(key, index) in arr" :key="index">
        {{ key }}
      </li>
    </ul>

    <!-- Задача 5: Вывод значений объекта в виде списка ul -->
    <ul>
      <li v-for="(value, key) in users" :key="key">
        {{ value }}
      </li>
    </ul>

    <!-- Задача 6: Вывод ключей и значений объекта в виде списка ul -->
    <ul>
      <li v-for="(value, key) in users" :key="key">
        {{ key }} - {{ value }}
      </li>
    </ul>

    <!-- Задача 7: Верстка с использованием массива и тегов div -->
    <div v-for="(item, index) in items" :key="index">
      <p>{{ item }}</p>
      <p class="divider"></p>
    </div>

    <!-- Задача 8: Верстка с использованием массива и списка ul -->
    <ul>
      <li v-for="(item, index) in items" :key="index">
        {{ item }}
      </li>
      <li class="divider"></li>
    </ul>
  </div>
</template>

<script>
export default {
  data() {
    return {
      // Задачи 1, 2, 3, 7, 8
      items: [1, 2, 3, 4, 5],

      // Задача 4
      arr: ['x', 'y', 'z'],

      // Задачи 5 и 6
      users: {
        user1: '100$',
        user2: '200$',
        user3: '300$',
      },
    };
  },
};
</script>

<style>
.divider {
  border-bottom: 1px solid #000; /* Стиль для разделителя */
}
</style>

