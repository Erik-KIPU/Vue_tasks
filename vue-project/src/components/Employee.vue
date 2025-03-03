<template>
  <div class="employee">
    <!-- Отображение данных работника -->
    <h2>{{ name }} {{ surname }}</h2>
    <p><strong>Возраст:</strong> {{ age }}</p>
    <p><strong>Зарплата:</strong> {{ salary }}</p>

    <!-- Кнопки для вызова переданных функций -->
    <button @click="callFunc1">Вызвать функцию 1</button>
    <button @click="callFunc2">Вызвать функцию 2</button>

    <!-- Кнопка для передачи имени в родительский компонент -->
    <button @click="emitName">Передать имя</button>

    <!-- Кнопка для передачи имени и зарплаты в родительский компонент -->
    <button @click="emitNameAndSalary">Передать имя и зарплату</button>

    <!-- Кнопка для удаления работника -->
    <button @click="emitDelete">Удалить</button>

    <!-- Форма для редактирования данных -->
    <div v-if="isEditing">
      <input v-model="editedName" placeholder="Имя" />
      <input v-model="editedSurname" placeholder="Фамилия" />
      <input v-model="editedAge" type="number" placeholder="Возраст" />
      <input v-model="editedSalary" type="number" placeholder="Зарплата" />
      <button @click="saveChanges">Сохранить</button>
      <button @click="cancelEditing">Отмена</button>
    </div>
    <button v-else @click="startEditing">Редактировать</button>
  </div>
</template>

<script>
export default {
  props: {
    name: {
      type: String,
      required: true,
    },
    surname: {
      type: String,
      required: true,
    },
    age: {
      type: Number,
      required: true,
    },
    salary: {
      type: Number,
      required: true,
    },
    func1: {
      type: Function,
      required: true,
    },
    func2: {
      type: Function,
      required: true,
    },
  },
  data() {
    return {
      isEditing: false,
      editedName: this.name,
      editedSurname: this.surname,
      editedAge: this.age,
      editedSalary: this.salary,
    };
  },
  methods: {
    callFunc1() {
      this.func1(this.name);
    },
    callFunc2() {
      this.func2(this.name, this.salary);
    },
    emitName() {
      this.$emit('name-emitted', this.name);
    },
    emitNameAndSalary() {
      this.$emit('name-salary-emitted', this.name, this.salary);
    },
    emitDelete() {
      this.$emit('delete-employee');
    },
    startEditing() {
      this.isEditing = true;
    },
    cancelEditing() {
      this.isEditing = false;
      this.resetEditedData();
    },
    saveChanges() {
      this.$emit('update-employee', {
        name: this.editedName,
        surname: this.editedSurname,
        age: this.editedAge,
        salary: this.editedSalary,
      });
      this.isEditing = false;
    },
    resetEditedData() {
      this.editedName = this.name;
      this.editedSurname = this.surname;
      this.editedAge = this.age;
      this.editedSalary = this.salary;
    },
  },
};
</script>

<style scoped>
.employee {
  border: 1px solid #ccc;
  padding: 16px;
  margin-bottom: 16px;
  border-radius: 8px;
}
button {
  margin: 5px;
}
</style>