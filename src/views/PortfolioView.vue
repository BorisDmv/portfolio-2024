<template>
  <main class="cont">
    <div class="navbar-wrapper">
      <NavBar />
    </div>
    <div class="content">
      <h1 class="text-4xl font-extrabold dark:text-white">Portfolio</h1>
      <div class="line"></div>
      <div class="whatIDo">
        <a
          v-for="(item, index) in whatIDo"
          :key="index"
          :href="item.link"
          target="_blank"
          rel="noopener noreferrer"
          style="text-decoration: none; color: inherit;"
        >
          <article class="card card--2">
            <div class="card__info-hover">
              <div class="card__clock-info"></div>
            </div>
            <div class="card__img"></div>
            <div class="card_link">
              <div class="card__img--hover" :style="{ backgroundImage: `url(${item.image})` }"></div>
            </div>
            <div class="card__info">
              <span class="card__category"></span>
              <h3 class="card__title">{{ item.title }}</h3>
              <span class="card__by">{{ item.description }}</span>
              <div class="card__tech">
                <span v-for="tech in item.tech" :key="tech" class="card__tech-item">{{ tech }}</span>
              </div>
            </div>
          </article>
        </a>
      </div>
    </div>
  </main>
</template>

<script setup>
import NavBar from "@/components/NavBar.vue";
import scanlabImage from '@/assets/scanlab-preview.webp';
import umlCreatorImage from '@/assets/uml-creator.png';
import auraMindImage from '@/assets/aura-mind.png';

const whatIDo = [
  {
    title: "Scanlab",
    description: "Scanlab is SaaS project which scans and provides you if some of your sites are down. It also provides you with a dashboard where you can see the status of your sites, uptime, and response time. You can also set up alerts to notify you when a site goes down.",
    image: scanlabImage,
    link: "https://www.scanlab.site/",
    tech: ["Vue 2/3", "Flutter", "Custom Illustrations"]
  },
  {
    title: "UML Creator",
    description: "The most intuitive and powerful tool for visualizing your software architecture.Create diagrams for free—no credit card needed. Enjoy an intuitive, user-friendly interface with no learning curve.Go from idea to diagram in minutes.",
    image: umlCreatorImage,
    link: "https://uml-creator.vercel.app/",
    tech: ["React", "Tailwind CSS", "Go", "PostgresSQL"]
  },
  {
    title: "Aura Mind",
    description: "Aura Mind is your companion for relaxation, focus, and stress relief.Guided breathing exercises, mood tracking, and a points system help you stay motivated and balanced.Unwind and reduce stress with meditation sessions and track your emotional progress over time.",
    image: auraMindImage,
    tech: ["Flutter", "Firebase"]
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
  padding: 80px 24px 32px 24px;
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

.whatIDo {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(340px, 1fr));
  gap: 32px;
  margin-top: 32px;
  align-items: stretch;
}

.card__like {
  width: 18px;
}

.card__clock {
  width: 15px;
  vertical-align: middle;
  fill: #ad7d52;
}
.card__time {
  font-size: 12px;
  color: #ad7d52;
  vertical-align: middle;
  margin-left: 5px;
}

.card__clock-info {
  float: right;
}

.card__img {
  visibility: hidden;
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;
  width: 100%;
  height: 235px;
  border-top-left-radius: 12px;
  border-top-right-radius: 12px;
}

.card__info-hover {
  position: absolute;
  padding: 16px;
  width: 100%;
  opacity: 0;
  top: 0;
}

.card__img--hover {
  transition: 0.2s all ease-out;
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;
  width: 100%;
  position: absolute;
  height: 235px;
  border-top-left-radius: 12px;
  border-top-right-radius: 12px;
  top: 0;
}
.card {
  transition: all 0.4s cubic-bezier(0.175, 0.885, 0, 1);
  background-color: #181818;
  width: 100%;
  position: relative;
  border-radius: 12px;
  overflow: hidden;
  box-shadow: 0px 13px 10px -7px rgba(0, 0, 0, 0.1);
  margin-bottom: 35px;
  margin-right: auto;
  min-height: 420px;
  height: 100%;
  box-sizing: border-box;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  align-items: stretch;
}
.card:hover {
  box-shadow: 0px 30px 18px -8px rgba(0, 0, 0, 0.1);
  transform: scale(1.05, 1.05);
}

.card__info {
  z-index: 2;
  background-color: #181818;
  border-bottom-left-radius: 12px;
  border-bottom-right-radius: 12px;
  padding: 16px 24px 24px 24px;
}

.card__category {
  font-family: "Raleway", sans-serif;
  text-transform: uppercase;
  font-size: 13px;
  letter-spacing: 2px;
  font-weight: 500;
  color: #868686;
}

.card__title {
  margin-top: 5px;
  margin-bottom: 10px;
  font-family: "Roboto", serif;
}

.card__by {
  font-size: 14px;
  font-family: "Roboto", sans-serif;
  font-weight: 500;
  color: #fff;
}

.card__author {
  text-decoration: none;
}

.card:hover .card__img--hover {
  height: 100%;
  opacity: 0.3;
}

.card:hover .card__info {
  background-color: transparent;
  position: relative;
}

.card:hover .card__info-hover {
  opacity: 1;
}

.card__tech {
  margin-top: 8px;
  display: flex;
  flex-wrap: wrap;
  gap: 8px;
}

.card__tech-item {
  background-color: #2c2c2c;
  color: #fff;
  padding: 4px 8px;
  border-radius: 16px;
  font-size: 12px;
  white-space: nowrap;
}


@media (max-width: 1244px) {
  .whatIDo {
    flex-direction: column;
    gap: 16px;
  }
  .card {
    width: 100%;
    margin-bottom: 30px;
  }
}

@media (max-width: 600px) {
  .content {
    padding: 80px 4px 8px 4px;
  }
  .card {
    padding: 10px;
    font-size: 0.95rem;
  }
  .card h3 {
    font-size: 1.1rem;
  }
}

@media (max-width: 500px) {
  .whatIDo {
    grid-template-columns: 1fr;
    gap: 16px;
  }
  .card {
    min-width: 0;
    width: 100%;
    box-sizing: border-box;
    padding: 10px 4px;
    margin-bottom: 16px;
  }
}
</style>
