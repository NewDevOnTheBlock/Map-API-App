<template>
  <div style="height: 100%; width: 100%">
    <!-- @ready="onReady" -->
    <l-map
      ref="map"
      v-model:zoom="zoom"
      :center="
        parseFloat(lat) === 0
          ? markerLatLng
          : [parseFloat(lat), parseFloat(lon)]
      "
    >
      <l-tile-layer
        :url="url"
        :attribution="attribution"
        layer-type="base"
        name="OpenStreetMap"
      ></l-tile-layer>
      <l-marker
        :lat-lng="
          parseFloat(lat) === 0
            ? markerLatLng
            : [parseFloat(lat), parseFloat(lon)]
        "
        :icon="icon"
      ></l-marker>
    </l-map>
  </div>
  <!-- <h1>{{ [parseFloat(lat), parseFloat(lon)] }}</h1> -->
</template>

<script lang="ts">
import "leaflet/dist/leaflet.css";
import {
  LMap,
  LTileLayer,
  LMarker,
  LIcon,
  LPopup,
} from "@vue-leaflet/vue-leaflet";
import L from "leaflet";

export default {
  components: {
    LMap,
    LTileLayer,
    LMarker,
    LIcon,
    LPopup,
  },
  data() {
    return {
      url: "https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png",
      attribution:
        '&copy; <a target="_blank" href="http://osm.org/copyright">OpenStreetMap</a>',
      zoom: 8,
      markerLatLng: ["47.31322", "-1.319482"],
      icon: L.icon({
        iconUrl: "../../node_modules/leaflet/dist/images/marker-icon.png",
        iconAnchor: [16, 37],
      }),
    };
  },
  props: ["lat", "lon"],
  // methods: {
  //   onReady(mapObject: any) {
  //     let e = mapObject.locate({setView : true});
  //     console.log(mapObject)
  //   }
  // }
};
</script>
