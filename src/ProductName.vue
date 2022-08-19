<template>
  <h4 class="product-name" v-on:click="clickedName">{{ name }}</h4>
</template>

<script>
export default {
  name: "ProductName",
  props: ["name"],
  methods: {
    clickedName() {
      console.log("name clicked...");
      this.$emit("clickHeader");
    },
  },
};
</script>

<style lang="css" scoped>
.product-name {
  font-size: 49px;
  color: orange;
}
</style>
