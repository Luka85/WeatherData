<template>
  <ul>
    <weather-city
      v-for="(station, index) in stations"
      :key="index"
      :id="index"
      :city="station.city"
      :country="station.country"
      :temperature="station.temperature"
      :humidity="station.humidity"
      :description="station.description"
    ></weather-city>
  </ul>
</template>

<script>
import WeatherCity from "./WeatherCity.vue";
export default {
  components: {
    WeatherCity,
  },
  inject: ["stations"],
};
</script>
