<template>
  <button :class="mode">
    <slot></slot>
  </button>
</template>
<script>
export default {
  props: ["mode"],
};
</script>
<style scoped>
.delete {
  padding: 0.5rem 1rem;
  background-color: #fff;
  color: #2e635e;
  border: 1px solid #2e635e;

  border-radius: 0.3rem;
  cursor: pointer;
}

.delete:hover,
.delete:active {
  background-color: #2e635e;
  color: #fff;
  border: 1px solid transparent;
}

.view {
  background-color: #2e635e;
  color: #fff;
  padding: 0.5rem 1rem;
  border: 1px solid #2e635e;
  border-radius: 0.3rem;
  cursor: pointer;
}

.view:hover,
.view:active {
  background-color: #fff;
  color: #2e635e;
  border: 1px solid #2e635e;
}

.active {
  width: 100%;
  background-color: #2e635e;
  color: #fff;
  padding: 0.5rem 1rem;
  border: 1px solid transparent;
  cursor: pointer;
}

.flat {
  width: 100%;
  padding: 0.5rem 1rem;
  background-color: #fff;
  color: #2e635e;
  border: 1px solid #2e635e;

  cursor: pointer;
}

@media (max-width: 360px) {
  button {
    font-size: 0.6rem;
  }
  .active {
    padding: 0.5rem 0.3rem;
  }
  .flat {
    padding: 0.5rem 0.3rem;
  }
}
</style>
