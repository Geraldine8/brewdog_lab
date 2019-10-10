<template lang="html">
  <div>
    <span>
      <li v-on:click="handleClick">
        {{beer.name}} <button v-if="shouldDelete" v-on:click="handleDelete" class="btn">Remove</button>
      </li>
    </span>
  </div>
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

.btn {
  /* display: flex;
   flex-direction: row; */
  /* margin-right:100px; */
  /* display:inline-block; */


}
</style>
