<template>
  <div class="app">
    <h1>Basket count: {{ count }}</h1>
    <div class="list">
      <!--TODO через v-for список продуктов(только имя) которые в корзине -->
      <div class="list__item">Apple</div>
      <div class="list__item">Ihpone</div>
    </div>
    <div class="product-list">
      <!--TODO вывести через v-for -->

      <product-card
        v-for="product in products"
        :key="product.name"
        v-bind:name="product.name"
        v-on:startClick="addBasket"
        v-on:clickOnProuctName="nameClick"
      />
      <!-- <product-card
        v-bind:name="products[0].name"
        v-bind:price="products[0].price"
        v-bind:image="products[0].image"
        v-on:startClick="increaseCount"
      />
      <product-card
        v-bind:name="products[1].name"
        v-bind:price="products[1].price"
        v-on:startClick="increaseCount"
      />
      <product-card
        v-bind:name="products[2].name"
        v-bind:price="products[2].price"
        v-bind:image="products[2].image"
        v-on:startClick="increaseCount"
      /> -->
    </div>

    <h6>{{ message }}</h6>
  </div>
</template>

<script>
import ProductCard from "./ProductCard.vue";
export default {
  name: "App",
  components: {
    ProductCard,
  },
  data() {
    return {
      count: 0,
      message: "",
      basketProducts: [],
      products: [
        {
          name: "Apple",
          price: 3000,
          image:
            "https://object.pscloud.io/cms/cms/Photo/img_0_77_3179_0_1.jpg",
        },
        { name: "Orage", price: 5500 },
        {
          name: "Ihone",
          price: 6000,
          image:
            "https://object.pscloud.io/cms/cms/Photo/img_0_8_1023_1_6_320.webp",
        },
      ],
    };
  },
  watch: {
    count: {
      handler() {
        console.log("WATCH IN COUNT");
        this.message = "count changed" + this.count;
      },
    },
  },
  mounted() {
    this.count = localStorage.getItem("count");
  },
  methods: {
    addBasket(name) {
      this.basketProducts.push(name);
    },
    nameClick() {
      console.log("App click on name");
    },
  },
};
</script>

<style lang="css" scoped>
.product-list {
  display: flex;
  gap: 1%;
}
</style>
