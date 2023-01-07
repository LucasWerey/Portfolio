<template>
<div id="app">
  <NavBar />
  <Home />
</div>
</template>

<script>
import NavBar from './components/menu/NavBar.vue'
import Home from './views/HomePage.vue'

export default {
  name: 'App',
  components: {
    NavBar,
    Home
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}

body{
  background-color: #BEBEBE;
  min-height: 100vh;
  width: 100%;
  margin:0;
}

</style>
