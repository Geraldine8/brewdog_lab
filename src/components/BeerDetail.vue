<template lang="html">
  <div v-if="beer">
    <h3>{{beer.name}}</h3>
    <button v-on:click="addToFavourites">Add to favourite</button>
    <!-- <button v-on:click="addToFavourites"</button> -->
    <p>Description: {{beer.description}}</p>
    <p>Tagline: {{beer.tagline}}</p>
    <p>First_brewed: {{beer.first_brewed}}</p>
    <div class="beer">
      <img :src="beer.image_url" :alt="beer.name" >
    </div>
  </div>
</template>

<script>
import {eventBus} from '../main.js'

export default {
  name: 'favourite-beer',
  props: ['beer'],
  methods: {
    addToFavourites(){
      eventBus.$emit('beer-favourited', this.beer)
    }
  }
}
</script>

<style lang="css" scoped>

  .beer img {
    height: 300px;;
    width: 100px;
  }
</style>
