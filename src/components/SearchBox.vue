<template lang="html">
  <div>
  <input type="text" v-model="searchInput" v-on:input="search" />
    <div v-if="filteredCountries.length > 0">
      <p v-for="country in filteredCountries">{{country.name}}</p>
    </div>
  </div>
</template>

<script>
export default {
  data(){
    return {
      searchInput: '',
      filteredCountries: []
    }
  },
  name: 'search-box',
  props: ['countries'],
  methods: {
    search(){
      const filteredCountries = this.countries.filter(country => country.name.includes(this.searchInput)?)
      this.filteredCountries = filteredCountries
    }
  }
}
</script>

<style lang="css" scoped>
</style>
