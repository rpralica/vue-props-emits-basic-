<template>
  <div>
    <slot></slot>
  </div>
</template>

<script>
export default {
  data() {
    return {};
  },
};
</script>

<style scoped>
div {
  background: deepskyblue;
  color: white;
  height: 5rem;
  padding: 1em;
}
h1 {
  color: yellow;
}
</style>
