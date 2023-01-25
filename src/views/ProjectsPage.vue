<template>
  <div class="container" >
    <h1 class="title">My Projects</h1>
    <div class="project">
      <!-- <div class="card" v-for="(card, index) in cards" :key="index">
        <img class="card-img-top" :src="card.image" :alt="card.alt">
        <div class="card-body">
          <h2 class="body-title">{{ card.titre }}</h2>
          <p class="card-text">{{ card.text }}</p>
        </div>
        <a :class="`card-button ${card.disabled} pointer`" :href="`${card.link}`" target="_blank">
          <p>Discover !</p>
        </a>
        <div class="card-footer">
          <div class="stack" v-for="(stack, index) in card.stack" :key="index">
            <img :src="`../img/${stack}`" alt="Image Tag" />
          </div>
        </div>
      </div>-->
      <!--<CarouselView @next="nextSlide" @previous="prevSlide">
      <ProjectCarousel v-for="(card, index) in cards" :key="card" :index="index" :visibleSlide="visibleSlide">-->
        <ProjectCards v-bind:skills="cards"></ProjectCards>  
      <!--</ProjectCarousel>
      </CarouselView>-->

    </div>
    <div class="custom-shape-divider-bottom-1674172921">
      <svg data-name="Layer 1" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1200 120" preserveAspectRatio="none">
        <path d="M741,116.23C291,117.43,0,27.57,0,6V120H1200V6C1200,27.93,1186.4,119.83,741,116.23Z" class="shape-fill">
        </path>
      </svg>
    </div>
  </div>
</template>

<script>
import DASHBOARD from "../images/Dashboard.png";
import FRESHCOOK from "../images/LogoFreshcook.png";
import OMNES from "../images/OmnesSante.png";
//import ProjectCarousel from "../components/carousel/CarouselSlider.vue";
//import CarouselView from "../components/carousel/CarouselView.vue";
import ProjectCards from "../components/carousel/CardProjects.vue";

export default {
  name: "ProjectsPage",
  components: {
    // ProjectCarousel,
    //CarouselView,
    ProjectCards
  },
  data() {
    return {
      cards: [
        { text: "Project to create a dashboard about the SNCF with the Data-SNCF API data", image: DASHBOARD, alt: "Image Dashboard", titre: "Dashboard SNCF", link: "https://dashboardlucaswerey.netlify.app/", stack: ["icons8-mongodb.7d4f7146.svg", "icons8-express-js.cc24394d.svg", "icons8-react.098ccd82.svg", "icons8-node-js.26176163.svg"], disabled: "false" },
        { text: "Prototyping project of a food delivery application on Figma", image: FRESHCOOK, alt: "Image Freshcook", titre: "Freshcook", link: "https://www.figma.com/proto/UjllwNPgwFAxsN9tRPEaAw/Projet-UI---Freshcook?page-id=116%3A247&node-id=118%3A1683&viewport=1007%2C264%2C0.07&scaling=scale-down&starting-point-node-id=116%3A248", stack: ["icons8-figma.5d7330fe.svg"], disabled: "false" },
        { text: "Project for the creation of a website for medical appointments", image: OMNES, alt: "OmnesSanté", titre: "Omnes Santé", link: "", stack: ["icons8-html-5.964cf5a7.svg", "icons8-css3.fdf257b7.svg", "icons8-javascript-logo.b3ed08f7.svg", "icons8-php-logo.6bb294f9.svg", "xml-svgrepo-com.1b6818d9.svg"], disabled: "disabled" }
      ],

      //   visibleSlide: 0

    }
  },

  /* computed: {
     cardsLenght() {
       return this.cards.length;
     }
   },
 
   methods: {
     nextSlide() {
       if(this.visibleSlide >= this.cardsLenght - 1) this.visibleSlide=0;
       else this.visibleSlide++;
     },
     prevSlide() {
       if(this.visibleSlide <= 0) this.visibleSlide= this.cardsLenght-1;
       else this.visibleSlide--;
     }
   }*/
}
</script>

<style scoped>
.container {
  display: flex;
  flex-direction: column;
  height: 95%;
  width: 70%;
  margin: auto;
}

img {
  width: 100%;
  height: 100%;
  object-fit: cover;
}

.title {
  font-size: 50px;
  color: #fff;
  font-weight: bold;
  height: auto;
  width: 100%;
}

.project{
  width: 100%;
  height : 80%;
  display: flex;
  flex-direction: column;
  justify-content: space-around;
  gap:3%;
}



.project .card:hover{
  opacity: 1;
  scale: 1.1;
  transition: scale 0.5s ease;
}

.project:hover > :not(:hover){
  opacity: .3;
}


/*



.card {
  position: relative;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  width: 400px;
  height: 500px;
  margin: 0 auto;
  border-radius: 20px;
  background-color: #fff;
  box-shadow: inset 0 0 0 1px rgba(0, 0, 0, 0.1), 0 2px 4px rgba(0, 0, 0, 0.2);
}


.card-img-top {
  width: 100%;
  height: 220px;
  object-fit: cover;
  border-radius: 15px 15px 0 0;
  filter: blur(0.2px);
  overflow: hidden;
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
  top: 54%;
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
  box-shadow: inset 0 0 0 1px rgba(0, 0, 0, 0.1), 0 2px 4px rgba(0, 0, 0, 0.2);
}

.disabled {
  background-color: #f3743588;
  pointer-events: none;
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
}*/

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

/*
@media (width <= 600px) {
  .project {
    grid-template-columns: repeat(1, 1fr);
    grid-template-rows: repeat(3, 1fr);
  }
}*/
/*
@media (600px <= width <= 1300px ){


 .project .card {
    width: 200px;
    height: 400px;
  }

  .project .card .card-body{
    font-size: small;
  }

  .project .card .card-button{
    top:38%;
  }

  .project .card .card-img-top{
    height: 100px;
  }
}
*/
</style>
