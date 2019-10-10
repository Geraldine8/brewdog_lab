<template lang="html">
  <div>
    <h3 v-if="beers.length > 0">Favourite Beers</h3>
    <span>
      <beers-list-name v-for="(beer, index) in beers" :beer="beer" :key="index" :shouldDelete='true' class="fav-beer"></beers-list-name>
    </span>
  </div>
</template>

<script>
import BeersListName from './BeersListName.vue'

export default {
  name:'favourite-beers',
  props: ['beers'],
  components:{
    "beers-list-name": BeersListName
  }
}
</script>

<style lang="css" scoped>

.fav-beer {
  list-style: none;
}

</style>
