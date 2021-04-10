<template>
  <div id="app">

    <label for="civilization_select">Select a Civilization:</label>
    <select id="civilization_select" v-model="selectedCivilization">
      <option disabled value="">Select a civilization</option>
      <option v-for="civilization in civilizations" :key="civilization.name" :value="civilization">{{civilization.name}}</option>
    </select>

    <civilization-detail v-if="selectedCountry" :selectedCountry="selectedCountry"/>

    <button v-if="!favouriteCivs.includes(selectedCivilization)" v-on:click="addToFavourites">Add Civilization</button>

    <favourite-civilizations :favouriteCs="favouriteCs"></favourite-countries>
</div>
</template>

<script>
import CivilizationDetail from './components/CivilizationDetail.vue';
import FavouriteCiv from './components/FavouriteCiv.vue';

export default {
  name: 'App',
  data() {
    return {
      civilizations: [],
      selectedCivilization: null,
      favouriteCivilization: []
    }
  },
  components: {
    'civilization-detail': CivilizationDetail,
    'favourite-Civilizations': FavouriteCiv
  },
  mounted(){
    this.getCivilizations()
  },
  methods: {
    getCivilizations: function(){
      fetch("https://age-of-empires-2-api.herokuapp.com/api/v1/civilizations")
      .then(res => res.json())
      .then(countries => this.countries = countries)
    },
    addToFavourites: function(){
      this.favouriteCivs.push(this.selectedCivilization)
    },
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
