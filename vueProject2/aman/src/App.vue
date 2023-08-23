<template>
  <div id="app">
    <h1>TastyVue Menu</h1>
    <div class="menu">
      <template v-if="dishes.length > 0">
        <DishItem v-for="dish in dishes" :key="dish.idMeal" :dish="dish" />
      </template>
      <p v-else>No dishes available.</p>
    </div>
  </div>
</template>

<script>
import DishItem from "@/components/DishItem.vue";
import axios from "axios";

export default {
  components: {
    DishItem
  },
  data() {
    return {
      dishes: [] // This array will hold the fetched dish data
    };
  },
  created() {
    // Fetch dish data from the API
    axios.get("https://www.themealdb.com/api.php")
      .then(response => {
        // Store the retrieved data in the "dishes" array
        this.dishes = response.data.meals;
      })
      .catch(error => {
        console.error("Error fetching dish data:", error);
      });
  }
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
.menu {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
}
</style>
