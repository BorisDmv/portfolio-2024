<script setup>
import { RouterView } from 'vue-router'
import SideScreen from './components/SideScreen.vue'
</script>

<template>
  <div id="app">
    <SideScreen />
    <div class="main-content">
      <RouterView />
    </div>
  </div>
</template>

<style scoped>
#app {
  display: flex;
  height: 100vh; /* Ensure the app takes up full viewport height */
}

.main-content {
  flex: 1; /* Takes up the remaining space */
  margin-left: 30%; /* Offset by the width of SideScreen */
  padding: 2rem;
}

/* Adjustments for smaller screens */
@media (max-width: 1024px) {
  #app {
    flex-direction: column;
  }

  .main-content {
    width: 100%;
    margin-left: 0; /* Reset margin for smaller screens */
  }
}
</style>