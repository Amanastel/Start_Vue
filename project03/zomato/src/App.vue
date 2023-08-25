<template>
  <div id="app">
    <header>
      <h1>Delicious Dishes Menu</h1>
      <filter-options @filtersApplied="applyFilters" />
    </header>
    <div class="menu">
      <Home v-for="dish in filteredDishes" :key="dish.idMeal" :dish="dish" />
    </div>
  </div>
</template>

<script>
import Home from './components/Home.vue';
import FilterOptions from './components/FilterOptions.vue';
import axios from 'axios';

export default {
  name: 'App',
  components: {
    Home,
    FilterOptions,
  },
  data() {
    return {
      dishes: [],
      selectedCategory: '', // Store selected category for filtering
    };
  },
  created() {
    // Fetch dish data from the API with initial category 'seafood'
    this.fetchDishes('seafood');
  },
  methods: {
    applyFilters(selectedCategory) {
      this.selectedCategory = selectedCategory;
      this.fetchDishes(selectedCategory); // Fetch dishes based on the selected category
    },
    fetchDishes(category) {
      axios
        .get(`https://www.themealdb.com/api/json/v1/1/filter.php?c=${category}`)
        .then((response) => {
          this.dishes = response.data.meals;
          console.log(response);
        })
        .catch((error) => {
          console.error('Error fetching dish data:', error);
        });
    },
  },
  computed: {
  filteredDishes() {
    console.log('Selected category:', this.selectedCategory);
    if (!this.selectedCategory) {
      return this.dishes;
    } else {
      const filtered = this.dishes.filter((dish) => {
        return dish.strCategory && dish.strCategory.toLowerCase() === this.selectedCategory.toLowerCase();
      });
      console.log('Filtered dishes:', filtered);
      return filtered;
    }
  },
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
