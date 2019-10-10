<template lang="html">
  <div class="">
    <h2>Brewdog App</h2>
    <div class="wrapper">
      <beers-list :beers='beers'></beers-list>
      <beer-detail :beer='selectedBeer' class="details"></beer-detail>
      <fav-beer :beers='favouriteBeer' class="details"></fav-beer>
    </div>
  </div>
</template>

<script>
import {eventBus} from './main.js';
import BeersList from './components/BeersList.vue';
import BeerDetail from './components/BeerDetail.vue';
import FavBeer from './components/FavBeer.vue';


export default {
  name: 'app',
  data(){
    return{
      beers: [],
      selectedBeer: null,
      favouriteBeer: []
    };
  },

  mounted(){
    fetch('https://api.punkapi.com/v2/beers')
    .then(response => response.json())
    .then(beers => this.beers = beers)

    eventBus.$on('beer-selected', (beer) =>{
      this.selectedBeer = beer;
    })

    eventBus.$on('beer-favourited', (beer) =>{
      if (this.favouriteBeer.includes(beer) === false) {
        this.favouriteBeer.push(beer)
      }
    })

    eventBus.$on('beer-favourite-deleted', (beer) =>{
      const beerPosition = this.favouriteBeer.indexOf(beer);
      this.favouriteBeer.splice(beerPosition, 1);
    })


  },

  components: {
    "beers-list": BeersList,
    "beer-detail": BeerDetail,
    "fav-beer": FavBeer
  }


}


</script>

<style lang="css" scoped>
.wrapper {
  display: flex;
  justify-content: space-around;
  /* background-color: #CBF3F0; */
}

h2 {
  text-align: center;
}
.details {
  /* border-style: inset; */
  /* border: 3px solid red; */
  width: 20%;
  padding: 10px;
}

</style>
