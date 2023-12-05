<template>
  <div id="app">
    <h1>FOOD IDENTITY</h1>
    <FoodSelector :foods="foods" @select="selectfood" />
    <FoodInfo :food="selectedfood" />
  </div>
 
  <div class="About">
    <h1><button class="button" style="vertical-align:middle"><span><a href="https://finalnodeproject.onrender.com"> About Me </a></span></button></h1>
    </div>
    
</template>

<script>
import FoodSelector from './components/FoodSelector.vue';
import FoodInfo from './components/FoodInfo.vue';

export default {
  name: 'App',
  components: {
    FoodSelector,  
    FoodInfo,     
  },
  data() {
    return {
      foods: [],
      selectedfood: null,
    };
  },
  async created() {
    await this.fetchfoods();
  },
  methods: {
    async fetchfoods() {
      const apiUrl = 'https://finalnodeproject.onrender.com/api';

      try {
        const response = await fetch(apiUrl);
        const data = await response.json();
        this.foods = data;
      } catch (error) {
        console.error('Error fetching data:', error);
      }
    },
    selectfood(food) {
      this.selectedfood = food;
    },
  },
};
</script>

<style>
html,
body {
  height: 100%;
}

body {
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;
  background-color: whitesmoke;
  background-image: url('@/assets/fooditems.jpg'); 
}



#app {
  font-family: bold, Arial, Helvetica, sans-serif;
  color: #515054;
  text-align: center;
  max-width: 1200px;
  margin: 0 auto;
  min-height: 100%;
}

h1 {
  font-size: 36px;
  margin-bottom: 30px;
  color: navy;
  margin-bottom: 20px;
  font-weight: bold;
  
}

button{
  font-size: 20px;
  border: 2px solid #0b3d91;
  padding: 10px 20px;
}
</style>
