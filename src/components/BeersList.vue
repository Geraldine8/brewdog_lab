<template lang="html">
  <div class="">
    <span>
      <beers-list v-for="(beer, index) in beers" :beer="beer" :key="index"></beers-list>
    </span>
  </div>
</template>

<script>
import BeersList from './BeersList.vue';

export default {
  name:'beers-list',
  props: ['beers'],
  components:{
    "beers-list": BeersList
  }
}
</script>

<style lang="css" scoped>
</style>
