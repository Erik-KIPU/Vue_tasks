<template>
  <div>
    <!-- Задание 1 -->
    <h2>Задание 1</h2>
    <input v-model="inputText" placeholder="Введите текст">
    <p>{{ inputText }}</p>

    <!-- Задание 2 -->
    <h2>Задание 2</h2>
    <input v-model="inputTextUpper" placeholder="Введите текст">
    <p>{{ inputTextUpper.toUpperCase() }}</p>

    <!-- Задание 3 -->
    <h2>Задание 3</h2>
    <input v-model.number="numberInput" placeholder="Введите число">
    <p>Квадрат числа: {{ numberInput * numberInput }}</p>

    <!-- Задание 4 -->
    <h2>Задание 4</h2>
    <input v-model.number="sqrtInput" placeholder="Введите число">
    <button @click="calculateSqrt">Вычислить квадратный корень</button>
    <p>Квадратный корень: {{ sqrtResult }}</p>

    <!-- Задание 5 -->
    <h2>Задание 5</h2>
    <input v-model.number="num1" placeholder="Введите первое число">
    <input v-model.number="num2" placeholder="Введите второе число">
    <button @click="calculateSum">Вычислить сумму</button>
    <p>Сумма: {{ sumResult }}</p>

    <!-- Задание 6 -->
    <h2>Задание 6</h2>
    <input v-model="text1" placeholder="Введите текст 1">
    <input v-model="text2" placeholder="Введите текст 2">
    <button @click="swapTexts">Поменять тексты местами</button>

    <!-- Задание 7 -->
    <h2>Задание 7</h2>
    <input v-model="fullName" placeholder="Введите ФИО">
    <button @click="splitName">Разделить ФИО</button>
    <p>Фамилия: {{ lastName }}</p>
    <p>Имя: {{ firstName }}</p>
    <p>Отчество: {{ middleName }}</p>

    <!-- Задание 8 -->
    <h2>Задание 8</h2>
    <textarea v-model="textareaText" placeholder="Введите текст"></textarea>
    <p>{{ textareaText }}</p>

    <!-- Задание 9 -->
    <h2>Задание 9</h2>
    <textarea v-model="wordsText" placeholder="Введите текст"></textarea>
    <button @click="splitWords">Разделить на слова</button>
    <ul>
      <li v-for="word in words" :key="word">{{ word }}</li>
    </ul>

    <!-- Задание 10 -->
    <h2>Задание 10</h2>
    <input type="checkbox" v-model="isVisible">
    <p v-if="isVisible">Этот абзац виден, если checkbox отмечен.</p>

    <!-- Задание 11 -->
    <h2>Задание 11</h2>
    <label><input type="checkbox" v-model="languages" value="JavaScript"> JavaScript</label>
    <label><input type="checkbox" v-model="languages" value="Python"> Python</label>
    <label><input type="checkbox" v-model="languages" value="Java"> Java</label>
    <label><input type="checkbox" v-model="languages" value="C++"> C++</label>
    <ul>
      <li v-for="lang in languages" :key="lang">{{ lang }}</li>
    </ul>
  </div>
</template>

<script>
export default {
  data() {
    return {
      inputText: '',
      inputTextUpper: '',
      numberInput: 0,
      sqrtInput: 0,
      sqrtResult: null,
      num1: 0,
      num2: 0,
      sumResult: 0,
      text1: '',
      text2: '',
      fullName: '',
      lastName: '',
      firstName: '',
      middleName: '',
      textareaText: '',
      wordsText: '',
      words: [],
      isVisible: false,
      languages: [],
    };
  },
  methods: {
    calculateSqrt() {
      this.sqrtResult = Math.sqrt(this.sqrtInput);
    },
    calculateSum() {
      this.sumResult = this.num1 + this.num2;
    },
    swapTexts() {
      [this.text1, this.text2] = [this.text2, this.text1];
    },
    splitName() {
      const parts = this.fullName.split(' ');
      this.lastName = parts[0] || '';
      this.firstName = parts[1] || '';
      this.middleName = parts[2] || '';
    },
    splitWords() {
      this.words = this.wordsText.split(' ');
    },
  },
};
</script>



