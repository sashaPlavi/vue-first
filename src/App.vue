<template>
  <div id="app">
    <h1>helloo</h1>
    <HelloWorld msg="cao bre" />
  </div>
</template>

<script>
import HelloWorld from "./components/HelloWorld.vue";
import axios from "axios";

export default {
  name: "app",
  components: {
    HelloWorld
  },

  created() {
    axios
      .get("https://jsonplaceholder.typicode.com/todos/?_limit=10")
      .then(res => console.log(res))
      .catch(err => console.log(err));
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
