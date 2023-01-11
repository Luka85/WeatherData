<template>
  <li>
    <base-card>
      <template #default>
        <header>
          <h3>{{ city }}, {{ country }}</h3>
          <h4>{{ temperature }}°C</h4>
          <base-button mode="view">View details</base-button>
          <!-- <p>Humidity: {{ humidity }}</p>
          <p>{{ description }}</p> -->
        </header>
        <div>
          <base-button mode="delete">Delete</base-button>
        </div>
      </template>
    </base-card>
  </li>
</template>

<script>
export default {
  props: ["city", "country", "temperature", "humidity", "description", "id"],
};
</script>

<style scoped>
h3,
h4 {
  margin-bottom: 0.5rem;
  font-weight: 400;
}
h3 {
  font-size: 1.1rem;
}
h4 {
  font-size: 1.8rem;
}
</style>
