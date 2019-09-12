<template>
  <div>
    <beer-card v-for="(beer, index) in beers" :beer="beer" :key="index"></beer-card>
  </div>
</template>

<script>
import { eventBus } from '@/main.js';

import BeerCard from '@/components/BeerCard.vue';

export default {
  name: 'beers-list',
  data() {
    return {};
  },
  props: ['beers'],
  components: {
    'beer-card': BeerCard
  }
};
</script>

<style scoped>
</style>
