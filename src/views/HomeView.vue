<template>
  <main class="container">
    <NavBar />
    <div class="content">
      <h1 class="text-4xl font-extrabold dark:text-white">About Me</h1>
      <div class="line"></div>
      <p>
        I'm a full-time software developer who loves coding and thrives in the dynamic world of technology. My primary tools are JavaScript, and for the frontend, I have a particular fondness for the Vue.js framework. When it comes to mobile development, Flutter is my go-to framework for creating seamless and efficient applications.
      </p>
      <p style="margin-top: 10px">
        Beyond the screen, I cherish the simple joys of life, like taking walks outside and immersing myself in nature's beauty. Originally from Sofia, Bulgaria, I've always been inspired by the blend of rich culture and scenic landscapes of my hometown.
      </p>

      <div class="whatIDo">
        <div class="card" v-for="(item, index) in whatIDo" :key="index">
          <h2>{{item.title}}</h2>
          <p>
            {{item.description}}
          </p>
        </div>
      </div>

    </div>
  </main>
</template>

<script setup>
import NavBar from "@/components/NavBar.vue";

const whatIDo = [
  {
    title: "Web Development",
    description: "I specialize in creating responsive and user-friendly web applications that cater to the needs of modern businesses. My goal is to provide clients with a seamless digital experience that enhances their online presence and drives growth."
  },
  {
    title: "Mobile Development",
    description: "I have a particular fondness for the Flutter framework when it comes to mobile development. I create seamless and efficient applications that provide users with a smooth and engaging experience."
  },
  {
    title: "UI/UX Design",
    description: "I have a keen eye for design and strive to create visually appealing interfaces that are intuitive and easy to use. I believe that good design is essential for creating a positive user experience."
  }
]

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

.content{
  padding: 90px 20px 20px 20px;
}

.whatIDo {
  display: flex;
  flex-wrap: wrap; /* Allow cards to wrap to the next line */
  gap: 20px; /* Adjust gap between cards */
}

.card {
  flex: calc(50% - 10px); /* Two cards per row, minus gap */
  padding: 20px;
  margin-top: 20px;
  background: linear-gradient(#212121, #282828) padding-box, linear-gradient(to right, #373737, #232323) border-box;
  border-radius: 10px;
  border: 2px solid transparent;
  transition: border-color 0.3s, border-width 0.3s;
}


.line{
  width: 50px;
  height: 5px;
  border-radius: 10px;
  background: #fefefe;
  margin: 5px 0 20px 0;
}

@media (max-width: 1444px) {
  .whatIDo {
    flex-direction: column;
  }
}

</style>
