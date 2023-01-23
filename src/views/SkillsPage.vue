<template>
    <div class="container">
        <div class="Title">
            <h1>My Technologies</h1>
        </div>
        <div class="Skills">
            <div class="buttonContainer">
                <div class="buttonGrid">
                    <button @click="grid = 1" v-bind:class="{ active: grid === 1 }">Front <div class="circle"></div>
                    </button>
                    <span class="line1"></span>
                    <button @click="grid = 2" v-bind:class="{ active: grid === 2 }">Back <div class="circle"></div>
                    </button>
                    <span class="line2"></span>
                    <button @click="grid = 3" v-bind:class="{ active: grid === 3 }">Design <div class="circle"></div>
                    </button>
                </div>
            </div>
            <div v-if="grid === 1" :class="gridClass" class="grid-container">
                <div v-for="image in front" :key="image.src" class="imageSkills">
                    <img :src="image.src" :alt="image.alt" />
                </div>
            </div>
            <div v-if="grid === 2" :class="gridClass" class="grid-container">
                <div v-for="image in back" :key="image.src">
                    <img :src="image.src" :alt="image.alt" />
                </div>
            </div>
            <div v-if="grid === 3" :class="gridClass" class="grid-container">
                <div v-for="image in design" :key="image.src">
                    <img :src="image.src" :alt="image.alt" />
                </div>
            </div>
        </div>
    </div>
</template>



<script>
import HTML from "../images/icons8-html-5.svg";
import CSS from "../images/icons8-css3.svg";
import JS from "../images/icons8-javascript-logo.svg";
import SASS from "../images/sass-lang-icon.svg";
import REACT from "../images/icons8-react.svg";
import BOOTSTRAP from "../images/getbootstrap-icon.svg";
import MATERIALUI from "../images/icons8-material-ui.svg";
import TAILWINDCSS from "../images/tailwindcss-icon.svg";
import PHP from "../images/icons8-php-logo.svg";
import XML from "../images/xml-svgrepo-com.svg";
import MYSQL from "../images/mysql-official.svg";
import MONGODB from "../images/icons8-mongodb.svg";
import NODEJS from "../images/icons8-node-js.svg";
import EXPRESS from "../images/icons8-express-js.svg";
import PHOTOSHOP from "../images/icons8-adobe-photoshop.svg";
import INDESIGN from "../images/icons8-adobe-indesign.svg";
import FIGMA from "../images/icons8-figma.svg";


export default {
    data() {
        return {
            front: [
                { src: HTML, alt: "html5" },
                { src: CSS, alt: "css3" },
                { src: JS, alt: "js" },
                { src: SASS, alt: "sass" },
                { src: REACT, alt: "react" },
                { src: BOOTSTRAP, alt: "bootstrap" },
                { src: MATERIALUI, alt: "material-ui" },
                { src: TAILWINDCSS, alt: "tailwindcss" }
            ],

            back: [
                { src: PHP, alt: "php" },
                { src: XML, alt: "xml" },
                { src: MYSQL, alt: "mysql" },
                { src: MONGODB, alt: "mongodb" },
                { src: NODEJS, alt: "nodejs" },
                { src: EXPRESS, alt: "expressjs" }
            ],

            design: [
                { src: PHOTOSHOP, alt: "photoshop" },
                { src: INDESIGN, alt: "indesign" },
                { src: FIGMA, alt: "figma" }
            ],
            grid: 1
        }
    },
    computed: {
        gridClass() {
            return `grid-${this.grid}`
        },
    },
}

</script>

<style scoped>
.container {
    height: 70vh;
    width: 100%;
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
}

.Title {
    width: 50%;
    height: 10%;
    display: flex;
    justify-content: start;
    align-items: center;
    top: 0;
    padding-bottom: 4%;
}

.Title h1 {
    text-align: left;
    font-size: 50px;
    color: #fff;
    font-weight: bold;
}

.Skills {
    width: 50%;
    height: 50%;
    display: flex;
    flex-direction: row;
}

.buttonContainer {
    width: 30%;
    height: 100%;
}

.buttonContainer .buttonGrid {
    display: flex;
    flex-direction: column;
    border-left: 2px solid #F37335;
    margin-top: 5px;
}

.buttonContainer .buttonGrid Button {
    width: 150px;
    height: auto;
    border: none;
    display: flex;
    flex-direction: row-reverse;
    align-items: center;
    justify-content: start;
    gap: 10px;
    background-color: transparent;
    font-size: 30px;
    color: #ffff;
}

.buttonContainer .buttonGrid .active .circle {
    background-color: #ffff;
    transition: ease-in-out 0.4s;
}

.buttonContainer .buttonGrid Button .circle {
    width: 30px;
    height: 30px;
    border-radius: 50%;
    background-color: transparent;
    border: 2px solid #ffff;
}

.line1,
.line2 {
    width: 2px;
    height: 50px;
    background-color: #ffff;
    transform: translateX(22px);
}

.grid-1 {
    display: grid;
    grid-template-columns: repeat(5, 1fr);
    grid-template-rows: auto;
    width: 100%;
    height: 70%;
    margin: 5px;
    border-top: #F37335 2px solid;
    border-right: #F37335 2px solid;
}

.grid-2 {
    display: grid;
    grid-template-columns: repeat(5, 1fr);
    grid-template-rows: auto;
    width: 100%;
    height: 70%;
    margin: 5px;
    border-top: red 2px solid;
    border-right: red 2px solid;
}

.grid-3 {
    display: grid;
    grid-template-columns: repeat(5, 1fr);
    grid-template-rows: auto;
    width: 100%;
    height: 70%;
    margin: 5px;
    border-top: rgb(0, 0, 0) 2px solid;
    border-right: rgb(0, 0, 0) 2px solid;
}

.imageSkills {
    display: flex;
    justify-content: center;
    align-items: center;
}

img {
    width: 100px;
    height: 100px;
    margin: 5px;
}

img:hover {
    animation-duration: 0.6s;
    animation-name: logo;
    animation-iteration-count: 1;
}

@keyframes logo {
    from {
        transform: rotate(0deg);
    }

    25% {
        transform: rotate(30deg);
    }

    50% {
        transform: rotate(-30deg);
    }

    75% {
        transform: rotate(30deg);
    }

    to {
        transform: rotate(0deg);
    }

}

@media (width <=1024px) {
    img {
    width: 75px;
    height: 75px;
}
.grid-1, .grid-2, .grid-3{
    grid-template-columns: repeat(3, 1fr);
    grid-template-rows: auto;
}
}
</style>