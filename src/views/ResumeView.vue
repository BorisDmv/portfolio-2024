<template>
  <main class="cont">
    <NavBar/>
    <div class="content">
      <h1 class="text-4xl font-extrabold dark:text-white">Resume</h1>
      <div class="line"></div>

<!--      <main class="relative min-h-screen flex flex-col justify-center bg-slate-50 overflow-hidden">-->
<!--        <div class="w-full max-w-6xl mx-auto px-4 md:px-6 py-24">-->
<!--          <div class="flex flex-col justify-center divide-y divide-slate-200 [&>*]:py-16">-->

            <div class="w-full max-w-3xl mx-auto">

              <!-- Vertical Timeline #1 -->
              <div class="-my-6">

                <!-- Item #1 -->
                <div class="relative pl-8 sm:pl-32 py-6 group" v-for="(item, index) in experience" :key="index">
                  <!-- Purple label -->
                  <div class="font-caveat font-medium text-2xl text-[#c8a884] mb-1 sm:mb-0">{{item.jobRole}}</div>
                  <!-- Vertical line (::before) ~ Date ~ Title ~ Circle marker (::after) -->
                  <div class="flex flex-col sm:flex-row items-start mb-1 group-last:before:hidden before:absolute before:left-2 sm:before:left-0 before:h-full before:px-px before:bg-slate-300 sm:before:ml-[6.5rem] before:self-start before:-translate-x-1/2 before:translate-y-3 after:absolute after:left-2 sm:after:left-0 after:w-2 after:h-2 after:bg-indigo-600 after:border-4 after:box-content after:border-slate-50 after:rounded-full sm:after:ml-[6.5rem] after:-translate-x-1/2 after:translate-y-1.5">
                    <time class="sm:absolute left-0 translate-y-0.5 inline-flex items-center justify-center text-xs font-semibold uppercase w-20 h-6 mb-3 sm:mb-0 text-grey-300 bg-[#292929] rounded-full">{{item.date}}</time>
                    <div class="text-xl font-bold text-slate-400">{{item.title}}</div>
                  </div>
                  <!-- Content -->
                  <div class="text-slate-500">{{item.description}}</div>
                </div>


              </div>
              <!-- End: Vertical Timeline #1 -->
            </div>

    </div>
  </main>
</template>

<script setup>
import NavBar from "@/components/NavBar.vue";

const experience = [
  {
    title: "HPH/C317",
    jobRole: "Software Developer",
    description: "I work as a software developer at HPH/C317. I am responsible for developing and maintaining the company's internal SaaS.",
    date: "June 2022",
  },
  {
    title: "Wideout",
    jobRole: "Creative Developer",
    description: "I worked at WideOut with the responsibility to prepare html/css/js design templates with ads for IMB Weather Channel and other clients.",
    date: "Feb 2022",
  },
  {
    title: "HelmErp",
    jobRole: "Frontend Developer",
    description: "Developing new features and maintaining furniture webapp with Nuxt.js",
    date: "June 2021",
  },
]

</script>

<style scoped>
.cont {
  width: 100%; /* Ensure the container takes the full remaining width */
  border-radius: 15px;
  background: #1f1f1f; /* Adjust background color as needed */
  box-sizing: border-box; /* Ensure padding is included in the width */
}

p {
  font-size: 1rem;
}

.content {
  padding: 90px 20px 20px 20px;
}

.line {
  width: 50px;
  height: 5px;
  border-radius: 10px;
  background: #fefefe;
  margin: 5px 0 20px 0;
}




</style>
