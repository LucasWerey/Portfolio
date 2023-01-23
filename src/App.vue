<template>
  <div id="app">
    <div class="page">
      <div class="contenu">
        <NavBar />
        <div class="section1" id="S1">
          <HomePage />
        </div>
        <div class="section2" id="S2">
          <ProjectsPage />
        </div>
        <div class="section3" id="S3">
          <SkillsPage />
        </div>
      </div>
      <FooterBar />
    </div>
    <ButtonUp />
  </div>
</template>

<script>
import NavBar from './components/menu/NavBar.vue'
import HomePage from './views/HomePage.vue'
import ProjectsPage from './views/ProjectsPage.vue'
import FooterBar from './components/footer/FooterBar.vue'
import SkillsPage from './views/SkillsPage.vue'
import ButtonUp from './components/ButtonUp.vue'

export default {
  name: 'App',
  components: {
    NavBar,
    HomePage,
    ProjectsPage,
    FooterBar,
    SkillsPage,
    ButtonUp,
  },

  mounted() {
    var elementToChange = document.getElementsByTagName("body")[0];
    elementToChange.style.cursor = "url('https://img.icons8.com/external-doodle-bomsymbols-/50/null/external-arrow-cursor-doodle-web-design-device-set-1-doodle-bomsymbols--2.png'), auto";
    window.addEventListener('resize', this.Resize)
  },

  methods:{
    Resize(){
      if(window.innerWidth < 800){
        alert("Please use a bigger screen to see the website correctly")
      }
    }
  }
}
</script>

<style >
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;

}

body {
  background: #FDC830;
  /* fallback for old browsers */
  background: -webkit-linear-gradient(to right, #F37335, #FDC830);
  /* Chrome 10-25, Safari 5.1-6 */
  background: linear-gradient(to right, #F37335, #FDC830);
  /* W3C, IE 10+/ Edge, Firefox 16+, Chrome 26+, Opera 12+, Safari 7+ */

  min-height: 100%;
  min-width: 100%;
  margin: 0;
}


.page {
  display: flex;
  flex-direction: column;
  min-width: 100vw;

}

.section1 {
  width: 100%;
  height: 100vh;
}

.section2 {
  width: 100%;
  height: 100vh;
  background: #FFC70026;
}

.section3 {
  width: 100%;
  height: 90vh;
  background: #FDC830;
  margin-top: -1px;
}

::-webkit-scrollbar {
  width: 0px;
  background: transparent;
}

::-moz-scrollbar {
  width: 0px;
  background: transparent;
}
</style>
