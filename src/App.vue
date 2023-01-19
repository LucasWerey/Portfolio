<template>
  <div id="app">
    <div class="page">
      <div class="contenu">
        <NavBar />

        <div class="container1">
          <HomePage />
        </div>
        <div class="container2">
          <ProjectsPage />
        </div>
      </div>
      <FooterBar />
    </div>
  </div>
</template>

<script>
import NavBar from './components/menu/NavBar.vue'
import HomePage from './views/HomePage.vue'
import ProjectsPage from './views/ProjectsPage.vue'
import FooterBar from './components/footer/FooterBar.vue'

export default {
  name: 'App',
  components: {
    NavBar,
    HomePage,
    ProjectsPage,
    FooterBar
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
  width: 100%;
  margin: 0;
}

.page {
  display: flex;
  flex-direction: column;

}

.container1 {
  width: 100%;
  height: 100vh;
}

.container2 {
  width: 100%;
  height: 120%;
  background: #FFC70026;
}


::-webkit-scrollbar {
  width: 0px;
  /* remove scrollbar space */
  background: transparent;
  /* optional: just make scrollbar invisible */
}

::-moz-scrollbar {
  width: 0px;
  /* remove scrollbar space */
  background: transparent;
  /* optional: just make scrollbar invisible */
}
</style>
