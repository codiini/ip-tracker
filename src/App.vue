<template>
  <div id="app">
    <div>
      {{data}}
    </div>
    <SearchBar />
    <InfoBoard></InfoBoard>
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
  mounted() {
    fetch(url)
      .then((response) => response.json())
      .then((data) => {
        console.log(data);
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
