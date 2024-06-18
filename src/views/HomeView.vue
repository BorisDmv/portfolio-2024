<template>
  <main class="container">
    <nav class="navbar">
      <ul>
        <li :class="{ active: isActive('/') }"><router-link to="/">About</router-link></li>
        <li :class="{ active: isActive('/blog') }"><router-link to="/blog">Blog</router-link></li>
        <li :class="{ active: isActive('/contact') }"><router-link to="/contact">Contact</router-link></li>
        <li :class="{ active: isActive('/portfolio') }"><router-link to="/portfolio">Portfolio</router-link></li>
      </ul>
    </nav>
    <div class="content">
      <h1 class="title">About Me</h1>
      <div class="line"></div>
      <p>
        I'm a full-time software developer who loves coding and thrives in the dynamic world of technology. My primary tools are JavaScript, and for the frontend, I have a particular fondness for the Vue.js framework. When it comes to mobile development, Flutter is my go-to framework for creating seamless and efficient applications.
      </p>
      <p style="margin-top: 10px">
        Beyond the screen, I cherish the simple joys of life, like taking walks outside and immersing myself in nature's beauty. Originally from Sofia, Bulgaria, I've always been inspired by the blend of rich culture and scenic landscapes of my hometown.
      </p>
    </div>
  </main>
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
.container {
  width: 100%; /* Ensure the container takes the full remaining width */
  border-radius: 15px;
  background: #1f1f1f; /* Adjust background color as needed */
  box-sizing: border-box; /* Ensure padding is included in the width */
}

p{
  font-size: 1rem;
}

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

.content{
  padding: 40px;
}

.title{
  color: white;
}

.line{
  width: 5%;
  height: 5px;
  border-radius: 10px;
  background: #fefefe;
  margin: 5px 0 20px 0;
}
</style>
<script setup>
</script>