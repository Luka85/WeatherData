<template>
  <ul>
    <weather-city
      v-for="(station, index) in stations"
      :key="index"
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
  data() {
    return {
      stations: [
        {
          city: "Kranj",
          country: "Slovenia",
          temperature: 15,
          humidity: 53,
          description: "Sunny",
        },
        {
          city: "Ljubljana",
          country: "Slovenia",
          temperature: 16,
          humidity: 55,
          description: "Cloudy",
        },
        {
          city: "Koper",
          country: "Slovenia",
          temperature: 22,
          humidity: 30,
          description: "Sunny",
        },
      ],
    };
  },
};
</script>
