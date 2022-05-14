<template>
  <div>
    <!-- <h1>Hello vue</h1>
    {{ num }}
    <p>{{ lastname }}</p>
    <p>{{ lastname + "#" + num * num }}</p> -->

    <!-- <p v-if="num > 500" style="font-size: 300px">Asylbek</p> -->
    <!-- <div v-for="u in users" :key="u">{{ u }}</div> -->
    <!-- <button v-on:click="foo">Click me</button> -->
    <!-- <button v-on:mouseover="boo">hover me</button> -->
    <h1>{{ counter }}</h1>
    <h2>{{ counter }}</h2>
    <h3>{{ counter }}</h3>
    <button v-on:click="increase">+</button>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      counter: 0,
      num: 600,
      lastname: "Dosov",
      users: ["dos", "asylbek"],
    };
  },
  methods: {
    increase() {
      this.counter++;
    },
    // foo: function () {
    //   alert();
    // },
    // boo() {
    //   console.log("Booo boo");
    // },
  },
};
</script>

<style>
</style>



