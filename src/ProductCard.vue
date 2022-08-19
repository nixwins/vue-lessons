<template>
  <div class="product-card">
    Product
    <img v-bind:src="image" alt="" />
    <product-name v-bind:name="name" v-on:clickHeader="clickedOnName" />
    <h3>{{ price }}</h3>
    <button v-on:click="addBasket">Add basket</button>
  </div>
</template>

<script>
import ProductName from "./ProductName.vue";
export default {
  name: "ProductCard",
  props: ["name", "price", "image"],
  components: {
    ProductName,
  },

  methods: {
    addBasket() {
      console.log("clicked product");
      this.$emit("startClick", this.name);
    },
    clickedOnName() {
      console.log("clicked on name start");
      this.$emit("clickOnProuctName");
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
