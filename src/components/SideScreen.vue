<template>
  <div class="cont">
    <div class="item-row">
      <img class="user-profile" src="../assets/40300461.png" />
      <div class="name-content">
        <h2>Boris Dimitrov</h2>
      </div>
      <div class="box">
        <p class="text-role">Software Engineer</p>
      </div>
      <div class="contact-info">
        <a class="contact-item" href="mailto:borisdimitrov1998@gmail.com">
          <div class="icon-box">
            <img class="icon" src="../assets/email.png" />
          </div>
          <span class="contact-text">Send Mail</span>
        </a>
        <a class="contact-item" href="https://github.com/BorisDmv" target="_blank">
          <div class="icon-box">
            <img class="icon" src="../assets/github.png" />
          </div>
          <span class="contact-text">My GitHub</span>
        </a>
<!--        <div class="contact-item">-->
<!--          <div class="icon-box">-->
<!--            <svg width="24" height="24" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">-->
<!--              <path d="M6.62 10.79a15.053 15.053 0 006.59 6.59l2.2-2.2a1 1 0 011.01-.24c1.12.37 2.33.57 3.58.57a1 1 0 011 1v3.5a1 1 0 01-1 1C7.61 22 2 16.39 2 9.5a1 1 0 011-1H6.5a1 1 0 011 1c0 1.25.2 2.46.57 3.58a1 1 0 01-.24 1.01l-2.21 2.2z" fill="#4caf50"/>-->
<!--            </svg>-->
<!--          </div>-->
<!--          <a href="tel:+359876079546">+359 876 079 546</a>-->
<!--        </div>-->
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "SideScreen"
}
</script>

<style scoped>
.cont {
  background: #1f1f1f;
  border-radius: 20px;
  box-shadow: 0 4px 24px rgba(0,0,0,0.12);
  padding: 32px 24px;
  max-width: 320px;
  min-height: 94vh;
  margin: 0 0 0 32px;
  position: sticky;
  top: 30px;
  left: 0;
  z-index: 100;
  align-self: flex-start;
  display: flex;
  flex-direction: column;
  justify-content: center;
}

.item-row {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.user-profile {
  width: 96px;
  height: 96px;
  border-radius: 50%;
  object-fit: cover;
  box-shadow: 0 2px 8px rgba(0,0,0,0.10);
  margin-bottom: 16px;
}

.name-content h2 {
  color: #fff;
  font-size: 1.7rem;
  margin-bottom: 4px;
  font-weight: 700;
}

.box {
  background: #313742;
  border-radius: 8px;
  padding: 6px 18px;
  margin-bottom: 12px;
}

.text-role {
  color: var(--accent-main);
  font-size: 1.1rem;
  font-weight: 500;
  margin: 0;
}

hr {
  width: 80%;
  border: none;
  border-top: 1px solid #444;
  margin: 18px 0;
}

.contact-info {
  width: 100%;
  display: flex;
  flex-direction: column;
  gap: 14px;
}

.contact-item {
  display: flex;
  align-items: center;
  gap: 12px;
  background: #292929;
  border-radius: 7px;
  padding: 8px 12px;
  transition: background 0.2s;
  text-decoration: none;
  color: #bdbdbd;
  font-size: 1rem;
}

.contact-item:hover {
  background: #313742;
  color: var(--accent-main);
}

.contact-item span {
  color: inherit;
  text-decoration: none;
}

.icon-box {
  width: 28px;
  height: 28px;
  display: flex;
  align-items: center;
  justify-content: center;
}

.icon {
  width: 22px;
  height: 22px;
}

.contact-item a {
  color: #bdbdbd;
  text-decoration: none;
  font-size: 1rem;
  transition: color 0.2s;
}

.contact-item a:hover {
  color: var(--accent-main);
}

.contact-text {
  display: inline;
}

@media (max-width: 1024px) {
  .cont {
    position: absolute;
    top: 0;
    left: 0;
    width: 100vw;
    max-width: 100vw;
    margin: 0;
    border-radius: 0 0 14px 14px;
    box-shadow: 0 2px 12px rgba(0,0,0,0.10);
    background: #1f1f1f;
    min-height: unset;
    height: auto;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: flex-start;
    padding: 8px 4px 4px 4px;
    z-index: 999;
  }
  .item-row {
    flex-direction: column;
    align-items: center;
    gap: 12px;
    width: 100%;
    justify-content: flex-start;
    flex-wrap: nowrap;
  }
  .contact-info {
    flex-direction: row;
    gap: 14px;
    align-items: center;
    width: 100%;
    flex-wrap: wrap;
    justify-content: center;
    margin-top: 8px;
  }
  .contact-item {
    padding: 8px 12px;
    font-size: 1rem;
    border-radius: 7px;
    min-width: unset;
    flex: unset;
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 12px;
    margin-left: 0;
    margin-right: 0;
  }
  hr {
    display: none;
  }
  .contact-item {
    /* Hide text for email and phone, keep icons */
  }
  .contact-item:nth-child(1) a, /* Email */
  .contact-item:nth-child(2) a, /* GitHub */
  .contact-item:nth-child(3) a { /* Phone */
    display: none !important;
  }
  .contact-text {
    display: none;
  }
}

@media (max-width: 900px) {
  .cont {
    position: absolute;
    top: 0;
    left: 0;
    width: 100vw;
    max-width: 100vw;
    margin: 0;
    border-radius: 0 0 20px 20px;
    box-shadow: 0 2px 12px rgba(0,0,0,0.10);
    background: #1f1f1f;
    min-height: unset;
    height: auto;
    display: block;
    padding: 8px 4px 4px 4px;
    z-index: 999;
  }
  .item-row {
    flex-direction: column;
    align-items: center;
    gap: 12px;
    width: 100%;
    justify-content: flex-start;
    flex-wrap: nowrap;
  }
  .contact-info {
    flex-direction: row;
    gap: 14px;
    align-items: center;
    width: 100%;
    flex-wrap: wrap;
    justify-content: center;
    margin-top: 8px;
  }
  .contact-item {
    padding: 8px 12px;
    font-size: 1rem;
    border-radius: 7px;
    min-width: unset;
    flex: unset;
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 12px;
    margin-left: 0;
    margin-right: 0;
  }
  hr {
    display: none;
  }
  .contact-text {
    display: none;
  }
}

@media (max-width: 500px) {
  .cont {
    position: static;
    top: 0;
    left: 0;
    width: 100vw;
    max-width: 100vw;
    margin: 0;
    border-radius: 0 0 20px 20px;
    box-shadow: 0 2px 12px rgba(0,0,0,0.10);
    background: #1f1f1f;
    min-height: unset;
    height: auto;
    display: block;
    padding: 8px 4px 4px 4px;
    z-index: 10000;
  }
  .item-row {
    flex-direction: column;
    align-items: center;
    gap: 12px;
    width: 100%;
    justify-content: flex-start;
    flex-wrap: nowrap;
  }
  .contact-info {
    gap: 4px;
    flex-wrap: wrap;
    justify-content: center;
  }
  .contact-item {
    font-size: 0.75rem;
    padding: 3px 4px;
    min-width: 80px;
    flex: 1 1 80px;
    gap: 4px;
  }
  .contact-text {
    display: none;
  }
}
</style>
