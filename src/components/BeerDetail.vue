<template lang="html">
  <div v-if="beer">
    <h3>{{beer.name}}</h3>
    <p>Description: {{beer.description}}</p>
    <p>Tagline: {{beer.tagline}}</p>
    <p>First_brewed: {{beer.first_brewed}}</p>
  </div>
</template>

<script>
export default {
  name: 'beer-detail',
  props: ['beer']
}
</script>

<style lang="css" scoped>
</style>
