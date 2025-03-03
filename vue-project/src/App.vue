<template>
  <div>
    <h2>Список работников</h2>
    <ul>
      <li v-for="user in users" :key="user.id">
        <Employee
          :name="user.name"
          :salary="user.salary"
          :age="user.age"
          @remove="removeUser(user.id)"
          @edit="editUser"
          :onLogName="logName"
          :onLogNameSalary="logNameSalary"
        />
      </li>
    </ul>

    <h3>Добавить работника</h3>
    <form @submit.prevent="addUser">
      <input v-model="newUser.name" placeholder="Имя" required />
      <input v-model="newUser.salary" type="number" placeholder="Зарплата" required />
      <input v-model="newUser.age" type="number" placeholder="Возраст" required />
      <button type="submit">Добавить</button>
    </form>
  </div>
</template>

<script>
import Employee from "./Employee.vue";

export default {
  components: {
    Employee,
  },
  data() {
    return {
      users: [
        { id: 1, name: "Андрей", salary: 1000, age: 30 },
        { id: 2, name: "Ольга", salary: 2000, age: 40 },
        { id: 3, name: "Виктор", salary: 3000, age: 50 },
      ],
      newUser: { name: "", salary: "", age: "" },
    };
  },
  methods: {
    logName(name) {
      console.log("Имя работника:", name);
    },
    logNameSalary(name, salary) {
      console.log(`Работник: ${name}, Зарплата: ${salary}`);
    },
    removeUser(id) {
      this.users = this.users.filter(user => user.id !== id);
    },
    editUser(updatedUser) {
      const index = this.users.findIndex(user => user.id === updatedUser.id);
      if (index !== -1) {
        this.users.splice(index, 1, updatedUser);
      }
    },
    addUser() {
      if (this.newUser.name && this.newUser.salary && this.newUser.age) {
        const id = Date.now();
        this.users.push({ id, ...this.newUser });
        this.newUser = { name: "", salary: "", age: "" };
      }
    },
  },
};
</script>