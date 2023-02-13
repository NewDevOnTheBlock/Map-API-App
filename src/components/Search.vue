<template>
  <div class="search-input" style="margin: 15px 15px 0px 15px">
    <v-text-field
      v-model:String="text"
      ref="input"
      @keyup.enter="onClick"
      bg-color="blue"
      append-inner-icon="fa:fas fa-search"
    ></v-text-field>
  </div>
  <div class="button" style="margin: 0px 15px 15px 15px">
    <v-btn block color="blue" @click="onClick"> Search </v-btn>
  </div>
  <hr />
  <div class="list">
    <v-list density="compact" style="padding: 0">
      <v-list-item
        v-for="(item, i) in items"
        :key="i"
        :value="item"
        active-color="blue"
        style="border-bottom: 1px solid grey; transition: 0.3s"
        @click="setPosition(item)"
      >
        <template v-slot:prepend>
          <img
            src="../../node_modules/leaflet/dist/images/marker-icon.png"
            style="width: 50%"
          />
        </template>

        <v-list-item-title v-text="item['display_name']"></v-list-item-title>
      </v-list-item>
    </v-list>
  </div>
</template>

<script lang="ts">
const NOMINATIM_BASE_URL: string =
  "https://nominatim.openstreetmap.org/search?";
let params: object = {
  q: "",
  format: "json",
  addressdetails: "addressdetails",
};

export default {
  name: "Search",
  emits: ["position"],
  data() {
    return {
      text: "",
      items: [],
      icon: "../images/marker-icon.png",
    };
  },
  methods: {
    onClick() {
      // console.log((this.$refs['input'] as any).value)
      let searchText = (this.$refs["input"] as any).value;
      params = {
        q: searchText,
        format: "json",
        addressdetails: 1,
        polygon_geojson: 0,
      };

      const queryString = new URLSearchParams(
        params as {
          q: string;
          format: string;
          addressdetails: string;
          polygon_geojson: string;
        }
      ).toString();

      fetch(`${NOMINATIM_BASE_URL}${queryString}`, {
        method: "GET",
        redirect: "follow",
      })
        .then((res) => res.text())
        .then((result) => {
          // console.log(JSON.parse(result));
          this.items = JSON.parse(result);
        })
        .catch((err) => console.error(err));
    },
    setPosition(item: any) {
      // console.log([item.lat, item.lon]);
      this.$emit("position", item);
    },
  },
};
</script>

<style>
@media (hover: hover) {
  .v-list-item:hover {
    background-color: lightgrey;
  }
}
</style>
