<template>
  <div>
    <!-- Задача 1: Вспомогательный метод для получения дня недели -->
    <p>День недели для числа 3: {{ getDayOfWeek(3) }}</p>

    <!-- Задача 2: Основной метод для вывода текущего дня недели -->
    <p>Текущий день недели: {{ currentDay }}</p>

    <!-- Задача 3: Метод для вывода квадрата числа через alert -->
    <button @click="showSquare(2)">Квадрат числа 2</button>
    <button @click="showSquare(3)">Квадрат числа 3</button>

    <!-- Задача 4: Вывод свойства text в абзаце -->
    <p>{{ text }}</p>

    <!-- Задача 5: Изменение свойства text по клику на кнопку -->
    <button @click="changeText('Новое значение 1')">Изменить текст на 1</button>
    <button @click="changeText('Новое значение 2')">Изменить текст на 2</button>

    <!-- Задача 6: Вычисляемое свойство price -->
    <p>Полная стоимость: {{ price }}</p>
    <button @click="changeCost">Изменить цену</button>

    <!-- Задача 7: Ссылка с обработчиком клика -->
    <a href="#" @click.prevent="handleLinkClick">Кликни меня (без перехода)</a>

    <!-- Задача 8: Кнопка с обработчиком клика, срабатывающим только один раз -->
    <button @click.once="handleSingleClick">Кликни меня (один раз)</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      text: 'Исходный текст', // Задача 4 и 5
      cost: 10, // Задача 6
      amount: 5, // Задача 6
    };
  },
  computed: {
    // Задача 6: Вычисляемое свойство для полной стоимости
    price() {
      return this.cost * this.amount;
    },
    // Задача 2: Текущий день недели
    currentDay() {
      return this.getDayOfWeek(new Date().getDay());
    },
  },
  methods: {
    // Задача 1: Вспомогательный метод для получения дня недели
    getDayOfWeek(dayNumber) {
      const days = ['Воскресенье', 'Понедельник', 'Вторник', 'Среда', 'Четверг', 'Пятница', 'Суббота'];
      return days[dayNumber] || 'Неверный номер дня';
    },

    // Задача 3: Метод для вывода квадрата числа через alert
    showSquare(num) {
      alert(`Квадрат числа ${num}: ${num * num}`);
    },

    // Задача 5: Метод для изменения свойства text
    changeText(newText) {
      this.text = newText;
    },

    // Задача 6: Метод для изменения свойства cost
    changeCost() {
      this.cost = Math.floor(Math.random() * 100); // Изменяем цену случайным образом
    },

    // Задача 7: Обработчик клика по ссылке
    handleLinkClick() {
      alert('Клик по ссылке, но переход отменен');
    },

    // Задача 8: Обработчик клика, срабатывающий только один раз
    handleSingleClick() {
      alert('Этот обработчик сработает только один раз');
    },
  },
};
</script>

