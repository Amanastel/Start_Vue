<template>
  <div>
    <p v-html="rowhtml"></p>
    <div class="home">
      <div class="flx">
        <users />
        <Products />
      </div>
      <h1>{{ name }}</h1>
      <h3>{{ a+b }}</h3>
      <h3>{{ok?'YES':'NO' }}</h3>
      <button v-bind:disabled="disbalebtn" v-on:click="updateText" > click me</button>
    </div>
    
  </div>
</template>

<script>
import users from "./users-main.vue";
import Products from "./Products.vue";
export default {
  name: "Home-main",
  components: {
    users,
    Products,
  },
  data() {
    return {
      name: "Aman",
      a:10,
      b:200,
      ok:true,
      rowhtml:'<h1>home components</h1>',
      disbalebtn:false,

    };
  },
  methods:{
    updateText(){
        this.name="Aman Kumar",
        this.ok= !this.ok
        this.disbalebtn = !this.disbalebtn
    }
  }
};
</script>

<style scoped>
.home {
  background-color: rgb(113, 242, 175);
  height: 500px;
  width: 90%;
  margin: auto;
  padding: 10px;
  /* display: flex; */
}
.flx{
    display: flex;
}
</style>
