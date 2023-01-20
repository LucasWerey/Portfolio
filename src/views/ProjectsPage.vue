<template>
  <div class="container" style="height:100vh">
    <h1 class="title">My Projects</h1>
    <div class="grid">
      <div class="card" v-for="(card, index) in cards" :key="index">
        <img class="card-img-top" :src="`../img/${card.image}`" :alt="card.alt">
        <div class="card-body">
          <h2 class="body-title">{{ card.titre }}</h2>
          <p class="card-text">{{ card.text }}</p>
        </div>
        <a class="card-button" :href="`${card.link}`" target="_blank">
          <p>Discover !</p>
        </a>
        <div class="card-footer">
          <div class="stack" v-for="(stack, index) in card.stack" :key="index">
            <img :src="`../img/${stack}`" alt="Image Tag" />
          </div>
        </div>
      </div>
    </div>
    <div class="custom-shape-divider-bottom-1674172921">
    <svg data-name="Layer 1" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1200 120" preserveAspectRatio="none">
        <path d="M741,116.23C291,117.43,0,27.57,0,6V120H1200V6C1200,27.93,1186.4,119.83,741,116.23Z" class="shape-fill"></path>
    </svg>
</div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      cards: [
        { text: "Projet de création d'un dashboard autour de la SNCF grâce aux données de l’API Data-SNCF", image: "Dashboard.b493d4a9.png", alt: "Image Dashboard", titre: "Dashboard SNCF", link: "https://dashboardlucaswerey.netlify.app/", stack: ["icons8-mongodb.7d4f7146.svg", "icons8-express-js.cc24394d.svg", "icons8-react.098ccd82.svg", "icons8-node-js.26176163.svg"] },
        { text: "Projet de prototypage d'une application sur Figma", image: "LogoFreshcook.cc48dbc9.svg", alt: "Image Freshcook", titre: "Freshcook", link: "https://www.figma.com/proto/UjllwNPgwFAxsN9tRPEaAw/Projet-UI---Freshcook?page-id=116%3A247&node-id=118%3A1683&viewport=1007%2C264%2C0.07&scaling=scale-down&starting-point-node-id=116%3A248", stack: ["icons8-figma.5d7330fe.svg"] },
        { text: "Projet de création d'un site de prise de rendez-vous médicaux", image: "OmnesSante.8e64e231.png", alt: "OmnesSanté", titre: "Omnes Santé", link: "", stack: ["icons8-html-5.964cf5a7.svg", "icons8-css3.fdf257b7.svg", "icons8-javascript-logo.17196e9c.svg", "icons8-php-logo.6bb294f9.svg", "xml-svgrepo-com.1b6818d9.svg"] }
      ]
    }
  }
}
</script>

<style scoped>
.container {
  display: flex;
  flex-wrap: wrap;
  height: 100%;
  width: 50%;
  margin: auto;
}

.grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  grid-gap: 16px;
  width: 100%;
  height: 85%;
}

@media (max-width: 600px) {
  .grid {
    grid-template-columns: repeat(1, 1fr);
    grid-template-rows: repeat(3, 1fr);
  }
}


.title {
  text-align: left;
  margin-bottom: 20px;
  font-size: 50px;
  color: #fff;
  font-weight: bold;
}



.card {
  position: relative;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  width: 300px;
  height: 500px;
  margin: 0 auto;
  border-radius: 20px;
  background-color: #fff;
  box-shadow: inset 0 0 0 1px rgba(0, 0, 0, 0.1), 0 2px 4px rgba(0, 0, 0, 0.2);
}

.card-img-top {
  width: 100%;
  height: 200px;
  object-fit: cover;
  border-radius: 15px 15px 0 0;
  filter: blur(0.2px);
}

.card-body {
  flex: 1;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  padding: 20px;
}

.card-text {
  text-align: center;
}


.card-button {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -175%);
  width: 100px;
  background-color: #F37335;
  color: white;
  padding: 10px;
  border-radius: 4px;
  border: none;
  display: flex;
  align-items: center;
  justify-content: center;
  text-decoration: none;
}

.card-button p {
  margin: 0;
}

.card-footer {

  width: 90%;
  padding: 10px;
  text-align: center;
  border-top: 1px solid #F37335;
}

.stack {
  display: inline-flex;

}

.stack img {
  width: 30px;
  height: 30px;
  margin: 5px;
}

.custom-shape-divider-bottom-1674172921 {
    position: absolute;
    bottom: -100%;
    left: 0;
    width: 100%;
    overflow: hidden;
    line-height: 0;
}

.custom-shape-divider-bottom-1674172921 svg {
    position: relative;
    display: block;
    width: calc(100% + 1.3px);
    height: 115px;
    transform: rotateY(180deg);
}

.custom-shape-divider-bottom-1674172921 .shape-fill {
    fill: #FDC830;
}
</style>
