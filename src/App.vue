<template>
  <div id="app">
    <img width="25%" src="./assets/logo.png">
    <Blogspot/>

  </div>
</template>

<script>
import Blogspot from "./components/blog";

export default {
  name: "App",
  components: {
    Blogspot
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
