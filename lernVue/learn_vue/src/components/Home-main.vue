<template>
  <div>
      <h1 class="homeStyle">class and style bindings</h1>
      <h1 v-bind:style="{color:'blue'}">class and style bindings</h1>
      <h1 v-bind:class="{display:show}" >class bindings with object</h1>
      <h1 v-bind:class="[aClass]" >class bindings with Arryas</h1>

      


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
      show:true,
      aClass: 'arraysClass'

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

.homeStyle{
    color: orange;
}

.display{
    background-color: burlywood;
}

.arraysClass{
    background-color: cyan;
}
</style>
