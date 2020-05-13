<template>
    <div class="main-container">
      <h1>Hello World!</h1>
      
    </div>
</template>

<script>
import CountryList for '.' 
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
    
  }

}
</script>





<style>
.main-container {
  display: flex;
  justify-content: space-between;
}
</style>
