<template>
  <div id="map"></div>
</template>

<script>
export default {
  name: "Map",
  props: ["longitude", "latitude"],
  data() {
    return {};
  },
  // MOunted lifecycle to load the map upon page load
  mounted() {
    this.loadMap();
  },
  // watch props for any change in value and the calls map function
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
        center: [this.longitude, this.latitude],
        zoom: 5,
      });
      map.addControl(new mapboxgl.NavigationControl());

      let geojson = {
        type: "FeatureCollection",
        features: [
          {
            type: "Feature",
            properties: {
              message: "Foo",
              iconSize: [60, 60],
            },
            geometry: {
              type: "Point",
              coordinates: [this.longitude, this.latitude],
            },
          },
        ],
      };
// This loops through the features array in the geojson object to create a marker for each feature
      geojson.features.forEach(function (marker) {
        new mapboxgl.Marker()
          .setLngLat(marker.geometry.coordinates)
          .addTo(map);
      });
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
