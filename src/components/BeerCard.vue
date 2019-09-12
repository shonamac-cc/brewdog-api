<template>
  <div>
    <div @click="handleClickBeer()">
      <p class="card-text">{{ beer.name }}</p>
    </div>
    <button @click="handleClickFav()">Add to favourites</button>
  </div>
</template>

<script>
import { eventBus } from '@/main.js';

export default {
  name: 'beer-card',
  data() {
    return {};
  },
  props: ['beer'],
  methods: {
    handleClickBeer() {
      eventBus.$emit('beer-selected', this.beer);
    },
    handleClickFav() {
      eventBus.$emit('fav-selected', this.beer);
    }
  }
};
</script>

<style scoped>
/* .wrapper {
  display: flex;
  max-width: 100%;
  flex-wrap: wrap;
  padding-top: 12px 6px 12px 6px;
}

.card {
  box-shadow: rgba(0, 0, 0, 0.117647) 0px 1px 6px,
    rgba(0, 0, 0, 0.117647) 0px 1px 4px;
  max-width: 200px;
  margin: 12px;
  transition: 0.15s all ease-in-out;
  display: flex;
  flex-direction: column;
  align-items: center;
}
.card:hover {
  transform: scale(1.1);
}

.card-text {
  padding: 8px 4px 8px 4px;
  text-decoration: none;
  padding: 12px;
  padding-top: 0px;
  color: #03a9f4;
  font-size: 1vw;
  text-align: center;
}

.thumbnail {
  width: 200px;
} */
</style>
