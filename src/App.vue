<template>
  <the-header title="Weather Data"></the-header>
  <weather-cities></weather-cities>
</template>
<script>
import TheHeader from "./components/layout/TheHeader.vue";
import WeatherCities from "./components/weather-data/WeatherCities.vue";
export default {
  components: {
    TheHeader,
    WeatherCities,
  },
  data() {
    return {};
  },
};
</script>

<style>
@import url("https://fonts.googleapis.com/css2?family=Roboto:wght@300;400;500;700;900&display=swap");

* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}
html {
  font-family: "Roboto", sans-serif;
}

body {
  margin: 0;
}
</style>
