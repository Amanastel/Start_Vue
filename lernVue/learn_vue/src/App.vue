<template>
  <div id="app">
    <!-- <img alt="Vue logo" src="./assets/logo.png"> -->
    <!-- <HelloWorld msg="Welcome to Your Vue.js App"/> -->
    <!-- <Homes msg="hello world"/> -->
    <child v-bind:users="users" />
    <Databind />
    <loveme msg="hello world" />

    <HomeMain />
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
// import Homes from './components/HomePage.vue'
// import loveme from './components/Love-me.vue'
import HomeMain from "./components/Home-main.vue";
import Databind from "./components/Databind.vue";
import child from "./components/child.vue";

export default {
  name: "App",
  components: {
    // HelloWorld,
    // Homes,
    // loveme,
    HomeMain,
    Databind,
    child,
  },
  data() {
    return {
      users: [
        { id: 1, name: "Aman", email: "aman@mail.com" },
        { id: 2, name: "Rahul", email: "rahul@mail.com" },
        { id: 3, name: "Sonu", email: "sonu@mail.com" },
        { id: 4, name: "Kunal", email: "kunal@mail.com" },
      ],
    };
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
