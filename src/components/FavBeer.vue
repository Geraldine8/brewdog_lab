<template lang="html">
  <div class="">
    <span>
      <beers-list-name v-for="(beer, index) in beers" :beer="beer" :key="index" :shouldDelete='true'></beers-list-name>
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
</style>
