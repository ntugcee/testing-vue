<template>
  <input v-model="car" placeholder="Add a new car" /> <br /><br />
  <input type="submit" @click="storeCar" value="Store" />
  <button @click="getCars">Get List</button>
  <button type="button" @click="clearLocal">Clear local</button>

  <ul class="list">
    <li v-for="(car, i) in cars" :key="i">
      {{ car }}
    </li>
  </ul>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      cars: [],
      car: "",
    };
  },
  created() {
    let test = JSON.parse(localStorage.getItem("cars"));
    if (test) {
      for (let i = 0; i < test.length; i++) {
        this.cars.push(test[i]);
      }
    }
  },
  methods: {
    storeCar() {
      if (this.car.length) {
        this.cars.push(this.car);
        localStorage.setItem("cars", JSON.stringify(this.cars));
        this.car = "";
      }
    },
    clearLocal() {
      localStorage.clear();
    },
  },

  getCars() {
    this.cars = JSON.parse(localStorage.getItem("cars"));
  },
};
</script>


<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
