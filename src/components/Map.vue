<template>
<<<<<<< HEAD
  <div style="height: 100%; width: 100%;">
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
=======
  <div style="height: 100%; width: 100%">
    <l-map ref="map" v-model:zoom="zoom" :center="markerLatLng">
      <l-tile-layer
        :url="url"
        :attribution="attribution"
        layer-type="base"
        name="OpenStreetMap"
      ></l-tile-layer>
      <l-marker :lat-lng="markerLatLng" :icon="icon"></l-marker>
    </l-map>
>>>>>>> 25925512a4670f8e971cb2a841eff4b4b2707003
  </div>
</template>

<script lang="ts">
import "leaflet/dist/leaflet.css";
<<<<<<< HEAD
import { 
  LMap, 
  LTileLayer,
  LMarker,
  LIcon,
  LPopup,
} from "@vue-leaflet/vue-leaflet";
import L from "leaflet";
import icon from "../images/marker-icon.png"

export default {
  name: "Map",
=======
import { LMap, LTileLayer, LMarker, LIcon } from "@vue-leaflet/vue-leaflet";
import L from "leaflet";

export default {
>>>>>>> 25925512a4670f8e971cb2a841eff4b4b2707003
  components: {
    LMap,
    LTileLayer,
    LMarker,
    LIcon,
<<<<<<< HEAD
    LPopup
=======
>>>>>>> 25925512a4670f8e971cb2a841eff4b4b2707003
  },
  data() {
    return {
      url: "https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png",
      attribution:
<<<<<<< HEAD
        '&copy; <a target="_blank" href="http://osm.org/copyright">OpenStreetMap</a>',
      zoom: 8,
      markerLatLng: ["47.31322", "-1.319482"],
      icon: L.icon({
        iconUrl: icon,
        iconAnchor: [16, 37]
      }),
    };
  },
  props: ["lat", "lng"],

};
</script>
=======
        '&copy; <a target="_blank" href="http://osm.org/copyright">OpenStreetMap</a> contributors',
      zoom: 8,
      markerLatLng: [47.31322, -1.319482],
      icon: L.icon({
        iconUrl: "../../node_modules/leaflet/dist/images/marker-icon.png",
        iconAnchor: [16, 37],
      }),
    };
  },
};
</script>

<style lang="scss"></style>
>>>>>>> 25925512a4670f8e971cb2a841eff4b4b2707003
