<template>
  <div>
    <!-- Задание 1: Добавление элемента в список -->
    <h2>Задание 1</h2>
    <input v-model="newItem" placeholder="Введите текст">
    <button @click="addItem">Добавить</button>
    <ul>
      <li v-for="(item, index) in items" :key="index">{{ item }}</li>
    </ul>

    <!-- Задание 2: Удаление элемента из списка -->
    <h2>Задание 2</h2>
    <ul>
      <li v-for="(item, index) in items2" :key="index" @click="removeItem(index)">
        {{ item }}
      </li>
    </ul>

    <!-- Задание 3: Таблица работников с удалением -->
    <h2>Задание 3</h2>
    <table border="1">
      <thead>
        <tr>
          <th>ID</th>
          <th>Имя</th>
          <th>Зарплата</th>
          <th>Возраст</th>
          <th>Действия</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="user in users" :key="user.id">
          <td>{{ user.id }}</td>
          <td>{{ user.name }}</td>
          <td>{{ user.salary }}</td>
          <td>{{ user.age }}</td>
          <td>
            <a href="#" @click.prevent="deleteUser(user.id)">Удалить</a>
          </td>
        </tr>
      </tbody>
    </table>

    <!-- Задание 4: Таблица работников с редактированием -->
    <h2>Задание 4</h2>
    <table border="1">
      <thead>
        <tr>
          <th>ID</th>
          <th>Имя</th>
          <th>Зарплата</th>
          <th>Возраст</th>
          <th>Действия</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="user in users" :key="user.id">
          <td>{{ user.id }}</td>
          <td>
            <input v-if="user.isEditing" v-model="user.name" />
            <span v-else>{{ user.name }}</span>
          </td>
          <td>
            <input v-if="user.isEditing" v-model="user.salary" type="number" />
            <span v-else>{{ user.salary }}</span>
          </td>
          <td>
            <input v-if="user.isEditing" v-model="user.age" type="number" />
            <span v-else>{{ user.age }}</span>
          </td>
          <td>
            <a href="#" @click.prevent="toggleEdit(user)">
              {{ user.isEditing ? 'Сохранить' : 'Редактировать' }}
            </a>
            <a href="#" @click.prevent="deleteUser(user.id)">Удалить</a>
          </td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
export default {
  data() {
    return {
      // Задание 1
      newItem: '',
      items: ['Элемент 1', 'Элемент 2', 'Элемент 3'],

      // Задание 2
      items2: ['Элемент A', 'Элемент B', 'Элемент C'],

      // Задание 3 и 4
      users: [
        { id: 1, name: 'name1', salary: 100, age: 30, isEditing: false },
        { id: 2, name: 'name2', salary: 200, age: 40, isEditing: false },
        { id: 3, name: 'name3', salary: 300, age: 50, isEditing: false },
      ],
    };
  },
  methods: {
    // Задание 1: Добавление элемента в список
    addItem() {
      if (this.newItem.trim()) {
        this.items.push(this.newItem);
        this.newItem = '';
      }
    },

    // Задание 2: Удаление элемента из списка
    removeItem(index) {
      this.items2.splice(index, 1);
    },

    // Задание 3 и 4: Удаление пользователя
    deleteUser(id) {
      this.users = this.users.filter((user) => user.id !== id);
    },

    // Задание 4: Переключение режима редактирования
    toggleEdit(user) {
      user.isEditing = !user.isEditing;
    },
  },
};
</script>

<style scoped>
/* Стили для компонента */
ul {
  list-style-type: none;
  padding: 0;
}
li {
  cursor: pointer;
  margin: 5px 0;
  padding: 5px;
  background-color: #f0f0f0;
}
li:hover {
  background-color: #ddd;
}
table {
  width: 100%;
  border-collapse: collapse;
  margin-top: 20px;
}
th, td {
  padding: 10px;
  text-align: left;
}
a {
  margin-right: 10px;
  color: blue;
  text-decoration: underline;
  cursor: pointer;
}
</style>

