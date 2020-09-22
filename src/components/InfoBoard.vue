<template>
  <div class="container">
    <div class="main">
      <div class="result-container">
        <div class="result">
          <p>ip address</p>
          <h2>{{ipData}}</h2>
        </div>
        <hr />
        <div class="result">
          <p>location</p>
          <h2>{{locationData.city}}, {{locationData.region}}</h2>
        </div>
        <hr />
        <div class="result">
          <p>timezone</p>
          <h2>UTC {{locationData.timezone}}</h2>
        </div>
        <hr />
        <div class="result">
          <p>isp</p>
          <h2>{{ispData}}</h2>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "InfoBoard",
  props: ["locationData", "ipData", "ispData"],
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
  display: flex;
  align-items: center;
  justify-content: center;
  margin: 20px auto 0 auto;
  position: absolute;
  top: -130px;
  z-index: 100;
  background: #fff;
  min-width: 80%;
  border-radius: 10px;
  min-height: 20vh;
  -webkit-box-shadow: 3px 12px 31px 0px rgba(0, 0, 0, 0.75);
  -moz-box-shadow: 3px 12px 31px 0px rgba(0, 0, 0, 0.75);
  box-shadow: 3px 12px 31px 0px rgba(0, 0, 0, 0.75);
}
.result-container {
  display: flex;
  align-items: center;
  justify-content: center;
}
p {
  text-transform: uppercase;
}
.result {
  margin: 30px;
  display: grid;
  place-items: center;
}
.result p {
  margin-bottom: 10px;
}
hr {
  width: 1px;
  height: 70px;
  position: relative;
  top: 15px;
}

/* Media Queries */

/* Mobile styles */
@media only screen and (max-width: 700px) {
  .main {
    height: auto;
    top: -160px;
  }
  hr {
    display: none;
  }
  .result-container {
    flex-direction: column;
  }
  .result {
    margin: 15px;
  }
  .result p {
    text-align: center;
    margin-bottom: 3px;
  }
  .result h2 {
    text-align: center;
  }
}
</style>
