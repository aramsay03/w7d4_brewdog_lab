<template lang="html">
<div>
<ul>
  <list-item v-for="(beer, index) in beers" :beer="beer" :key="index"></list-item>
</ul>

</div>
</template>

<script>
import ListItem from './ListItem.vue'
import {eventBus} from '../main.js'

export default {
  name: 'beer-select',
  props: ['beers'],
  components: {
    "list-item": ListItem
  },

  methods: {
    handleChange(event){
      eventBus.$emit('beer-change', this.beer)
    }
  }
}


</script>

<style lang="css" scoped>
</style>
