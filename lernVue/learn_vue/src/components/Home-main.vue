<template>
  <div>
    <h1>home components</h1>
    <users/>
    <Products/>
  </div>
</template>

<script>
import users from './users-main.vue'
import Products from './Products.vue'
export default {
  name: "Home-main",
  components:{
    users,
    Products
  }
};
</script>

<style scoped>
div{
    background-color: rgb(113, 242, 175);
    height: 500px;
    width: 90%;
    margin: auto;

}
</style>
