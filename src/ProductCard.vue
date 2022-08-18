<template>
  <div class="product-card">
    Product
    <img v-bind:src="image" alt="" />
    <h2>{{ name }}</h2>
    <h3>{{ price }}</h3>
    <button v-on:click="addBasket">Add basket</button>
  </div>
</template>

<script>
export default {
  name: "ProductCard",
  props: ["name", "price", "image"],
  methods: {
    addBasket() {
      console.log("clicked product");
      this.$emit("startClick", this.price);
    },
  },
};
</script>
<style>
.product-card {
  width: 30%;
}
img {
  width: 100%;
}
</style>
