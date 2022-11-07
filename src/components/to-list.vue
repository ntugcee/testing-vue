<template>
  <div style="border: 1px solid red">
    <ul class="list">
      <li v-for="(item, index) in data" :key="index">
        {{ item }}
      </li>
    </ul>
  </div>
</template>

<script setup>
import { defineProps } from "vue";

const props = defineProps({
  data: null,
});
console.log("prop geldi", props.data);

</script>

<style>

</style>