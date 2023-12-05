<template>
  <div class="food-list">
    <div v-if="food">
      <h3 class="food-title">{{ food.Name }}</h3>
      <table class="food-details">
        <tr>
          <th>Field</th>
          <th>Information</th>
        </tr>
        <tr>
          <td>ID</td>
          <td>{{ food.id }}</td>
        </tr>
        <tr>
          <td>Name</td>
          <td>{{ food.Name }}</td>
        </tr>
        <tr>
          <td>Type</td>
          <td>{{ food.Type }}</td>
        </tr>
        <tr>
          <td>Popularity</td>
          <td>{{ food.Popularity }}</td>
        </tr>
        <tr>
          <td>Rating</td>
          <td>{{ food.Rating }}</td>
        </tr>
        <tr>
          <td>Review</td>
          <td>{{ food.Review }}</td>
        </tr>
      </table>
    </div>
    <p v-else class="initial">Click on a food item to find details about it.</p>
  </div>
</template>

<script>
export default {
  name: 'FoodInfo',
  props: {
    food: {
      type: Object,
      default: null,
    },
  },
};
</script>

<style scoped>
.initial {
  color: white;
}

.food-title {
  color: #fff; /* Set the font color of the title to white */
}

.food-list {
  width: 50%;
  margin: 0 auto;
  margin-top: 40px;
  display: inline-block;
  border: 1px solid #c9b7a2;
  padding: 20px;
  border-radius: 4px;
  box-shadow: 0 0 5px rgba(0, 0, 0, 0.1);
  background-color: #0b3d91;
}

.food-details {
  width: 100%;
  color: #fff;
  border-collapse: collapse;
  margin-top: 20px;
}

.food-details th,
.food-details td {
  border: 1px solid #ccc;
  padding: 8px;
  text-align: left;
}

.food-details th {
  background-color: #fff;
  font-weight: bold;
  color: #000;
}
</style>
