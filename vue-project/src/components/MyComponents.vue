<template>
  <div class="employee">
    <p>Имя: <input v-model="editableUser.name" /></p>
    <p>Зарплата: <input v-model="editableUser.salary" type="number" /></p>
    <p>Возраст: <input v-model="editableUser.age" type="number" /></p>
    
    <button @click="onLogName(editableUser.name)">Вывести имя</button>
    <button @click="onLogNameSalary(editableUser.name, editableUser.salary)">Вывести имя и зарплату</button>
    
    <button @click="$emit('remove')">Удалить</button>
    <button @click="$emit('edit', editableUser)">Сохранить изменения</button>
  </div>
</template>

<script>
export default {
  props: {
    name: String,
    salary: Number,
    age: Number,
    onLogName: Function,
    onLogNameSalary: Function,
  },
  data() {
    return {
      editableUser: {
        name: this.name,
        salary: this.salary,
        age: this.age,
      },
    };
  },
};
</script>

<style>
.employee {
  border: 1px solid #ccc;
  padding: 10px;
  margin: 5px 0;
  border-radius: 5px;
}
</style>


