<template>
  <nav class="navbar">
    <ul>
      <li :class="{ active: isActive('/') }"><router-link to="/">About</router-link></li>
      <li :class="{ active: isActive('/resume') }"><router-link to="/resume">Resume</router-link></li>
      <li :class="{ active: isActive('/portfolio') }"><router-link to="/portfolio">Portfolio</router-link></li>
    </ul>
  </nav>
</template>

<script setup>
import { useRoute } from 'vue-router';
import { computed } from 'vue';

// Use the useRoute hook to access the current route
const route = useRoute();

// Define the isActive function
const isActive = (targetRoute) => {
  return computed(() => route.path === targetRoute).value;
};
</script>


<style scoped>
.navbar {
  background: #292929;
  float: right;
  border-radius: 0 15px 0 15px;
  padding: 15px 30px;
  box-shadow: 0 2px 12px rgba(0,0,0,0.08);
}

.navbar ul {
  list-style-type: none;
  margin: 0;
  padding: 0;
  display: flex;
  gap: 24px;
}

.navbar li {
  position: relative;
  transition: transform 0.2s;
}

.navbar li.active > a,
.navbar li.active > .router-link-active {
  color: #fff;
  font-weight: bold;
  border-bottom: 2px solid var(--accent-main);
}

.navbar li a,
.navbar li .router-link-active {
  color: #bdbdbd;
  text-decoration: none;
  font-size: 1.1rem;
  padding: 6px 0;
  transition: color 0.2s;
}

.navbar li:hover {
  transform: translateY(-2px) scale(1.05);
}

.navbar li a:hover,
.navbar li .router-link-active:hover {
  color: var(--accent-main);
}


@media (max-width: 860px) {
  .navbar{
    width: 100%;
    height: 50px;
    padding: 0;
    border-radius: 15px 15px 0 0;
    display: flex;
    justify-content: center;
    align-items: center;
  }
  .navbar ul{
    height: 100%;
    justify-content: center;
    align-items: center;
    width: 100%;
    gap: 18px;
  }
}

@media (max-width: 420px) {
  .navbar {
    padding: 10px 8px;
  }
  .navbar ul {
    gap: 8px;
    padding: 0;
  }
  .navbar li {
    margin: 0 2px;
    font-size: 0.95rem;
  }
}
</style>