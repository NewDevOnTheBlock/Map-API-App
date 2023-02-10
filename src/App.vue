<template>
  <Map />
  <Search />
</template>

<script lang="ts">
  import Map from "./components/Map.vue"
  import Search from "./components/Search.vue"
  
  export default {
    name: 'App',
    components: {
      Map,
      Search
    }
  }
</script>

<style scoped lang="scss">

</style>
