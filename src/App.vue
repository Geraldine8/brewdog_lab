<template lang="html">
  <div class="">
    <h2>Brewdog App</h2>
    <div class="wrapper">
      <beers-list :beers='beers'></beers-list>
    </div>
  </div>
</template>

<script>
import {evenBus} from './main.js';
import BeersList from './components/BeersList.vue'

export default {
  name: 'app',
  data(){
    return{
      beers: []
    }
  },

  mounted(){
    fetch('https://api.punkapi.com/v2/beers')
    .then(response => response.json())
    .then(beers => this.beers = beers)


  },

  components: {
    "beers-list": BeersList
  }


}








</script>

<style lang="css" scoped>
</style>
