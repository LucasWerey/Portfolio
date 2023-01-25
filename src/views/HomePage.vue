<template>
  <div class="page" style="height: 100vh;">
    <div class="center-content">
      <div class="text"><v-typical class="blink"
          :steps="['Hello 👋,', 3000, 'Bonjour 👋,', 3000, 'Hallo 👋,', 3000, 'Holà 👋,', 3000, 'おはよう 👋,', 3000]" :loop="Infinity"
          :wrapper="'p'"></v-typical>
        <p>I'm <span class="name">Lucas</span></p>
        <p>welcome on </p>
        <p>my personal website</p>
      </div>
      <img class="image" src="../images/man.svg" alt="Image">
    </div>
    <div class="custom-shape-divider-bottom-1674134076">
      <svg data-name="Layer 1" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1200 120" preserveAspectRatio="none">
        <path
          d="M985.66,92.83C906.67,72,823.78,31,743.84,14.19c-82.26-17.34-168.06-16.33-250.45.39-57.84,11.73-114,31.07-172,41.86A600.21,600.21,0,0,1,0,27.35V120H1200V95.8C1132.19,118.92,1055.71,111.31,985.66,92.83Z"
          class="shape-fill"></path>
      </svg>
    </div>

  </div>


</template>


<script>
import VTypical from 'vue-typical';

export default {
  components: {
    VTypical,
  },
};
</script>


<style scoped>
.page {
  display: flex;
  align-items: center;
  justify-content: center;
}

.center-content {
  display: flex;
  align-items: center;
  justify-content: center;
}

.text {
  font-size: 50px;
  color: #fff;
  font-weight: bold;
  width: 100%;
  padding-right: 20px;
}
@media (max-width: 800px) {
  .text {
    font-size: 30px;
  }
}

@media (max-width: 600px) {
  .text {
    font-size: 20px;
  }
}

.image {
  width: 80%;
  height: 80%;
}

p {
  margin: 0;
}

p:nth-child(2) span {
  text-decoration: none;
  box-shadow: inset 0 -.5em 0 #FDC830;
  color: inherit;
}

.custom-shape-divider-bottom-1674134076 {
  position: absolute;
  bottom: 0;
  left: 0;
  width: 100%;
  overflow: hidden;
  line-height: 0;
}

.custom-shape-divider-bottom-1674134076 svg {
  position: relative;
  display: block;
  width: calc(100% + 1.3px);
  height: 220px;
}

.custom-shape-divider-bottom-1674134076 .shape-fill {
  fill: #FFC70026;
}


.blink::after {
  content: '|';
  animation: blink 1s infinite step-start;
}

.bubble {
  width: 10px;
  height: 10px;
  background-color: #000;
  border-radius: 50%;
  position: absolute;
}


@keyframes blink {
  50% {
    opacity: 0;
  }
}
</style>