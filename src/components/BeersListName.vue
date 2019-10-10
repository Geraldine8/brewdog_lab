<template lang="html">
  <span>
    <li v-on:click="handleClick">{{beer.name}}</li>
    <button v-if="shouldDelete" v-on:click="handleDelete">Remove</button>
  </span>
</template>

<script>
import{eventBus} from '../main.js'
export default {
  name: 'beers-list-name',
  props: ['beer', 'shouldDelete'],
  methods: {
    handleClick(){
      eventBus.$emit('beer-selected', this.beer)
    },
    handleDelete(){
      eventBus.$emit('beer-favourite-deleted', this.beer)
    }
  }
}
</script>

<style lang="css" scoped>
</style>
