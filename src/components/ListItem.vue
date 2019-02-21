<template lang="html">
  <option v-on:click="handleClick" >{{country.name}}</option>
</template>

<script>


export default {
  name: 'list-item',
  props: ['country'],
}
</script>


<style lang="css" scoped>
</style>
