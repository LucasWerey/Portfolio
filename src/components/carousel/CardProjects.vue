<template>
  <div class="card" v-for="info in skills" :key="info">
    <div class="card-img">
      <img :src="info.image" class="card-img-left" alt="Card background image">
    </div>
    <div class="card-body">
      <h2 class="card-title">{{ info.titre }}</h2>
      <h3 class="card-text">{{ info.text }}</h3>
        <a :href="info.link" :class="`card-btn ${info.disabled}`" target="_blank" aria-label="Click me it's cool !">
          <p>Discover !</p>
        </a>
    <div class="footer">
      <div class="footer-stacks">
        <img v-for="stack in info.stack" :src="`../img/${stack}`" alt="stack" :key="stack" class="stacks">
      </div>
    </div>
    </div>
    <div class="aside">
      <div class="aside-stacks">
        <img v-for="stack in info.stack" :src="`../img/${stack}`" alt="stack" :key="stack" class="stacks">
      </div>
    </div>
  </div>
</template>

<script>

export default {
  name: 'CardProjects',
  props: {
    skills: {
      type: Array,
      required: true
    }
  },
}


</script>
<style scoped>
.card {
  display: flex;
  flex-direction: row;
  justify-content: space-evenly;
  align-items: center;
  height: 100%;
  width: 100%;
  border-radius: 10px;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.5);
  overflow: hidden;
  transition: 0.5s;
  overflow: hidden;
}


.card-img {
  height: 100%;
  width: 50%;
  margin-right: 6%;
}

.card-img-left {
  height: 100%;
  width: 100%;
}

img {
  object-fit: cover;
}

.card-body {
  height: 100%;
  width: 50%;
  display: flex;
  flex-direction: column;
  justify-content: flex;
  align-items: flex-start;
}

@media (max-width: 768px) {
  .card-body {
    height: 100%;
    width: 70%;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
  }
}

.card-title {
  font-size: 30px;
  font-weight: 500;
  letter-spacing: 1px;
  color: #ffff;
}

@media (max-width: 768px) {
  .card-title {
    font-size: 20px;
  }
}

.card-text {
  font-size: 15px;
  font-weight: 200;
  letter-spacing: 1px;
  color: #ffff;
  height:20%;
}

@media (max-width: 768px) {
  .card-text {
    font-size: 12px;
  }
}

.footer{
  visibility: none;
  display:none;
}
.footer-stacks{
  visibility: hidden;
}

@media (max-width: 768px) {

  .footer{
    width: 100%;
    height: 20%;
    display: flex;
    align-items: center;
    margin:2%;
  }
  .footer-stacks{
    visibility: visible;
    width: 100%;
    display: flex;
    flex-direction: row;
    justify-content: space-around;
    align-items: center;
    margin:2%;
  }
}
.aside {
  height: 80%;
  width: 20%;
  border-left: 2px solid white;
  display: flex;
  flex-direction: row;
  align-items: center;
  margin: 1%;
}

@media (max-width: 768px) {
  .aside {
    display: none;
  }
}
.aside-stacks {
  height: 100%;
  width: 100%;
  display: flex;
  flex-direction: column;
  justify-content: space-around;
  align-items: center;
}

.stacks {
  height: 20%;
  width: 20%;
  margin: 1%;
  object-fit: contain;
}

@media (max-width: 768px) {
  .stacks {
    height: 10%;
    width: 10%;
  }
}

.card-btn {
  text-decoration: none;
  color: black;
  padding: 10px 10px;
  font-size: 15px;
  font-weight: 200;
  letter-spacing: 1px;
  outline: 0;
  border: 1px solid #FDC830;
  background-color: #FDC830;
  border-radius: 20px 20px 0px 0px;
  cursor: pointer;
  transition: transform 0.5s ease-in-out;
}

@media (max-width: 768px) {
  .card-btn {
    font-size: 12px;
    padding: 0;
    border-radius: 20px;
    padding:2px;
  }
}

.card-btn:hover,
.card-btn:focus {
  background-color: #FDC830;
  color: black;
  border: 1px solid #FDC830;
  box-shadow: 0 0 10px #ffd76985;
  transform: scale(1.1);
}

.disabled {
  pointer-events: none;
  visibility: hidden;
}
</style>