<template lang="html">
  <div>
  <input type="text" v-model="searchInput" v-on:input="search" />
    <div v-if="filteredCountries.length > 0" v-for="(country, index) in filteredCountries" :key="index">
      <country-details :country='country'></country-details>
    </div>
  </div>
</template>

<script>
import CountryDetails from './CountryDetails.vue';

export default {
  data(){
    return {
      searchInput: '',
      filteredCountries: []
    }
  },
  name: 'search-box',
  props: ['countries'],
	components: {
		"country-details": CountryDetails
	},
  methods: {
    search(){
      const filteredCountries = this.countries.filter(country => country.name.toLowerCase().includes(this.searchInput.toLowerCase()));
      this.filteredCountries = filteredCountries
    }
  }
}
</script>

<style lang="css" scoped>
</style>
