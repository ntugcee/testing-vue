<template>
  <div style="border: 1px solid green; padding: 20px">
    <input v-model="data" placeholder="Add a new " /> <br /><br />
    <button @click="addTodo($event)">Add List</button>
    <button type="button" @click="clearLocal">Clear local</button>
    <div style="background: red">
      <!-- <h1>{{baslik}}</h1> -->
    </div>
    <to-list :data="todo" @delete="deleteTodo" />
  </div>
</template>

<script setup>
import ToList from "./to-list.vue";
import { ref, defineEmits } from "vue";
const emit = defineEmits(["change", "delete"]);
const todo = ref([]);

const data = ref("");

console.log("dskahdkjs---->>>>", data.value);

// const addTodo = (item) => {
//   todo.value.push(item)
//   emit('change', todo);
// }

function addTodo() {
  todo.value.push(data.value);
  emit("change", todo);
}

const deleteTodo = (item) => {
  todo.value.push(item);
};
</script>

<style>
button,
input {
  background-color: white;
  color: black;
  border: 2px solid #4caf50; /* Green */
  margin-right: 4px;
  margin-bottom: 8px;
}
</style>

