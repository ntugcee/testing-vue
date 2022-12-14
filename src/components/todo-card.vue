<template>
  <div class="card">
    <ul class="list-group-item">
      <li class="list-item-label">
        <input class="checkbox" type="checkbox">
        <span :class="{ done: item?.done }" @click="setDone(item)" class="cursor">
          {{ item?.content }}
        </span>
        <span class="list-group-item" v-if="item && item.done">
          Done:{{ item.done }}
        </span>
        <span type="button" class="far fa-trash-alt delete" @click="deleteTodo(index)"></span>
      </li>
    </ul>
  </div>
</template>

<script setup>
import { defineProps } from "vue";

defineProps({
  item: {
    type: Object,
  },
});

function setDone(todo) {
  todo.done = !todo.done;
}

// function deleteTodo(index) {
//   todos.value.splice(index, 1);
// }



</script>

<style>
.cursor {
  cursor: pointer;
}

.done {
  text-decoration: line-through;
}

.card {
  display: flex;
  align-items: center;
  margin: auto;
  width: 50%;
  padding: 4px;
  border-radius: 10px;
  margin-bottom: 12px;
  margin-top: 12px;
  background-color: transparent;
}

.checkbox {
  width: 16px;
  height: 16px;
  border-radius: 35%;
  border: 1px solid #042940;
  transition: 0.2s;
  margin-right: 18px;
  flex-shrink: 0;
  margin-top: 4px;
  appearance: none;
}

.list-group-item input:hover {
  border-color: #DBF227;
  box-shadow: 0 0 0 3px;
}

.list-group-item input:checked {
  background-size: 10px;
  border: 1px solid #DBF227;
  background-color: #8C1F28;
}

.list-group-item input:checked+span {
  color: #8C1F28;
  text-decoration: line-through #8C1F28;
}

.list-item-label {
  display: flex;
  align-items: flex-start;
  color: #042940;
  margin-right: 8px;
  font-size: 14px;
  line-height: 24px;
  position: relative;
  transition: 0.2s;
  cursor: pointer;
}

.far {
  margin-left: auto;
  margin-right: 5px;
  display: block;
  width: 26px;
  height: 26px;
  cursor: pointer;
}
</style>