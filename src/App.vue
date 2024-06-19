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
}

.side-content{
  padding: 2rem;
}

.main-content {
  flex: 1; /* Takes up the remaining space */
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