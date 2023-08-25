<template>
    <div class="dish-item" v-if="dish">
      <img :src="dish.strMealThumb" :alt="dish.strMeal" />
      <h3>{{ dish.strMeal }}</h3>
    </div>
  </template>
  
  <script>
  export default {
    name: 'HomeItem', // Change 'Home-s' to 'HomeItem' for better naming
    props: {
      dish: Object // This prop will contain dish information
    }
  }
  </script>
  
  <style scoped>
  .dish-item {
    border: 1px solid #e2e2e2;
    border-radius: 8px;
    padding: 20px;
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
    text-align: center;
    margin: 20px;
    width: calc(25% - 40px); /* 25% width for each card with margin included */
    display: inline-block;
    vertical-align: top;
    transition: transform 0.2s ease-in-out;
  }
  
  .dish-item:hover {
    transform: translateY(-5px);
  }
  
  .dish-item img {
    max-width: 100%;
    border-radius: 8px;
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
    transition: transform 0.2s ease-in-out;
  }
  
  .dish-item img:hover {
    transform: scale(1.05);
  }
  
  .dish-item h3 {
    margin-top: 10px;
    font-size: 18px;
    font-weight: bold;
    color: #333;
  }
  </style>
  