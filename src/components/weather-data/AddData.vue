import BaseButton from "../UI/BaseButton.vue";

<template>
  <base-card>
    <form @submit.prevent="submitForm()">
      <div class="form-control">
        <label for="city">City</label>
        <input
          type="text"
          name="city"
          id="city"
          placeholder="Type your city..."
          v-model.trim="city"
        />
      </div>
      <div class="form-control">
        <label for="country">Country</label>
        <input
          type="text"
          name="country"
          id="country"
          placeholder="Type your country..."
          v-model.trim="country"
        />
      </div>
      <div class="form-control">
        <label for="temperature">Temperature</label>
        <input
          type="number"
          name="temperature"
          id="temperature"
          placeholder="Type the temperature..."
          v-model.trim="temperature"
        />
      </div>
      <div class="form-control">
        <label for="humidity">Humidity</label>
        <input
          type="number"
          name="humidity"
          id="humidity"
          placeholder="Type the humidity..."
          v-model.trim="humidity"
        />
      </div>
      <div class="form-control">
        <label for="description">Description</label>
        <input
          type="text"
          name="description"
          id="description"
          placeholder="Type a short weather description (e.g. sunny, mostly cloudy, etc)..."
          v-model.trim="description"
        />
      </div>

      <base-button mode="view" type="submit">Submit Data</base-button>
    </form>
  </base-card>

  <base-dialog v-if="isInvalid" @close="confirmError">
    <template #header>
      <h3>Invalid Input</h3>
    </template>
    <template #default class="description">
      <p>You entered invalid data!</p>
      <p>For each input you must enter some data.</p>
      <base-button mode="view" @click="confirmError">Okay</base-button>
    </template>
  </base-dialog>
</template>

<script>
export default {
  inject: ["stations", "addStation"],
  data() {
    return {
      city: "",
      country: "",
      temperature: null,
      humidity: null,
      description: "",
      isInvalid: false,
    };
  },
  methods: {
    submitForm() {
      if (
        this.city === "" ||
        this.country === "" ||
        this.temperature === null ||
        this.humidity === null ||
        this.description === ""
      ) {
        this.isInvalid = true;
      } else {
        console.log(this.stations);
        this.addStation(
          this.city,
          this.country,
          this.temperature,
          this.humidity,
          this.description
        );
      }
    },
    confirmError() {
      this.isInvalid = false;
    },
  },
};
</script>

<style scoped>
form {
  width: 100%;
}
.form-control {
  display: flex;
  flex-direction: column;
  margin-bottom: 0.7rem;
}
input {
  padding: 0.2rem;
}

label {
  margin-bottom: 0.1rem;
  font-size: 0.9rem;
}
h3 {
  color: #fff;
  font-weight: 200;
}

p {
  margin-bottom: 0.5rem;
}

.description {
  margin: 0 1rem;
}
</style>
