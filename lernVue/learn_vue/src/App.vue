<template>
  <div id="app">
    <!-- <img alt="Vue logo" src="./assets/logo.png"> -->
    <!-- <HelloWorld msg="Welcome to Your Vue.js App"/> -->
    <!-- <Homes msg="hello world"/> -->
    <Databind/>
    <loveme msg="hello world"/>
    
    <HomeMain/>
   
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
// import Homes from './components/HomePage.vue'
// import loveme from './components/Love-me.vue'
import HomeMain from './components/Home-main.vue'
import Databind from './components/Databind.vue'


export default {
  name: 'App',
  components: {
    // HelloWorld,
    // Homes,
    // loveme,
    HomeMain,
    Databind,
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



