<template>
    <div class="search-bar">
      <button
        v-for="food in foods"
        :key="food._id"
        @click="handleClick(food)"
        class="food-button"
        :class="{ selected: isSelected(food) }"
      >
        {{ food.Name }} 
      </button>
    </div>
  </template>
  
  <script>
  export default {
    name: 'foodSelector',
    props: {
      foods: {
        type: Array,
        default: () => [],
      },
    },
    data() {
      return {
        selectedfood: null,
      };
    },
    methods: {
      handleClick(food) {
        this.selectedfood = food;
        this.$emit('select', food);
      },
      isSelected(food) {
        return this.selectedfood === food;
      },
    },
  };
  </script>
  
  <style scoped>
  .search-bar {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    gap: 10px;
    margin-bottom: 40px;
  }
  
  .food-button {
    background-color: #0b3d91; /* Dark blue */
    border: 2px solid #0b3d91;
    color: #ffffff;
    padding: 10px 20px;
    text-align: center;
    text-decoration: none;
    display: inline-block;
    font-size: 16px;
    margin: 4px 2px;
    cursor: pointer;
    border-radius: 4px;
    transition-duration: 0.4s;
    box-shadow: 0 0 5px #c9b7a2;
    outline: none;
    transition-duration: 0.4s;
  }
  
  .food-button:hover,
  .food-button.selected {
    background-color: #034a04; /* Lighter shade of blue */
    color: #ffffff;
  }
  </style>
  