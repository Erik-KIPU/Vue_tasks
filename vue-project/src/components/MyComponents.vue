<template>
  <div>
    <!-- Список работников -->
    <ul>
      <li v-for="user in users" :key="user.id">
        <Employee :name="user.name" :salary="user.salary" :age="user.age" />
      </li>
    </ul>
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
        { id: 1, name: "name1", salary: 100, age: 30 },
        { id: 2, name: "name2", salary: 200, age: 40 },
        { id: 3, name: "name3", salary: 300, age: 50 },
      ],
    };
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

