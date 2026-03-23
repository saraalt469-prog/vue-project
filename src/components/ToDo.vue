
<script setup>
import { ref, defineEmits,defineProps } from "vue";
const props = defineProps({
  text:{
    type: String,
  }
})
const emit = defineEmits([ 'Remove'])
</script>

<template>
<div class="toDo">
  <p>{{ text }}</p>
  <button class="toDo__btn" @click="emit('Remove')">x</button>
</div>
</template>

<style>
.toDo__btn{
  background-color: transparent;
  border: none;
  font-size: 30px;
}
p{
    color: black;
    font-size: 20px;
}
.toDo
{
    display: flex;
    justify-content: space-between;
}
</style>
