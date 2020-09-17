<template>
  <div class="container">
    <h1>IP Address Tracker</h1>
    <form class="ip-form">
      <input
        class="ip-input"
        type="text"
        placeholder="Search for any IP address or domain"
      />
      <img src="../assets/icon-arrow.svg" alt class="ip-icon" />
    </form>
  </div>
</template>


<script>


export default {
  name: "SearchBar",
  props: {},
 
};
</script>

<style scoped>
.container {
  display: grid;
  place-items: center;
  height: 30vh;
  background: url(../assets/pattern-bg.png);
  padding-bottom: 220px;
  padding-top: 50px;
}
.container h1 {
  color: #fff;
  padding-bottom: 20px;
}
.ip-form {
  display: flex;
  align-items: center;
  justify-content: center;
  width: 100%;
}
.ip-input {
  font-size: 20px;
  padding: 20px;
  width: 40%;
  outline: none;
  border: none;
  border-radius: 20px 0px 0px 20px;
}
.ip-input:focus-within {
  outline: 1px solid purple;
}
.ip-input::placeholder {
  font-size: 20px;
}
.ip-icon {
  padding: 25px;
  background: hsl(0, 0%, 17%);
  color: hsl(0, 0%, 59%);
  text-align: center;
  border-radius: 0px 20px 20px 0px;
}
.ip-icon:hover {
  background: hsl(0, 0%, 29%);
}
</style>