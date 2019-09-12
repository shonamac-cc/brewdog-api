<template>
  <div class="details-box">
    <div>
      <img class="beer-image" :src="selectedBeer.image_url" alt />
    </div>
    <div class="beer-text">
      <p>{{ selectedBeer.name }}</p>
      <p>{{ selectedBeer.abv }}</p>
      <p>{{ selectedBeer.food_pairing }}</p>
      <p>{{ selectedBeer.description }}</p>
    </div>
  </div>
</template>

<script>
export default {
  name: 'beer-details',
  props: ['selectedBeer']
};
</script>

<style scoped>
.details-box {
  display: flex;
  flex-direction: row;
  margin: 20px;
}

.beer-image {
  height: 250px;
}

.beer-text {
}
</style>
