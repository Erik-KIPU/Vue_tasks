<template>
  <div>
    <!-- Задача 1: Вывод текста в зависимости от возраста -->
    <p v-if="age < 18">Подросток</p>
    <p v-else-if="age >= 19 && age <= 25">Молодой человек</p>
    <p v-else>Мужчина</p>

    <!-- Задача 2: Скрытие трех абзацев по нажатию на кнопку -->
    <p v-if="showParagraphs">Абзац 1</p>
    <p v-if="showParagraphs">Абзац 2</p>
    <p v-if="showParagraphs">Абзац 3</p>
    <button @click="hideParagraphs">Скрыть абзацы</button>

    <!-- Задача 3: Тогглинг абзаца по нажатию на кнопку -->
    <p v-if="isToggled">Этот абзац можно скрыть или показать</p>
    <button @click="toggleParagraph">
      {{ isToggled ? 'Скрыть абзац' : 'Показать абзац' }}
    </button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      // Задача 1
      age: 25,

      // Задача 2
      showParagraphs: true,

      // Задача 3
      isToggled: false,
    };
  },
  methods: {
    // Задача 2: Метод для скрытия абзацев
    hideParagraphs() {
      this.showParagraphs = false;
    },

    // Задача 3: Метод для тогглинга абзаца
    toggleParagraph() {
      this.isToggled = !this.isToggled;
    },
  },
};
</script>

