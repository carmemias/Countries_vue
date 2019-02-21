<template lang="html">
<div class="">
  <select v-on:change="handleChange">
    <list-item v-for="(country, index) in countries" :key="index" :country="country" ></list-item>
  </select>
</div>
</template>

<script>
import ListItem from './ListItem.vue';
import {eventBus} from '../main.js'

export default {
  name: 'countries-list',
  props: ['countries'],
  components: {
    'list-item': ListItem,
  },
  methods: {
    handleChange(){
      eventBus.$emit('clicked-country', countr)
    }
  }
}
</script>

<style lang="css" scoped>
</style>
