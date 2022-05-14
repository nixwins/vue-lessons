<template>
  <div>
    <div v-for="u in users" :key="u" class="item" v-on:click="showAlert(u)">
      {{ u.name }}
    </div>

    <p style="font-size: 40px; color: red">{{ clickedUser }}</p>

    <!-- <p>{{ name + " " + lastname }}</p> -->

    <!-- <p>{{ fullname }}</p> -->

    <!-- <button
      class="button"
      v-bind:class="{ 'is-active': isClicked }"
      v-on:click="addClass"
    >
      Click me
    </button> -->
    <!-- <input type="text" v-bind:value="login" v-on:input="changeLogin" /> -->
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      users: [
        { id: 1, name: "Dos" },
        { id: 2, name: "Asylbek" },
      ],
      name: "Dos",
      lastname: "Zhora",
      isClicked: false,
      login: "1nixwins",
      clickedUser: "",
    };
  },
  computed: {
    fullname() {
      return this.name + " " + this.lastname;
    },
  },
  methods: {
    showAlert(user) {
      // alert();
      // console.log("Privet", user.name);
      this.clickedUser = user.name;
    },
    changeLogin(event) {
      console.log(event);
      this.login = event.target.value;
    },

    addClass() {
      // this.isClicked = !this.isClicked;
      // if (this.isClicked === true) {
      //   this.isClicked = false;
      // } else {
      //   this.isClicked = true;
      // }
    },
  },
};
</script>

<style>
.is-active {
  background: rosybrown;
}
</style>