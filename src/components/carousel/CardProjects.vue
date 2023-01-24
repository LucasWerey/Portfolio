<template>
  <div class="card" v-for="info in skills" :key="info">
    <div class="card-img">
      <img :src="info.image" class="card-img-left" alt="Card background image">
    </div>
    <div class="card-body">
      <h2 class="card-title">{{ info.titre }}</h2>
      <h3 class="card-text">{{ info.text }}</h3>
      <a :href="info.link" :class="`card-btn ${info.disabled}`" target="_blank" aria-label="Click me it's cool !"><p>Discover !</p></a>
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
 }


 .card-img {
   height: 100%;
   width: 50%;
   margin-right:6%;
 }

 .card-img-left{
  height:100%;
  width: 100%;
 }

 img{
  object-fit: cover;
 }
 .card-body{
    height: 100%;
    width: 50%;
    display: flex;
    flex-direction: column;
    justify-content: flex;
    align-items: flex-start;
 }

 .card-title{
    font-size: 30px;
    font-weight: 500;
    letter-spacing: 1px;
    color: #ffff;
 }

 .card-text{
    font-size: 20px;
    font-weight: 200;
    letter-spacing: 1px;
    color: #ffff;
 }
 .aside{
    height: 80%;
    width: 20%;
    border-left: 2px solid white;
    display: flex;
    flex-direction: row;
    align-items: center;
    margin : 1%;
 }

 .aside-stacks{
    height: 100%;
    width: 100%;
    display: flex;
    flex-direction: column;
    justify-content: space-around;
    align-items: center;
 }
 .stacks{
    height: 20%;
    width: 20%;
    margin: 1%;
    object-fit: contain;
 }

 .card-btn{
  text-decoration: none;
  color: black;
  font-size: 15px;
  font-weight: 200;
  letter-spacing: 1px;
  padding: 0.5% 2%;
  outline: 0;
  border: 1px solid black;
  cursor: pointer;
  position: relative;
  background-color: rgba(0, 0, 0, 0);
 }

 .card-btn::after{
  content: "";
  background-color: #FDC830;
  width: 100%;
  z-index: -1;
  position: absolute;
  height: 100%;
  top: 5px;
  left: 5px;
  transition: 0.2s;
 }

  .card-btn:hover::after{
    top: 0;
    left: 0;
  }

 .disabled{
  content:"Coming soon";
  pointer-events: none;
 }

</style>