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
  
  .map, .search {
    width: 50%;
  }
}

.map {
  height: 100vh;
}

.search {
  background-color: grey;
}

@media screen and (max-width: 768px) {
  .container {
    flex-direction: column;

    .map, .search {
      width: 100%;
      height: 50vh;
    }
  }
}
</style>
