<template>
  <div class="container">
    sidebar
  </div>
</template>

<script>
export default {
  name: "SideScreen"
}
</script>

<style scoped>
.container {
  background: #1f1f1f;
  width: 30%;
  height: 100vh; /* Full height */
  position: fixed; /* Fixed position */
  top: 0;
  left: 0;
}

@media (max-width: 1024px) {
  .container {
    width: 100%;
    height: auto;
    position: relative;
  }
}
</style>