<template>
  <!-- <to-add :baslik="baslik"/> -->
  <to-add @change="bas" />
  
</template>

<script>
import ToAdd from './components/to-add.vue';

export default {
  name: 'App',
  components: {
    ToAdd
  },

  data() {
    return {
      cars: [],
      car: "",
      // baslik:"merhaba"
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
    bas(e) {
      console.log('haci abi ',e)
    }
  },

  getCars() {
    this.cars = JSON.parse(localStorage.getItem("cars"));
  },
 };
</script>


<style>

</style>
