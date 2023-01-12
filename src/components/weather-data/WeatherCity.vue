<template>
  <li>
    <base-card>
      <template #default>
        <header>
          <h3>{{ city }}, {{ country }}</h3>
          <h4>{{ temperature }}°C</h4>
          <base-button mode="view" @click="viewDetails"
            >View details</base-button
          >
          <div v-if="isVisible">
            <p>Humidity: {{ humidity }}</p>
            <p>{{ description }}</p>
          </div>
        </header>
        <div>
          <base-button mode="delete" @click="deleteStation(id)"
            >Delete</base-button
          >
        </div>
      </template>
    </base-card>
  </li>
</template>

<script>
export default {
  props: ["city", "country", "temperature", "humidity", "description", "id"],
  inject: ["deleteStation"],
  data() {
    return {
      isVisible: false,
    };
  },

  methods: {
    viewDetails() {
      this.isVisible = !this.isVisible;
    },
  },
};
</script>

<style scoped>
h3,
h4 {
  margin-bottom: 0.5rem;
  font-weight: 400;
  color: #2e635e;
}
h3 {
  font-size: 1.1rem;
}
h4 {
  font-size: 1.8rem;
}

p {
  color: #2e635e;
}
div {
  margin-top: 1rem;
}
</style>
