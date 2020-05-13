<template>
  <div class="main-container">
    <h1>Country List</h1>
    <country-list :countries="countries"></country-list>
    <more-details :countries="selectedCountry"></more-details>
  </div>
</template>

<script>
import {eventBus} from "./main.js"
import CountryList from "./components/CountryList.vue";
import MoreDetails from "./components/MoreDetails.vue";

export default {
  name: "app",
  data() {
    return {
      countries: [],
      selectedCountry: null
    };
  },
  mounted() {
    fetch("https://restcountries.eu/rest/v2/all")
      .then(res => res.json())
      .then(countries => (this.countries = countries));

      eventBus.$on("country-selected", country => {
        this.selectedCountry = country;
      })
  },
  components: {
    "country-list": CountryList,
    "more-details": MoreDetails
  }
};
</script>


<style>
/* .main-container {
  display: flex;
  justify-content: space-between;
} */
</style>
