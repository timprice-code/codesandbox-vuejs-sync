<template>
  <div id="app">
    <img width="25%" src="./assets/logo.png">
    <HelloWorld msg="PFTDL"/>
    <ListStreams msg="Stream Listing"/>
  </div>
</template>

<script>
import HelloWorld from "./components/HelloWorld";
import ListStreams from "./components/ListStreams";

export default {
  name: "App",
  components: {
    HelloWorld,
    ListStreams
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
