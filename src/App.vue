<template>
  <div id="app">
    <div class="nav">
      <header>Brewdog Beers</header>
    </div>
    <div class="content">
      <div>
        <fav-beers :favBeers="favBeers"></fav-beers>
      </div>
      <div class="beer-content">
        <beers-list class="beer-list" :beers="beers"></beers-list>
        <beer-details v-if="selectedBeer" class="beer-details" :selectedBeer="selectedBeer"></beer-details>
      </div>
    </div>
  </div>
</template>

<script>
import BeersList from '@/components/BeersList.vue';
import BeerDetails from '@/components/BeerDetails.vue';
import FavBeers from '@/components/FavBeers.vue';

import { eventBus } from '@/main.js';

export default {
  name: 'app',
  data() {
    return {
      beers: [],
      selectedBeer: null,
      favBeers: []
    };
  },
  components: {
    'beers-list': BeersList,
    'beer-details': BeerDetails,
    'fav-beers': FavBeers
  },
  mounted() {
    fetch('https://api.punkapi.com/v2/beers')
      .then(response => response.json())
      .then(beers => (this.beers = beers));

    eventBus.$on('beer-selected', beer => {
      this.selectedBeer = beer;
    });
    eventBus.$on('fav-selected', beer => {
      this.favBeers.push(beer);
    });
  }
};
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.content {
  display: flex;
  flex-direction: row;
}

.beer-content {
  display: flex;
  flex-direction: row;
}

.beer-list {
  min-width: 40vw;
  border: black;
  border-style: solid;
}

.nav {
  height: 46px;
  background-color: #00afdb;
  padding-left: 160px !important;
}

header {
  font-size: 30px;
  background-color: #00afdb;
  height: 46px;
  text-align: center;
  color: #ffffff;
  font-weight: bold;
}
</style>
