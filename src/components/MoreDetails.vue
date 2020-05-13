<template lang='html'>
  <div>
      <ul>
        <h3>{{countries.name}}</h3>
        <p>Capital: {{countries.capital}}</p>
        <p>Region: {{countries.region}}</p>
        <p>Population: {{countries.population}}</p>
      </ul>
  </div>

</template>

<script>
export default {
  name:'more-details',
  props: ['countries']

}
</script>

<style>

</style>