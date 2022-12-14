<template>
  <todo-card v-for="(todo, index) in todos" :key="index" :item="todo"></todo-card>
</template>
<script setup>
import { defineProps } from "vue";
import todoCard from "./todo-card.vue";

defineProps({
  todos: Object,
});

// function deleteTodo(index) {
//   console.log("silindim", todos.value[index]);
//   todos.value.splice(index, 1);
// }
</script>
