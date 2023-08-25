<template>
    <div class="filters">
      <label for="mealCategory">Meal Category:</label>
      <select id="mealCategory" v-model="selectedCategory">
        <option value="">All</option>
        <option v-for="category in categories" :key="category" :value="category">
          {{ category }}
        </option>
      </select>
      <button @click="applyFilters">Apply Filters</button>
    </div>
  </template>
  
  <script>
  import axios from 'axios';
  
  export default {
    data() {
      return {
        categories: [], // Array to store meal categories
        selectedCategory: '', // Selected meal category for filtering
      };
    },
    created() {
      // Fetch meal categories from the API
      axios
        .get('https://www.themealdb.com/api/json/v1/1/categories.php')
        .then((response) => {
          this.categories = response.data.categories.map((category) => category.strCategory);
        })
        .catch((error) => {
          console.error('Error fetching meal categories:', error);
        });
    },
    methods: {
      applyFilters() {
        // Emit an event to notify the parent component about selected filters
        this.$emit('filtersApplied', this.selectedCategory);
      },
    },
  };
  </script>
  
  <style scoped>
  /* Your styles here */
  </style>
  