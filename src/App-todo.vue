<template>
  <div class="app-container">
    <todo-header @addTodo="addTodo"></todo-header>
    <todo-list :todos="todos"></todo-list>
  </div>
</template>

<script setup>
import { ref } from "vue";
import TodoHeader from "./components/todo-header.vue";
import TodoList from "./components/todo-list.vue";

const todos = ref([{ content: "test1", done: false }]);


const addTodo = (event) => {
  console.log("fhjkshfjksdhfjkd", event);
};

</script>
