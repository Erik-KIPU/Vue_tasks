<template>
  <div>
    <!-- Задание 1: Родной язык (radio) -->
    <h2>Задание 1</h2>
    <label>
      <input type="radio" v-model="nativeLanguage" value="Русский"> Русский
    </label>
    <label>
      <input type="radio" v-model="nativeLanguage" value="Английский"> Английский
    </label>
    <label>
      <input type="radio" v-model="nativeLanguage" value="Французский"> Французский
    </label>
    <p>Выбранный язык: {{ nativeLanguage }}</p>

    <!-- Задание 2: Город (select) -->
    <h2>Задание 2</h2>
    <select v-model="selectedCity">
      <option value="Москва">Москва</option>
      <option value="Санкт-Петербург">Санкт-Петербург</option>
      <option value="Новосибирск">Новосибирск</option>
    </select>
    <p>Выбранный город: {{ selectedCity }}</p>

    <!-- Задание 3: День недели (select) -->
    <h2>Задание 3</h2>
    <select v-model="selectedDay">
      <option value="Понедельник">Понедельник</option>
      <option value="Вторник">Вторник</option>
      <option value="Среда">Среда</option>
      <option value="Четверг">Четверг</option>
      <option value="Пятница">Пятница</option>
      <option value="Суббота">Суббота</option>
      <option value="Воскресенье">Воскресенье</option>
    </select>
    <p>Выбранный день: {{ selectedDay }}</p>

    <!-- Задание 4: Дата (три селекта) -->
    <h2>Задание 4</h2>
    <select v-model="selectedDayOfMonth">
      <option v-for="day in 31" :key="day" :value="day">{{ day }}</option>
    </select>
    <select v-model="selectedMonth">
      <option v-for="month in 12" :key="month" :value="month">{{ month }}</option>
    </select>
    <select v-model="selectedYear">
      <option v-for="year in years" :key="year" :value="year">{{ year }}</option>
    </select>
    <p>Выбранная дата: {{ selectedDayOfMonth }}.{{ selectedMonth }}.{{ selectedYear }}</p>

    <!-- Задание 5: Блокировка инпута -->
    <h2>Задание 5</h2>
    <input ref="inputField" v-model="inputText" placeholder="Введите текст">
    <button @click="toggleInputLock">{{ isInputLocked ? 'Разблокировать' : 'Заблокировать' }}</button>

    <!-- Задание 6: Ввод текста по Enter -->
    <h2>Задание 6</h2>
    <input v-model="enterText" @keyup.enter="addEnterText" placeholder="Введите текст и нажмите Enter">
    <p>Введенный текст: {{ enteredText }}</p>

    <!-- Задание 7: Ссылка с Ctrl -->
    <h2>Задание 7</h2>
    <a href="#" @click.prevent="handleCtrlClick">Нажмите меня с зажатым Ctrl</a>
    <p>{{ ctrlClickText }}</p>

    <!-- Задание 8: Ссылка с разными кнопками мыши -->
    <h2>Задание 8</h2>
    <a href="#" @click.prevent="handleMouseClick($event)">Нажмите меня (левая, правая или средняя кнопка мыши)</a>
    <p>{{ mouseClickText }}</p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      nativeLanguage: '', // Задание 1
      selectedCity: '', // Задание 2
      selectedDay: '', // Задание 3
      selectedDayOfMonth: 1, // Задание 4
      selectedMonth: 1, // Задание 4
      selectedYear: new Date().getFullYear(), // Задание 4
      years: Array.from({ length: 10 }, (_, i) => new Date().getFullYear() - i), // Задание 4
      inputText: '', // Задание 5
      isInputLocked: false, // Задание 5
      enterText: '', // Задание 6
      enteredText: '', // Задание 6
      ctrlClickText: '', // Задание 7
      mouseClickText: '', // Задание 8
    };
  },
  methods: {
    // Задание 5: Блокировка/разблокировка инпута
    toggleInputLock() {
      this.isInputLocked = !this.isInputLocked;
      this.$refs.inputField.disabled = this.isInputLocked;
    },

    // Задание 6: Ввод текста по Enter
    addEnterText() {
      this.enteredText = this.enterText;
      this.enterText = '';
    },

    // Задание 7: Обработка клика с Ctrl
    handleCtrlClick(event) {
      if (event.ctrlKey) {
        this.ctrlClickText = 'Вы нажали ссылку с зажатым Ctrl!';
      } else {
        this.ctrlClickText = '';
      }
    },

    // Задание 8: Обработка клика разными кнопками мыши
    handleMouseClick(event) {
      if (event.button === 0) {
        this.mouseClickText = 'left';
      } else if (event.button === 2) {
        this.mouseClickText = 'right';
      } else if (event.button === 1) {
        this.mouseClickText = 'middle';
      }
    },
  },
};
</script>

<style scoped>
/* Стили для компонента */
a {
  display: block;
  margin: 10px 0;
  color: blue;
  text-decoration: underline;
  cursor: pointer;
}
</style>
