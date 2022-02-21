<template>
  <div id="app">
    <Herois />
  </div>
</template>

<script>
import Herois from "./components/Herois.vue";

export default {
  name: "App",
  components: {
    Herois,
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
