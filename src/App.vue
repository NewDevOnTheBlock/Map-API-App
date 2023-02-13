<template>
  <div class="container">
    <div class="map">
      <Map :lat="lat" :lon="lon" />
    </div>
    <div class="search">
      <Search @position="position($event)" />
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
  data() {
    return {
      lat: 0,
      lon: 0,
    };
  },
  methods: {
    position(event: any) {
      this.lat = event.lat;
      this.lon = event.lon;
    },
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

  .map,
  .search {
    width: 50%;
    height: 100vh;
  }
}

.search {
  background: rgb(31, 31, 31);
}

// Removing Scrollbar
body {
  -ms-overflow-style: none; /* for Internet Explorer, Edge */
  scrollbar-width: none; /* for Firefox */
  overflow-y: scroll;
  &::-webkit-scrollbar {
    display: none; /* for Chrome, Safari, and Opera */
  }
}

@media screen and (max-width: 912px) {
  .container {
    flex-direction: column;

    .map,
    .search {
      width: 100%;
      height: 50vh;
    }
  }

  .list {
    height: calc(100vh - (50vh + 146px));
    overflow-y: scroll;
  }
}
</style>
