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
  <keep-alive>
    <component :is="selectedComponent"></component>
  </keep-alive>
</template>

<script>
import AddData from "./AddData.vue";
import WeatherCities from "./WeatherCities.vue";
export default {
  components: {
    AddData,
    WeatherCities,
  },
  provide() {
    return {
      stations: this.stations,
      addStation: this.addStation,
      deleteStation: this.deleteStation,
      id: this.id,
    };
  },
  data() {
    return {
      selectedComponent: "weather-cities",
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
  methods: {
    setSelectedComponents(component) {
      this.selectedComponent = component;
    },
    addStation(city, country, temperature, humidity, description) {
      const newStation = {
        city: city,
        country: country,
        temperature: temperature,
        humidity: humidity,
        description: description,
      };
      this.stations.unshift(newStation);
      this.selectedComponent = "weather-cities";
    },
    deleteStation(id) {
      this.stations.splice(id, 1);
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
