<template>
  <header>
    <h1>{{ title }}</h1>
  </header>
</template>
<script>
export default {
  props: ["title"],
};
</script>

<style scoped>
header {
  background-color: #2e635e;
  height: 5rem;
  display: flex;
  justify-content: center;
  align-items: center;
}

h1 {
  color: #fff;

  font-weight: 200;
}
</style>
