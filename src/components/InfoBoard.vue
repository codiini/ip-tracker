<template>
  <div class="container">
    <div class="main">
      <ul class="list-container">
        <li class="list-item">
          <p>ip address</p>
          <h2 id="ip-address-result">{{ipData}}</h2>
        </li>
        <hr>
        <li class="list-item">
          <p>location</p>
          <h2 class="location-result">{{locationData.city}},{{locationData.region}}</h2>
        </li>
        <hr>
        <li class="list-item">
          <p>timezone</p>
          <h2 class="time-zone-result">UTC {{locationData.timezone}}</h2>
        </li>
        <hr>
        <li class="list-item">
          <p>isp</p>
          <h2 class="isp-result">
            {{ispData}}
          </h2>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  name: "InfoBoard",
  props: ["locationData","ipData","ispData"],
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
  z-index: 100;
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
  margin: 30px;
}
.list-item p {
  margin-bottom: 10px;
}
hr{
  width:1px;
  height:70px;
  position:relative;
  top:15px;
}
</style>
