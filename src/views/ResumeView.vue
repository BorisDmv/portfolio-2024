<template>
  <main class="cont">
    <div class="navbar-wrapper">
      <NavBar/>
    </div>
    <div class="content">
      <h1 class="text-4xl font-extrabold dark:text-white">Resume</h1>
      <div class="line"></div>
      <div class="timeline-section">
        <h2 class="timeline-title">Experience Timeline</h2>
        <div class="timeline-grid">
          <div class="timeline-card" v-for="(item, index) in experience" :key="index">
            <div class="timeline-header">
              <span class="timeline-role">{{item.jobRole}}</span>
              <span class="timeline-date">{{item.date}}</span>
            </div>
            <div class="timeline-company">{{item.title}}</div>
            <ul class="timeline-tasks">
              <li v-for="(task, tIdx) in item.tasks" :key="tIdx">* {{task}}</li>
            </ul>
          </div>
        </div>
      </div>
      <div class="skills-section">
        <h2 class="skills-title">Skills & Strengths</h2>
        <div class="skills-list">
          <span class="skill">Web Development</span>
          <span class="skill">Mobile Development</span>
          <span class="skill">UI/UX Design</span>
          <span class="skill">Testing</span>
          <span class="skill">SEO & Optimization</span>
          <span class="skill">Mentoring</span>
          <span class="skill">Creative Problem Solving</span>
          <span class="skill">Team Collaboration</span>
        </div>
      </div>
    </div>
  </main>
</template>

<script setup>
import { onMounted } from 'vue';
import NavBar from "@/components/NavBar.vue";

function animateOnScroll() {
  const timelineSection = document.querySelector('.timeline-section');
  const timelineCards = document.querySelectorAll('.timeline-card');
  const skillsSection = document.querySelector('.skills-section');
  const skillItems = document.querySelectorAll('.skill');

  function handleScroll() {
    if (timelineSection) {
      const rect = timelineSection.getBoundingClientRect();
      if (rect.top < window.innerHeight - 100) {
        timelineSection.classList.add('animate');
        timelineCards.forEach((card, i) => {
          card.classList.add('animate');
          card.style.animationDelay = `${0.1 + i * 0.1}s`;
        });
      }
    }
    if (skillsSection) {
      const rect = skillsSection.getBoundingClientRect();
      if (rect.top < window.innerHeight - 100) {
        skillsSection.classList.add('animate');
        skillItems.forEach((item, i) => {
          item.classList.add('animate');
          item.style.animationDelay = `${0.1 + i * 0.1}s`;
        });
      }
    }
  }

  window.addEventListener('scroll', handleScroll);
  handleScroll();
}

onMounted(() => {
  animateOnScroll();
});

const experience = [
  {
    title: "HPH/C317",
    jobRole: "Software Developer",
    description: "Vue3 frontend developer\nFlutter Mobile App\nDoing landing pages\nMaintenance/Migration on vue project\nOptimisation and SEO improvements on websites\nMentoring new hires\nUnit/End to End testing",
    date: "June 2022 - Present",
    tasks: [
      "Vue3 frontend developer",
      "Flutter Mobile App",
      "Unit/End to End testing",
      "Doing landing pages",
      "Maintenance/Migration on vue project",
      "Optimisation and SEO improvements on websites",
      "Mentoring new hires"
    ]
  },
  {
    title: "WideOut",
    jobRole: "Creative Developer",
    description: "Implementation of advertisements for IBM Weather Channel, Culthealth, AARP and more",
    date: "Feb 2022 - May 2022",
    tasks: [
      "Implementation of advertisements for IBM Weather Channel, Culthealth, AARP and more",
      "Developed interactive ad components using HTML5 and JavaScript",
      "Collaborated with designers to deliver creative solutions",
      "Ensured cross-browser compatibility and performance",
      "Worked with remote teams to meet tight deadlines"
    ]
  },
  {
    title: "HelmErp",
    jobRole: "Frontend Developer",
    description: "Developing new features in NuxtJS\nMaintaining a furniture NuxtJS",
    date: "June 2021 - Nov 2021",
    tasks: [
      "Developing new features in NuxtJS",
      "Maintaining a furniture NuxtJS",
      "Implemented reusable UI components",
      "Optimized application performance and loading times",
      "Collaborated with backend developers for API integration"
    ]
  },
]
</script>

<style scoped>
.cont {
  width: 100%;
  min-height: 100vh;
  border-radius: 15px;
  background: #1f1f1f;
  box-sizing: border-box;
  display: flex;
  flex-direction: column;
  justify-content: flex-start;
}

.navbar-wrapper {
  width: 100%;
  display: flex;
  justify-content: flex-end;
  align-items: flex-start;
  padding-top: 0;
}

.content {
  padding: 110px 32px 32px 32px;
  flex: 1;
  display: flex;
  flex-direction: column;
  justify-content: flex-start;
}

