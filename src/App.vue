<template lang="html">
  <div class="">
    <h2>Brewdog App</h2>
    <div class="wrapper">
      <beers-list :beers='beers'></beers-list>
      <beer-detail :beer='selectedBeer'></beer-detail>
    </div>
  </div>
</template>

<script>
import {eventBus} from './main.js';
import BeersList from './components/BeersList.vue';
import BeerDetail from './components/BeerDetail.vue'

export default {
  name: 'app',
  data(){
    return{
      beers: [],
      selectedBeer: null
    };
  },

  mounted(){
    fetch('https://api.punkapi.com/v2/beers')
    .then(response => response.json())
    .then(beers => this.beers = beers)

    eventBus.$on('beer-selected', (beer) =>{
      this.selectedBeer = beer;
    })

  },

  components: {
    "beers-list": BeersList,
    "beer-detail": BeerDetail
  }


}








</script>

<style lang="css" scoped>
</style>
