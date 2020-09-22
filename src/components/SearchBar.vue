<template>
  <div class="container">
    <h1>IP Address Tracker</h1>
    <form class="ip-form">
      <input
        class="ip-input"
        type="text"
        placeholder="Search for any IP address or domain"
        v-model="domainInput" @keyup.enter="searchDomain"
      />
      <button type="submit" @click.prevent="searchDomain"></button>
    </form>
  </div>
</template>


<script>
export default {
  name: "SearchBar",
  props: {},
  data() {
    return {
      domainInput: "",
    };
  },
  methods: {
    searchDomain() {
      this.$emit("domainData", this.domainInput);
    },
  },
};
</script>

<style scoped>
.container {
  display: grid;
  place-items: center;
  height: 50vh;
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
  width: 60%;
}
.ip-input {
  font-size: 20px;
  padding: 20px;
  width: 100%;
  outline: none;
  border: none;
  border-radius: 20px 0px 0px 20px;
}
.ip-input:focus-within {
  outline: 1px solid purple;
}
.ip-input::placeholder {
  font-size: 15px;
}
button {
  background-image: url("../assets/icon-arrow.svg");
  background-color: hsl(0, 0%, 17%);
  background-repeat: no-repeat;
  background-position: center;
  outline: none;
  border: none;
  border-radius: 0px 20px 20px 0px;
  padding: 33px;
}
button:hover {
  cursor: pointer;
  opacity: 0.8;
}
/* Media Queries */

/* Mobile styling */
@media only screen and(max-width:70px){
.ip-input{
  width:0;
}

}
</style>