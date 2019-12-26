<template>
  <div id="app">
    <Header />

    <HelloWorld msg="cao bre" />
    <Todos v-bind:todos="todos" />
  </div>
</template>

<script>
import HelloWorld from "./components/HelloWorld.vue";
import Todos from "./components/Todos.vue";
import Header from "./components/layout/Header.vue";
import axios from "axios";

export default {
  name: "app",
  components: {
    HelloWorld,
    Todos,
    Header
  },
  data() {
    return {
      todos: []
    };
  },

  created() {
    axios
      .get("https://jsonplaceholder.typicode.com/todos/?_limit=10")
      .then(res => (this.todos = res.data))
      .catch(err => console.log(err));
  }
};
</script>

<style>
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}
body {
  font-family: Arial, Helvetica, sans-serif;
  line-height: 1.4;
}
</style>
