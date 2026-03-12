<script setup>
import { ref } from "vue";
const items = ref([
  {
    id: 1,
    name: "Швейцарские часы",
    price: 79990,
    image:
      "https://i.pinimg.com/736x/cb/4e/22/cb4e2226eb6b387a345edb2527ecca17.jpg",
  },
  {
    id: 2,
    name: "Голубь",
    price: 99990,
    image:
      "https://i.pinimg.com/1200x/a7/a4/6d/a7a46de35f7021f7c156ab51266f9c0d.jpg",
  },
]);
const visible = ref(false);
</script>

<template>
  <header class="header">
    <p class="header-title">Карточки товара</p>
    <button class="header-button" @click="visible = !visible">
      {{ visible ? "скрыть" : "показать" }}
    </button>
  </header>
  <div class="cards" v-if="visible">
    <div v-for="item in items" class="card">
      <img :src="item.image" alt="" class="image" />
      <h3 class="title">{{ item.name }}</h3>
      <p class="price">{{ item.price }}руб.</p>
    </div>
  </div>
</template>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  color: aliceblue;
}
body {
  background-color: darkslategrey;
}
.cards {
  margin: 50px auto 50px auto;
  max-width: 600px;

  display: flex;
  flex-direction: column;
  gap: 40px;
  border-radius: 10px;
}
.card {
  padding: 20px;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  background-color: rgb(105, 129, 105);
  border-radius: 60px;
}
.image {
  max-width: 500px;
  max-height: 500px;
  margin: 0 auto;
  border-radius: 10px;
}
.price {
  background-color: darkolivegreen;
  padding: 5px;
  border-radius: 5px;
  margin-top: 20px;
}
.title {
  background-color: darkolivegreen;
  font-size: 30px;
  margin-top: 20px;
  border-radius: 5px;
  padding: 5px;
}
.header {
  display: flex;
  background-color: rgb(105, 129, 105);
  justify-content: space-between;
  padding: 15px 70px;
}
.header-title {
  font-size: 30px;
}
.header-button {
  background-color: darkolivegreen;
  padding: 5px;
  border-radius: 5px;
}
</style>
