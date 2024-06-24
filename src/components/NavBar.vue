<template>
  <nav class="navbar">
    <ul>
      <li :class="{ active: isActive('/') }"><router-link to="/">About</router-link></li>
      <li :class="{ active: isActive('/resume') }"><router-link to="/resume">Resume</router-link></li>
      <li :class="{ active: isActive('/portfolio') }"><router-link to="/portfolio">Portfolio</router-link></li>
      <li :class="{ active: isActive('/contact') }"><router-link to="/contact">Contact</router-link></li>
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
  padding: 15px;
}

.navbar ul {
  list-style-type: none;
  margin: 0;
  padding: 0;
  display: flex;
  gap: 20px;
}

.navbar ul li {
  display: inline;
}

.navbar ul li a {
  text-decoration: none;
  color: #cecece;
  font-weight: bold;
  padding: 5px 10px;
  border-radius: 5px;
  transition: background-color 0.3s, color 0.3s;
}

.navbar ul li a:hover {
  background-color: #3a3a3a;
  color: #fff;
}

.active {
  background-color: #3a3a3a;
  color: #fff;
}


@media (max-width: 860px) {
  .navbar{
    width: 100%;
    height: 50px;
    padding: 0;
    border-radius: 15px 15px 0 0;
  }

  .navbar ul{
    height: 100%;
    justify-content: end;
    align-items: center;
  }
}

@media (max-width: 420px) {
  .navbar ul{
    gap: 0;
  }
}
</style>