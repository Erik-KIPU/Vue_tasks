<template>
  <div>
    <div>{{ name }}</div> <!-- Выводим имя -->
    <div>{{ surn }}</div> <!-- Выводим фамилию -->
  </div>
</template>

<script>
export default {
  data() {
    return {
      name: 'john',
      surn: 'smit',
    };
  },
};
</script>

