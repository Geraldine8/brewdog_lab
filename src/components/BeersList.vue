<template lang="html">
  <div class="">
    <h3>Beers</h3>
    <span>
      <beers-list-name v-for="(beer, index) in beers" :beer="beer" :key="index" ></beers-list-name>
    </span>
  </div>
</template>

<script>
import BeersListName from './BeersListName.vue'

export default {
  name:'beers-list',
  props: ['beers'],
  components:{
    "beers-list-name": BeersListName
  }
}
</script>

<style lang="css" scoped>

</style>
