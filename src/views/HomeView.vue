<template>
  <main class="cont">
    <div class="navbar-wrapper">
      <NavBar />
    </div>
    <div class="content">
      <h1 class="text-4xl font-extrabold dark:text-white">About Me</h1>
      <div class="line"></div>
      <p>
        I'm a full-time software developer who loves coding and thrives in the dynamic world of technology. I enjoy building user experiences and solving problems through creative solutions. My passion for learning keeps me motivated to explore new ideas and approaches in software development.
      </p>
      <p style="margin-top: 10px">
        Beyond the screen, I cherish the simple joys of life, like taking walks outside and immersing myself in nature's beauty. I believe that a balanced life fuels my creativity and enhances my work. Whether it's through coding or enjoying the outdoors, I find inspiration in every moment.
      </p>
      <div class="about-section">
        <h2 class="about-title">What I'm Great At</h2>
        <ul class="about-list">
          <li>Creating engaging and intuitive user experiences</li>
          <li>Solving complex problems with creative solutions</li>
          <li>Collaborating with teams and mentoring others</li>
          <li>Adapting quickly to new technologies and challenges</li>
          <li>Balancing work and life for sustained creativity</li>
        </ul>
        <div class="download-cv-wrapper">
          <a href="/Boris_CV.pdf" download class="download-cv-btn">
            <svg class="cv-icon" xmlns="http://www.w3.org/2000/svg" width="22" height="22" fill="none" viewBox="0 0 24 24"><path :fill="'var(--accent-main)'" d="M12 16a1 1 0 0 1-1-1V8a1 1 0 1 1 2 0v7a1 1 0 0 1-1 1Zm0 4a1 1 0 0 1-.7-1.7l.7-.7.7.7A1 1 0 0 1 12 20ZM6 2h12a2 2 0 0 1 2 2v16a2 2 0 0 1-2 2H6a2 2 0 0 1-2-2V4a2 2 0 0 1 2-2Zm0 2v16h12V4H6Z"/></svg>
            <span>Download My CV</span>
          </a>
        </div>
      </div>
    </div>
  </main>
</template>

<script setup>
import { onMounted } from 'vue';
import NavBar from "@/components/NavBar.vue";

function animateOnScroll() {
  const aboutSection = document.querySelector('.about-section');
  const aboutListItems = document.querySelectorAll('.about-list li');
  const cvBtn = document.querySelector('.download-cv-btn');

  function handleScroll() {
    const rect = aboutSection.getBoundingClientRect();
    if (rect.top < window.innerHeight - 100) {
      aboutSection.classList.add('animate');
      aboutListItems.forEach((li, i) => {
        li.classList.add('animate');
        li.style.animationDelay = `${0.1 + i * 0.1}s`;
      });
      if (cvBtn) cvBtn.classList.add('animate');
      window.removeEventListener('scroll', handleScroll);
    }
  }

  window.addEventListener('scroll', handleScroll);
  handleScroll();
}

onMounted(() => {
  animateOnScroll();
});
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

p{
  font-size: 1rem;
}

.content {
  padding: 110px 32px 32px 32px;
  flex: 1;
  display: flex;
  flex-direction: column;
  justify-content: flex-start;
}

.about-section {
  margin: 32px 0 0 0;
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
.about-section.animate {
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

.about-title {
  color: var(--accent-main);
  font-size: 1.3rem;
  font-weight: 700;
  margin-bottom: 18px;
}

.about-list {
  list-style: none;
  padding: 0;
  margin: 0 auto;
  max-width: 500px;
  text-align: left;
}

.about-list li {
  background: #292929;
  color: #fff;
  border-radius: 8px;
  padding: 12px 18px;
  font-size: 1rem;
  font-weight: 500;
  margin-bottom: 12px;
  box-shadow: 0 1px 6px rgba(0,0,0,0.08);
  transition: background 0.2s;
  opacity: 0;
  transform: translateY(20px);
  transition: opacity 0.7s cubic-bezier(0.23, 1, 0.32, 1), transform 0.7s cubic-bezier(0.23, 1, 0.32, 1);
}
.about-list li.animate {
  opacity: 1;
  transform: translateY(0);
}

.about-list li:hover {
  background: var(--accent-main);
  color: #232323;
  transform: scale(1.07);
}

.about-list li:nth-child(1) { animation-delay: 0.1s; }
.about-list li:nth-child(2) { animation-delay: 0.2s; }
.about-list li:nth-child(3) { animation-delay: 0.3s; }
.about-list li:nth-child(4) { animation-delay: 0.4s; }
.about-list li:nth-child(5) { animation-delay: 0.5s; }

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

.line {
  width: 50px;
  height: 5px;
  border-radius: 10px;
  background: var(--accent-main);
  margin: 5px 0 20px 0;
}

.download-cv-wrapper {
  display: flex;
  justify-content: center;
  margin-top: 28px;
}

.download-cv-btn {
  display: inline-flex;
  align-items: center;
  gap: 10px;
  background: #313742;
  color: var(--accent-main);
  font-weight: 700;
  padding: 14px 32px;
  border-radius: 10px;
  text-decoration: none;
  box-shadow: 0 2px 12px rgba(0,0,0,0.15);
  transition: background 0.2s, box-shadow 0.2s, color 0.2s, transform 0.3s, opacity 0.7s, transform 0.7s;
  opacity: 0;
  transform: translateY(20px);
}
.download-cv-btn.animate {
  opacity: 1;
  transform: translateY(0);
}

.download-cv-btn:hover {
  background: var(--accent-main);
  color: #232323;
  box-shadow: 0 4px 16px rgba(0,0,0,0.25);
  transform: scale(1.07);
}

.cv-icon {
  vertical-align: middle;
  fill: var(--accent-main);
}

@media (max-width: 1024px) {
  .cont {
    min-height: auto;
  }
  .content {
    padding: 90px 24px 16px 24px;
  }
}

@media (max-width: 600px) {
  .content {
    padding: 80px 12px 8px 12px;
  }
}
</style>
