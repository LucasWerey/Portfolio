<template>
    <div class="Nav">
        <div class="Top">
            <div class="log"><img src="../../images/logoSite.svg" alt="logo" /> </div>
            <ul class="menu">
                <li class="menu-item" v-for="link in links" :key="link.id">
                    <a v-on:click="scroll(link.scroll)" class="menu-link">
                        <span :id="link.id">{{ link.text }}</span>
                    </a>
                </li>
            </ul>
            <div class="Burger">
                <BurgerMenu />
            </div>
        </div>
        <SlideBar id="SlideBar">
            <ul class="menu" id="MenuSlide">       
                <li class="menu-item" v-for="link in links" :key="link.id">
                    <a v-on:click="scroll(link.scroll)" class="menu-link">
                        <span :id="link.id">{{ link.text }}</span>
                    </a>
                </li>
            </ul>
        </SlideBar>
    </div>
</template>

<script>
import BurgerMenu from './BurgerMenu.vue'
import SlideBar from './SlideBar.vue'


export default {

    components: {
        BurgerMenu,
        SlideBar
    },
    data() {
        return {
            selectedElementWidth: 0,
            links: [{
                id: 1,
                text: 'Home',
                scroll: "S1"
            },
            {
                id: 2,
                text: 'Projects',
                scroll: "S2"
            },
            {
                id: 3,
                text: 'Skills',
                scroll: "S3"
            },
          /*  {
                id: 4,
                text: 'Contact',
                scroll: "S4"
            },*/],
        }
    },

    mounted() {
        window.addEventListener('scroll', this.CheckCurrentSection)
    },


    methods: {

        CheckCurrentSection() {
            let currentSection1 = document.querySelector('.section1');
            let currentSection2 = document.querySelector('.section2');
            let currentSection3 = document.querySelector('.section3');

            let currentSectionY = currentSection1.getBoundingClientRect().top - 100;
            let currentSectionY2 = currentSection2.getBoundingClientRect().top - 100;
            let currentSectionY3 = currentSection3.getBoundingClientRect().top - 100;

            let currentSectionHeight = currentSection1.getBoundingClientRect().height;
            let currentSectionHeight2 = currentSection2.getBoundingClientRect().height;
            let currentSectionHeight3 = currentSection3.getBoundingClientRect().height;

            if (currentSectionY < 0 && (currentSectionY + currentSectionHeight) > 0) {
                this.selectedElementWidth = document.getElementById("1").offsetWidth;
                document.getElementById("1").classList.add("active");
            } else {
                document.getElementById("1").classList.remove("active");
            }

            if (currentSectionY2 < 0 && (currentSectionY2 + currentSectionHeight2) > 0) {
                this.selectedElementWidth = document.getElementById("2").offsetWidth;
                document.getElementById("2").classList.add("active");
            } else {
                document.getElementById("2").classList.remove("active");
            }

            if (currentSectionY3 < 0 && (currentSectionY3 + currentSectionHeight3) > 0) {
                this.selectedElementWidth = document.getElementById("3").offsetWidth;
                document.getElementById("3").classList.add("active");
            } else {
                document.getElementById("3").classList.remove("active");
            }

        },

        scroll(id) {
            document.getElementById(id).scrollIntoView({ behavior: "smooth", block: "start", inline: "nearest" });
        },

    }
}
</script>

<style scoped>
.Nav {
    position: fixed;
    overflow: hidden;
    top: 0;
    display: flex;
    justify-content: center;
    align-items: center;
    width: 100%;
    z-index: 9999;
}

.Top {
    padding: 30px 37px 30px 50px;
    display: flex;
    justify-content: space-between;
    position: relative;
    width: 85%;
    height: auto;
}

.menu {
    list-style-type: none;
    display: flex;
    align-items: center;
    padding: 0;
    margin: 0;
    position: relative;
    gap: 100px;
    font-weight: bolder;

}

#MenuSlide {
    display: inline-flex;
    list-style-type: none;
    font-weight: bolder;
    gap: 20px;
}

.menu-item {
    display: inline-flex;
}

.menu-link {
    color: white;
    text-decoration: none;
    width: 100%;
    cursor: pointer;
}

.menu-link span {
    font-size: 2em;
    position: relative;
} 


span.active::after {
    content: '';
    position: absolute;
    width: 100%;
    height: 4px;
    background-color: rgb(255, 255, 255);
    left: 0;
    bottom: -5px;
    border-radius: 2px;
    animation: appear 0.4s linear;
}

@keyframes appear {
    from {
        width: 0%;
    }

    to {
        width: 100%;
    }
}

.Burger {
    display: none;
}

#SlideBar {
    display: none;
}


@media screen and (max-width: 768px) {

    .menu {
        display: none;
    }

    .Burger {
        display: block;
    }

    #SlideBar {
        display: block;
    }

    #menuSlide .menu-item .menu-link {
        display: block;
        font-size: 5px;
    }
}
</style>