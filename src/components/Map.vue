<template>
  <div id="map"></div>
</template>

<script>
export default {
  name: "Map",
  data() {
    return {};
  },
  mounted() {
    this.loadMap();
  },
  watch: {
    longitude() {
      this.loadMap();
    },
    latitude() {
      this.loadMap();
    },
  },
  methods: {
    loadMap() {
      let mapboxgl = require("mapbox-gl/dist/mapbox-gl.js");
      mapboxgl.accessToken =
        "pk.eyJ1IjoiaW5pdWJvbmciLCJhIjoiY2tmOW9mYTF0MGhkZzJ5b2Y0ZDBqMGhhbyJ9.Y7n1D7Gde0TMqwHsAr0Kng";
      let map = new mapboxgl.Map({
        container: "map",
        style: "mapbox://styles/mapbox/streets-v11",
        center: [this.locationData.lng, this.locationData.lat],
        zoom: 5,
      });
      map.addControl(new mapboxgl.NavigationControl());
    },
  },
};
</script>

<style scoped>
#map {
  position: relative;
  z-index: 1;
  height: 61vh;
  width: 100vw;
}
</style>
