<template>
  <div id="app">
    <weather></weather>
  </div>
</template>

<script>
import Weather from "./components/Weather.vue";

export default {
  name: "App",
  components: {
    weather: Weather,
  },
};
</script>

<style>
body {
  background: #3a7bd5; /* fallback for old browsers */
  background: -webkit-linear-gradient(
    to right,
    #3a6073,
    #3a7bd5
  ); /* Chrome 10-25, Safari 5.1-6 */
  background: linear-gradient(
    to right,
    #3a6073,
    #3a7bd5
  ); /* W3C, IE 10+/ Edge, Firefox 16+, Chrome 26+, Opera 12+, Safari 7+ */
}
</style>
