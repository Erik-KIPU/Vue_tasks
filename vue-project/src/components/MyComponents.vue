<template>
  <div>
    <!-- Задача 1: Условный рендеринг абзацев -->
    <p v-if="visible">Первый абзац (visible = true)</p>
    <p v-else>Второй абзац (visible = false)</p>

    <!-- Задача 2: Инвертирование условия -->
    <p v-if="!hidden">Инвертированный текст (hidden = false)</p>

    <!-- Задача 3: Показ абзаца по клику на кнопку -->
    <p v-if="showParagraph">Этот абзац можно показать или скрыть</p>
    <button @click="showParagraph = !showParagraph">
      {{ showParagraph ? 'Скрыть абзац' : 'Показать абзац' }}
    </button>

    <!-- Задача 4: Показ и скрытие абзаца двумя кнопками -->
    <p v-if="isParagraphVisible">Абзац с двумя кнопками</p>
    <button @click="isParagraphVisible = true">Показать абзац</button>
    <button @click="isParagraphVisible = false">Скрыть абзац</button>

    <!-- Задача 5: Тогглинг трех абзацев -->
    <p v-if="showParagraph1">Абзац 1</p>
    <p v-if="showParagraph2">Абзац 2</p>
    <p v-if="showParagraph3">Абзац 3</p>
    <button @click="showParagraph1 = !showParagraph1">
      {{ showParagraph1 ? 'Скрыть абзац 1' : 'Показать абзац 1' }}
    </button>
    <button @click="showParagraph2 = !showParagraph2">
      {{ showParagraph2 ? 'Скрыть абзац 2' : 'Показать абзац 2' }}
    </button>
    <button @click="showParagraph3 = !showParagraph3">
      {{ showParagraph3 ? 'Скрыть абзац 3' : 'Показать абзац 3' }}
    </button>

    <!-- Задача 6: Условный рендеринг текста в зависимости от isAdmin -->
    <p v-if="isAdmin">Вы администратор</p>
    <p v-else>Вы не администратор</p>

    <!-- Задача 7: Показ абзаца с текущим днем недели -->
    <p v-if="day === 0">Воскресенье</p>
    <p v-else-if="day === 1">Понедельник</p>
    <p v-else-if="day === 2">Вторник</p>
    <p v-else-if="day === 3">Среда</p>
    <p v-else-if="day === 4">Четверг</p>
    <p v-else-if="day === 5">Пятница</p>
    <p v-else-if="day === 6">Суббота</p>
    <p v-else>Неверный день недели</p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      // Задача 1 и 2
      visible: true,
      hidden: false,

      // Задача 3
      showParagraph: false,

      // Задача 4
      isParagraphVisible: false,

      // Задача 5
      showParagraph1: false,
      showParagraph2: false,
      showParagraph3: false,

      // Задача 6
      isAdmin: true,

      // Задача 7
      day: new Date().getDay(), // Текущий день недели (0 - воскресенье, 6 - суббота)
    };
  },
};
</script>

