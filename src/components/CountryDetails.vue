<template lang="html">
  <div v-if="country">
    <h1>{{country.name}}</h1>
      <p>Capital: {{country.capital}}</p>
      <p>Population: {{country.population}}</p>
      <p>Languages: {{this.getLanguages()}}</p>
      <img :src="country.flag" alt="">
  </div>
</template>

<script>
export default {
  name: 'country-details',
  props: ['country'],
  methods: {
    getLanguages(){
    const languages = this.country.languages.map(language => language.name).join(', ')
    return languages
    }
  }
}
</script>

<style lang="css" scoped>
/* div {
  position: fixed;
  top: 0;
  right: 30px;
} */
img {
  width: 100px;
  height: auto;
}
</style>