.line {
  width: 50px;
  height: 5px;
  border-radius: 10px;
  background: var(--accent-main);
  margin: 5px 0 20px 0;
}

.timeline-section {
  margin: 32px 0 0 0;
  width: 100%;
  max-width: unset;
  background: #232323;
  border-radius: 12px;
  box-shadow: 0 2px 12px rgba(0,0,0,0.10);
  padding: 32px 24px;
  animation: fadeInUp 0.8s cubic-bezier(0.23, 1, 0.32, 1);
  opacity: 0;
  transform: translateY(40px);
  transition: opacity 0.8s cubic-bezier(0.23, 1, 0.32, 1), transform 0.8s cubic-bezier(0.23, 1, 0.32, 1);
}
.timeline-section.animate {
  opacity: 1;
  transform: translateY(0);
}
@keyframes fadeInUp {
  0% {
    opacity: 0;
    transform: translateY(40px);
  }
  100% {
    opacity: 1;
    transform: translateY(0);
  }
}
.timeline-title {
  color: var(--accent-main);
  font-size: 1.5rem;
  font-weight: 700;
  margin-bottom: 24px;
  text-align: center;
}
.timeline-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
  gap: 28px;
}
.timeline-card {
  background: #292929;
  border-radius: 10px;
  box-shadow: 0 1px 8px rgba(0,0,0,0.10);
  padding: 24px 18px;
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  transition: box-shadow 0.2s, transform 0.2s;
  opacity: 0;
  transform: translateY(20px);
  transition: opacity 0.7s cubic-bezier(0.23, 1, 0.32, 1), transform 0.7s cubic-bezier(0.23, 1, 0.32, 1);
}
.timeline-card.animate {
  opacity: 1;
  transform: translateY(0);
}
.timeline-card:nth-child(1) { animation-delay: 0.1s; }
.timeline-card:nth-child(2) { animation-delay: 0.2s; }
.timeline-card:nth-child(3) { animation-delay: 0.3s; }
@keyframes fadeInList {
  0% {
    opacity: 0;
    transform: translateY(20px);
  }
  100% {
    opacity: 1;
    transform: translateY(0);
  }
}
.timeline-header {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
  align-items: center;
  width: 100%;
  margin-bottom: 8px;
  gap: 8px;
}
.timeline-role {
  color: var(--accent-main);
  font-size: 1.1rem;
  font-weight: 600;
}
.timeline-date {
  white-space: nowrap;
  min-width: 120px;
  text-align: right;
  background: #313742;
  color: #bdbdbd;
  border-radius: 6px;
  padding: 4px 12px;
  font-size: 0.95rem;
  font-weight: 500;
}
.timeline-company {
  color: #e0e0e0;
  font-size: 1.15rem;
  font-weight: 500;
  margin-bottom: 10px;
}
.timeline-tasks {
  margin-left: 0;
  padding-left: 18px;
  color: #bdbdbd;
  font-size: 1rem;
}
.timeline-tasks li {
  margin-bottom: 6px;
}

.skills-section {
  margin: 32px 0 0 0;
  width: 100%;
  max-width: unset;
  background: #232323;
  border-radius: 12px;
  box-shadow: 0 2px 12px rgba(0,0,0,0.10);
  padding: 32px 24px;
  text-align: center;
  animation: fadeInUp 0.8s cubic-bezier(0.23, 1, 0.32, 1);
  opacity: 0;
  transform: translateY(40px);
  transition: opacity 0.8s cubic-bezier(0.23, 1, 0.32, 1), transform 0.8s cubic-bezier(0.23, 1, 0.32, 1);
}
.skills-section.animate {
  opacity: 1;
  transform: translateY(0);
}
.skills-title {
  color: var(--accent-main);
  font-size: 1.5rem;
  font-weight: 700;
  margin-bottom: 18px;
}
.skills-list {
  display: flex;
  flex-wrap: wrap;
  gap: 16px;
  justify-content: center;
}
.skill {
  background: #292929;
  color: #fff;
  border-radius: 8px;
  padding: 10px 22px;
  font-size: 1rem;
  font-weight: 500;
  box-shadow: 0 1px 6px rgba(0,0,0,0.08);
  transition: background 0.2s, color 0.2s, transform 0.3s, opacity 0.7s, transform 0.7s;
  opacity: 0;
  transform: translateY(20px);
}
.skill.animate {
  opacity: 1;
  transform: translateY(0);
}
.skill:hover {
  background: var(--accent-main);
  color: #232323;
  transform: scale(1.07);
}

@media (max-width: 1024px) {
  .cont {
    min-height: auto;
  }
  .content {
    padding: 90px 16px 16px 16px;
  }
}

@media (max-width: 600px) {
  .content {
  }
}

@media (max-width: 500px) {
  .timeline-grid {
    grid-template-columns: 1fr;
    gap: 16px;
  }
  .timeline-card {
    min-width: 0;
    width: 100%;
    box-sizing: border-box;
    padding: 16px 8px;
  }
}
</style>
