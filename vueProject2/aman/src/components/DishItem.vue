<template>
    <div class="app">
      <h1>TastyVue Menu</h1>
      <div class="menu">
        <!-- Display a message if dishes array is empty or still loading -->
        <p v-if="dishes.length === 0 && isLoading">Loading...</p>
        <p v-else-if="dishes.length === 0">No dishes available.</p>
        <!-- Loop through and render DishItem components -->
        <div v-else>
          <DishItem v-for="dish in dishes" :key="dish.idMeal" :dish="dish" />
        </div>
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
        dishes: [], // Initialize as an empty array
        isLoading: true // Add a loading indicator
      };
    },
    created() {
      axios
        .get("https://www.themealdb.com/api/json/v1/1/categories.php")
        .then(response => {
          // Store the retrieved data in the "dishes" array and set isLoading to false
          this.dishes = response.data.categories;
          this.isLoading = false;
        })
        .catch(error => {
          console.error("Error fetching dish data:", error);
        });
    }
  };
  </script>
  