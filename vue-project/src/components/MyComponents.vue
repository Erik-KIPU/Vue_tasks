<template>
  <div>
    <!-- Задание 1 -->
    <ul>
      <li v-for="link in hrefs" :key="link.href">
        <a :href="link.href">{{ link.text }}</a>
      </li>
    </ul>

    <!-- Задание 2 -->
    <table>
      <tr v-for="product in products" :key="product.name">
        <td>{{ product.name }}</td>
        <td>{{ product.price }}</td>
        <td>{{ product.quantity }}</td>
      </tr>
    </table>

    <!-- 30 абзацев -->
    <p v-for="n in 30" :key="n">{{ n }}</p>

    <!-- Положительные элементы массива -->
    <div v-for="item in items" :key="item">
      <span v-if="item > 0">{{ item }}</span>
    </div>

    <!-- Список продуктов -->
    <ul>
      <li v-for="product in products" :key="product.id">{{ product.name }}</li>
    </ul>

    <!-- Управление списком -->
    <button @click="addItem">Добавить элемент</button>
    <button @click="removeFirstItem">Удалить первый элемент</button>
    <button @click="removeLastItem">Удалить последний элемент</button>
    <button @click="removeSecondLastItem">Удалить предпоследний элемент</button>
    <button @click="sortItems">Сортировать элементы</button>
    <button @click="reverseItems">Обратный порядок элементов</button>
    <ul>
      <li v-for="(item, index) in dynamicItems" :key="index">{{ item }}</li>
    </ul>
  </div>
</template>

<script>
export default {
  data() {
    return {
      hrefs: [
        { href: '1.html', text: 'text1' },
        { href: '2.html', text: 'text2' },
        { href: '3.html', text: 'text3' },
      ],
      products: [
        { name: 'product1', price: 100, quantity: 5 },
        { name: 'product2', price: 200, quantity: 4 },
        { name: 'product3', price: 300, quantity: 3 },
      ],
      items: [1, -2, 3, -4, 5],
      dynamicItems: ['Элемент 1', 'Элемент 2', 'Элемент 3']
    };
  },
  methods: {
    addItem() {
      this.dynamicItems.push(`Элемент ${this.dynamicItems.length + 1}`);
    },
    removeFirstItem() {
      this.dynamicItems.shift();
    },
    removeLastItem() {
      this.dynamicItems.pop();
    },
    removeSecondLastItem() {
      if (this.dynamicItems.length > 1) {
        this.dynamicItems.splice(-2, 1);
      }
    },
    sortItems() {
      this.dynamicItems.sort();
    },
    reverseItems() {
      this.dynamicItems.reverse();
    }
  }
};
</script>


