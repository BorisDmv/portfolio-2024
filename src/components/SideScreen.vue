<template>
  <div class="container">
    <div class="row">
      <img class="user-profile" src="../assets/40300461.png" />
      <div class="name-content">
        <h2>Boris Dimitrov</h2>
      </div>
      <div class="box">
        <p class="text-role">Software Engineer</p>
      </div>
      <hr>
      <div class="contact-info">
        <div class="contact-item">
          <div class="icon-box">
            <i class="icon-email"></i>
          </div>
          <span>borisdimitrov1998@gmail.com</span>
        </div>
        <div class="contact-item">
          <div class="icon-box">
            <i class="icon-phone"></i>
          </div>
          <span>+359 876079546</span>
        </div>
        <div class="contact-item">
          <div class="icon-box">
            <i class="icon-birthday"></i>
          </div>
          <span>Jan 31, 1998</span>
        </div>
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
h2 {
  color: #f2f2f2;
  font-weight: bold;
  font-size: 1.6rem;
}

.text-role{
  font-size: 0.9rem;
  font-weight: 500;
}

.user-profile{
  width: 100px;
  height: 100px;
  border-radius: 50%;
  margin-bottom: 20px;
}

.container {
  background: #1f1f1f;
  margin: 2rem;
  width: 20%;
  position: fixed; /* Fixed position */
  top: 0;
  bottom: 0;
  left: 0;
  border-radius: 15px;
  display: flex;
  justify-content: center;
  flex-direction: column;
}

.row {
  text-align: center;
}

.name-content{
  margin-bottom: 20px;
}

.box {
  background-color: #3a3a3a;
  border-radius: 10px;
  padding: 10px;
  color: #fff;
  width: 62%;
  display: flex;
  justify-content: center;
  margin: auto;
}

hr {
  width: 80%;
  margin: 20px auto;
}

.contact-info {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.contact-item {
  display: flex;
  align-items: center;
  margin: 10px 0;
}

.icon-box {
  width: 30px;
  height: 30px;
  border: 2px solid #000;
  border-top: none;
  border-right: none;
  opacity: 0.6;
  display: flex;
  justify-content: center;
  align-items: center;
  margin-right: 10px;
}

.icon-email:before {
  content: "\2709"; /* Unicode character for an envelope icon */
}

.icon-phone:before {
  content: "\260E"; /* Unicode character for a phone icon */
}

.icon-birthday:before {
  content: "\1F382"; /* Unicode character for a birthday cake icon */
}

@media (max-width: 1024px) {
  .container {
    width: auto;
    height: auto;
    position: relative;
  }
}
</style>