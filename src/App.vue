<template>
<<<<<<< HEAD
  <main class="container">
    <div class="map">
      <Map :lat="lat" :lon="lon" />
    </div>
    <div class="search">
      <Search @position="position($event)"/>
    </div>
  </main>
</template>

<script lang="ts">
import Map from './components/Map.vue';
  import Search from './components/Search.vue';

  export default {
    name: "App",
    components: {
      Map,
      Search,
    },
    data() {
      return {
        lat: 0,
        lon: 0
      };
    },
    methods: {
      position(event: any) {
        this.lat = event.lat;
        this.lon = event.lon;
      }
    },
  };
</script>

<style lang="scss">

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
    background-color: rgb(31, 31, 31);
  }

  body {
    -ms-overflow-style: none; /* IE, edge */
    scrollbar-width: none; /* firefox */
    overflow-y: scroll;
    &::-webkit-scrollbar {
      display: none; /* chorme, safari, opera */
    }
  }

  @media screen and (max-width: 768px) {
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
=======
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
>>>>>>> 25925512a4670f8e971cb2a841eff4b4b2707003
    }
  }
</style>
