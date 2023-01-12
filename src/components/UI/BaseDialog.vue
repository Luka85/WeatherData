<template>
  <teleport to="body">
    <div @click="closeError"></div>
    <dialog open>
      <header>
        <slot name="header"></slot>
      </header>
      <section>
        <slot></slot>
      </section>
    </dialog>
  </teleport>
</template>

<script>
export default {
  emits: ["close"],
  methods: {
    closeError() {
      this.$emit("close");
    },
  },
};
</script>

<style scoped>
dialog {
  position: absolute;
  top: 40%;
  left: 50%;
  transform: translate(-50%, -50%);
  display: flex;
  flex-direction: column;
  margin: 2rem auto;
  width: 40%;
  border-radius: 12px;
  border: none;
  padding: 0 0 1rem 0;
}

header {
  border-radius: 12px 12px 0 0;
  background-color: #2e635e;
  height: 3rem;
  display: flex;
  justify-content: center;
  align-items: center;
  margin-bottom: 1rem;
}
section {
  margin: 0 1rem;
}

div {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100vh;
  background-color: rgba(0, 0, 0, 0.75);
}
</style>
