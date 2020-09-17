<template>
  <div class="container">
    <div class="main">
      <ul class="list-container">
        <li class="list-item">
          <p>ip address</p>
          <h2 id="ip-address-result">192.212.174.101</h2>
        </li>
        <hr>
        <li class="list-item">
          <p>location</p>
          <h2 class="location-result">Brooklyn, NY 10001</h2>
        </li>
        <hr>
        <li class="list-item">
          <p>timezone</p>
          <h2 class="time-zone-result">UTC -05:00</h2>
        </li>
        <hr>
        <li class="list-item">
          <p>isp</p>
          <h2 class="isp-result">
            SpaceX
            Starlink
          </h2>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  name: "InfoBoard",
  props: {},
};
</script>

<style scoped>
.container {
  position: relative;
  display: flex;
  align-items: center;
  justify-content: center;
  width: 100%;
}
.main {
  position: absolute;
  top: -50px;
  background: #fff;
  width: 75%;
  border-radius: 10px;
  height: 20vh;
  -webkit-box-shadow: 3px 12px 31px 0px rgba(0, 0, 0, 0.75);
  -moz-box-shadow: 3px 12px 31px 0px rgba(0, 0, 0, 0.75);
  box-shadow: 3px 12px 31px 0px rgba(0, 0, 0, 0.75);
}
.list-container {
  display: flex;
  align-items: center;
  justify-content: center;
  list-style-type: none;
}
p {
  text-transform: uppercase;
}
.list-item {
  margin: 30px 50px;
}
.list-item p {
  margin-bottom: 10px;
}
hr{
  width:1px;
  height:70px;
}
</style>
