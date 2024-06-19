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
            <img class="icon" src="../assets/email.png" />
          </div>
          <a href="mailto:borisdimitrov1998@gmail.com">Send Mail</a>
        </div>
        <div class="contact-item">
          <div class="icon-box">
            <img class="icon" src="../assets/github.png" />
          </div>
          <a href="https://github.com/BorisDmv" target="_blank">My GitHub</a>
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
  margin: 2rem 0 2rem 2rem;
  height: 1000px;
  min-width: 320px;
  width: 20%;
  position: sticky; /* Fixed position */
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
  align-items: start;
  width: 50%;
  margin: auto;
}

.contact-item {
  width: 100%;
  display: flex;
  align-items: center;
  margin: 10px 0;
}

.icon-box {
  width: 26%;
  height: 40px;
  background: #3a3a3a;
  border-radius: 15px;
  display: flex;
  justify-content: center;
  align-items: center;
  margin-right: 10px;
}

.icon {
  height: 25px;
}

@media (max-width: 1024px) {
  .row{
    padding: 2rem;
  }

  .icon-box {
    width: 50%;
  }

  .container {
    width: auto;
    height: auto;
    margin: 2rem 2rem 0 2rem;
    position: relative;
  }

  .contact-info {
    flex-direction: row;
    justify-content: center;
  }

  .contact-item {
    width: 100%;
  }

}

@media (max-width: 860px) {
  .container{
    margin: 0 0 2rem 0;
    min-width: auto;
  }

  .contact-info {
    flex-direction: column;
  }

  .contact-item{
    justify-content: center;
  }
}
</style>