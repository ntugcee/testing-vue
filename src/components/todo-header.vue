<template>
  <div class="mx-auto mt-4" style="width: 18rem">
    <div class="app-header">
      <h4>What's on your <span>TODO LİST </span> ?</h4>
    </div>
    <input class="input form-control m-auto my" placeholder="add a new.." type="text" autocomplete="off"
      v-model="todo" />
    <br />
    <button type="button" class="btn btn-light" @click="$emit('addTodo', todo)">
      <span>+</span>
    </button>

  </div>
</template>

<script setup>
import { ref, defineEmits } from "vue";


defineEmits(["addTodo"]);

const todo = ref("")
// const input_content = ref('')

// const addTodo = () => {
//   if (input_content.value.trim() === '') {
//     return
//   }
// }

// const props = defineProps({
//   name: ["name"],
// })

</script>

<style>
.app-header {
  font-weight: bold;
}

.app-header span {
  color: #005C53;
  text-decoration: underline;
}

.input,
.btn {
  background-color: transparent;
  outline: none;
  border: none;
  border-bottom: 1px solid #005C53;
  color: #042940;
  box-shadow: none;
  border-radius: 0;
}

.input::placeholder {
  color: #005C53;
}

.btn {
  display: flex;
  align-items: center;
}

.btn span {
  color: #005C53;

}

.btn:hover {
  background-color: #E6FFAD;
}

.btn:focus {
  background-color: transparent;
}

.input:hover {
  background-color: #E6FFAD;
}

.input:focus {
  color: #042940;
  background-color: transparent;
  /* outline: 1px solid #E6FFAD; */
  outline: dashed #E6FFAD;
}
</style>

