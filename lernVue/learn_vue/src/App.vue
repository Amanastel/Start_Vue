<template>
  <div id="app">
    <!-- <img alt="Vue logo" src="./assets/logo.png"> -->
    <!-- <HelloWorld msg="Welcome to Your Vue.js App"/> -->
    <!-- <Homes msg="hello world"/> -->
    <loveme msg="hello world"/>
    <HomeMain/>
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
// import Homes from './components/HomePage.vue'
// import loveme from './components/Love-me.vue'
import HomeMain from './components/Home-main.vue'


export default {
  name: 'App',
  components: {
    // HelloWorld,
    // Homes,
    // loveme,
    HomeMain,
  }
}
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



