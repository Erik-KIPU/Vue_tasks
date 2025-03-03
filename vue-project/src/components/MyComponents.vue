<template>
  <div>
    <!-- Абзац с динамическими классами -->
    <p :class="cssClasses">Текст с динамическими классами</p>

    <!-- Применение объекта с классами -->
    <p :class="obj">Абзац с классами из объекта</p>

    <!-- Прячем элемент с классом hidden -->
    <p :class="hiddenObj">Этот текст можно скрыть</p>
    
    <!-- Кнопки управления скрытием -->
    <button @click="showElement">Показать</button>
    <button @click="hideElement">Скрыть</button>
    <button @click="toggleElement">Тогглить</button>
    
    <!-- Элемент с переключаемым классом hidden -->
    <p v-show="isVisible">Этот элемент управляется кнопками</p>

    <!-- Применение другого объекта с классами -->
    <p :class="{ active: true, valid: false }">Текст с объектом классов</p>

    <!-- Динамические классы на основе свойств -->
    <p :class="{ 'is-valid': isValid, 'is-disabled': isDisabled }">
      Абзац с динамическими классами
    </p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      cssClasses: "text-red bg-gray",
      obj: {
        done: true,
        selected: false,
      },
      hiddenObj: {
        hidden: true,
      },
      isVisible: false,
      isValid: true,
      isDisabled: true,
    };
  },
  methods: {
    showElement() {
      this.isVisible = true;
    },
    hideElement() {
      this.isVisible = false;
    },
    toggleElement() {
      this.isVisible = !this.isVisible;
    },
  },
};
</script>

<style>
.hidden {
  display: none;
}
.is-valid {
  color: green;
}
.is-disabled {
  opacity: 0.5;
}
.text-red {
  color: red;
}
.bg-gray {
  background-color: gray;
}
.done {
  text-decoration: line-through;
}
.selected {
  font-weight: bold;
}
.active {
  border: 2px solid blue;
}
</style>


