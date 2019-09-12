<template>
  <div class="fav-beers">
    <header>Favourites</header>
    <div v-for="(beer, index) in favBeers" :key="index">
      <p>{{ beer.name }}</p>
    </div>
  </div>
</template>

<script>
export default {
  name: 'fav-beers',
  props: ['favBeers']
};
</script>

<style scoped>
header {
  font-size: 30px;
  background-color: #00afdb;
  height: 46px;
  text-align: center;
  vertical-align: center;
  color: #ffffff;
  font-weight: bold;
}

.fav-beers {
  height: 100%;
  width: 160px;
  position: fixed;
  z-index: 1;
  top: 0;
  left: 0;
  background-color: #111;
  overflow-x: hidden;
  padding-top: 0px;
  color: #ffffff;
  font-weight: bold;
}

/* .sidenav a {
  padding: 6px 8px 6px 16px;
  text-decoration: none;
  font-size: 25px;
  color: #818181;
  display: block;
}

.sidenav a:hover {
  color: #f1f1f1;
} */
</style>
