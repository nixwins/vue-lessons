<template>
  <div>
    <p v-on:click="changeName">{{ name }}</p>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      name: "Марс",
    };
  },
  methods: {
    changeName() {
      this.name = "Земля";
    },
  },
};
</script>

<style lang="scss" scoped>
</style>