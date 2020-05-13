<template>
    <div class="main-container">
      <h1>Hello World!</h1>
      <country-list :countries="countries"></country-list>
    </div>
</template>

<script>
import CountryList from './components/CountryList.vue' ;
import MoreDetails from './components/MoreDetails.vue';

export default {
  name:"app",
  data() {
    return {
      countries: [],
      selectedCountry: null
    };
  },
  mounted(){
    fetch("https://restcountries.eu/rest/v2/all")
    .then(res => res.json())
    .then(countries =>(this.countries = countries));
  },
  components:{
    "country-list": CountryList,
    "more-details": MoreDetails
    
  }

}
</script>


<style>
.main-container {
  display: flex;
  justify-content: space-between;
}
</style>
