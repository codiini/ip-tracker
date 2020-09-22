<template>
  <div id="app">
    <SearchBar @domainData="domainNameCall" />
    <InfoBoard :locationData="locationData" :ipData="ipData" :ispData="ispData" />
    <Map :longitude="longitude" :latitude="latitude" />
  </div>
</template>

<script>
import SearchBar from "./components/SearchBar";
import InfoBoard from "./components/InfoBoard";
import Map from "./components/Map";
const apiKey = process.env.VUE_APP_IP_API;
export default {
  name: "App",
  components: {
    SearchBar,
    InfoBoard,
    Map,
  },
  data() {
    return {
      domainInput: "",
      locationData: {},
      ipData: "",
      ispData: "",
      longitude:"",
      latitude:"",
    };
  },
  mounted: function () {
    this.getData();
  },
  methods: {
    domainNameCall(payload) {
      this.domainInput = payload;
      this.getData();
    },
    getData() {
      const url = `https://geo.ipify.org/api/v1?apiKey=${apiKey}&domain=${this.domainInput}`;
      fetch(url)
        .then((response) => response.json())
        .then((responseData) => {
          this.locationData = responseData.location;
          this.latitude = responseData.location.lat;
          this.longitude = responseData.location.lng;
          this.ipData = responseData.ip;
          this.ispData = responseData.isp;
        });
    },
  },
};
</script>

<style>
@import url("https://fonts.googleapis.com/css2?family=Rubik:ital,wght@0,400;0,500;1,700&display=swap");

* {
  padding: 0;
  margin: 0;
  box-sizing: border-box;
  font-family: "Rubik", sans-serif;
}
</style>
