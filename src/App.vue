<script setup>
import { ref } from "vue";
import ToDo from "./components/ToDo.vue";
import Counter from "./components/Counter.vue";

const tasks = ref([
  {
    id: 1,
    text: "Написать конспект",
  },
  {
    id: 2,
    text: "Пройти урок в Дуолинго",
  },
  {
    id: 3,
    text: "Разобрать пропсы и эмиты",
  },
]);
const RemoveText = (index) => {
  tasks.value.splice(index, 1);
};

//---------------------------------------------------------------------------------

const count = ref(0);

const Fincrement = () => {
  count.value++;
};
const Fdecrement = () => {
  count.value--;
};
</script>

<template>
  <div class="todo-list">
    <h3>Список задач</h3>
    <ToDo
      v-for="el in tasks"
      :key="el.id"
      :text="el.text"
      @Remove="RemoveText(index)"
    />
  </div>

  <div class="Component">
    <Counter @increment="Fincrement" @decrement="Fdecrement" />
    <p>Счетчик:{{ count }}</p>
  </div>
</template>

<style>
.todo-list {
  background-color: rgb(194, 192, 192);
  max-width: 700px;
  border-radius: 20px;
  padding: 20px;
  margin: 50px auto;
}
.Component {
  display: flex;
  flex-direction: column;
  max-width: 300px;

  align-items: center;
  margin: 0 auto;
}
</style>
