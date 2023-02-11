<template>
  <div style="height: 100%; width: 100%">
    <l-map ref="map" v-model:zoom="zoom" :center="markerLatLng">
      <l-tile-layer
        :url="url"
        :attribution="attribution"
        layer-type="base"
        name="OpenStreetMap"
      ></l-tile-layer>
      <l-marker :lat-lng="markerLatLng">
        <l-icon :icon-url="icon"></l-icon>
      </l-marker>
    </l-map>
  </div>
</template>

<script lang="ts">
import "leaflet/dist/leaflet.css";
import { LMap, LTileLayer, LMarker, LIcon } from "@vue-leaflet/vue-leaflet";
import markerIcon from "../../node_modules/leaflet/dist/images/marker-icon.png";

export default {
  components: {
    LMap,
    LTileLayer,
    LMarker,
    LIcon
  },
  data() {
    return {
      url: "https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png",
      attribution:
        '&copy; <a target="_blank" href="http://osm.org/copyright">OpenStreetMap</a> contributors',
      zoom: 8,
      markerLatLng: [47.31322, -1.319482],
      icon: markerIcon,
    };
  },
};
</script>

<style lang="scss">

</style>
