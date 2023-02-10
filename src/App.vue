<template>
  <div class="container">
    <div class="map">
      <Map />
    </div>
    <div class="search">
      <Search />
    </div>
  </div>
</template>

<script lang="ts">
import Map from "./components/Map.vue";
import Search from "./components/Search.vue";

export default {
  name: "App",
  components: {
    Map,
    Search,
  },
};
</script>

<style lang="scss">
// Resets
* {
  margin: 0;
  padding: 0;
}

.container {
  width: 100vw;
  height: 100vh;
  display: flex;
  flex-direction: row;
  
  div {
    width: 50%;
  }
}

.map {
  background-color: lightblue;
}

.search {
  background-color: grey;
}
</style>
