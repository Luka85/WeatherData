<template>
  <li>
    <base-card>
      <template #default>
        <header>
          <h3>{{ city }}, {{ country }}</h3>
          <h4>{{ temperature }}°C</h4>
          <button>View details</button>
          <p>Humidity: {{ humidity }}</p>
          <p>{{ description }}</p>
        </header>
        <div>
          <button>Delete</button>
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
