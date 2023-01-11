<template>
  <the-header title="Weather Data"></the-header>
  <weather-tab></weather-tab>
</template>
<script>
import TheHeader from "./components/layout/TheHeader.vue";
import WeatherTab from "./components/weather-data/WeatherTab.vue";
export default {
  components: {
    TheHeader,
    WeatherTab,
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
