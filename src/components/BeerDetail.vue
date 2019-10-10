<template lang="html">
  <div v-if="beer">
    <h3>{{beer.name}}</h3>
    <p>Description: {{beer.description}}</p>
    <p>Tagline: {{beer.tagline}}</p>
    <p>First_brewed: {{beer.first_brewed}}</p>
    <div class="beer">
      <img :src="beer.image_url" :alt="beer.name" >
    </div>
  </div>
</template>

<script>
export default {
  name: 'beer-detail',
  props: ['beer']
}
</script>

<style lang="css" scoped>

  .beer img {
    height: 300px;;
    width: 100px;
  }
</style>
