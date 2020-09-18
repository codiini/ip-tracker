<template>
  <div id="app">
    <SearchBar />
    <InfoBoard :locationData="locationData" :ipData="ipData" :ispData="ispData" />
  </div>
</template>

<script>
import SearchBar from "./components/SearchBar";
import InfoBoard from "./components/InfoBoard";
const apiKey = process.env.VUE_APP_API;
const url = `https://geo.ipify.org/api/v1?apiKey=${apiKey}`;
export default {
  name: "App",
  components: {
    SearchBar,
    InfoBoard,
  },
  data() {
    return {
      locationData: {},
      ipData: "",
      ispData: "",
    };
  },
  mounted: function () {
    fetch(url)
      .then((response) => response.json())
      .then((responseData) => {
        this.locationData = responseData.location;
        this.ipData = responseData.ip;
        this.ispData = responseData.isp;

        console.log(responseData);
      });
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
