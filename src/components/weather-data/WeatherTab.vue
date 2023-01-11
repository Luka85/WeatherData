<template>
  <base-card>
    <base-button
      :mode="setWeatherCitiesModeButton"
      @click="setSelectedComponents('weather-cities')"
      >All Places</base-button
    >
    <base-button
      :mode="setAddDataModeButton"
      @click="setSelectedComponents('add-data')"
      >Add Weather Data</base-button
    >
  </base-card>
  <component :is="selectedComponent"></component>
</template>

<script>
import AddData from "./AddData.vue";
import WeatherCities from "./WeatherCities.vue";
export default {
  components: {
    AddData,
    WeatherCities,
  },
  data() {
    return {
      selectedComponent: "weather-cities",
    };
  },
  methods: {
    setSelectedComponents(component) {
      this.selectedComponent = component;
    },
  },
  computed: {
    setWeatherCitiesModeButton() {
      return this.selectedComponent === "weather-cities" ? "active " : "flat";
    },
    setAddDataModeButton() {
      return this.selectedComponent === "add-data" ? "active " : "flat";
    },
  },
};
</script>
