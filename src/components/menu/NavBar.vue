<template>
    <div class="Nav">
    <div class="Top">
        <div class="log">Logo</div>  
    <ul class="menu">
        <div class="menu-indicator"></div>
        <li class="menu-item" v-for="link in links" :key="link.id">
            <a href="#" class="menu-link">
                <span>{{link.text}}</span>
            </a>
        </li>
    </ul>
    <div class="Burger">
    <BurgerMenu />
</div>
</div>
<SlideBar id="SlideBar">
    <ul class="menu" id="MenuSlide">
        <div class="menu-indicator"></div>
        <li class="menu-item" v-for="link in links" :key="link.id">
            <a href="#" class="menu-link">
                <span>{{link.text}}</span>
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
    data(){
        return{
            selectedElementWidth: 0,
            links:[{
                id:1,
                text: 'Home'
            },
            {
                id:2,
                text: 'Portfolio'
            },
            {
                id:3,
                text: 'Skills'
            },
            {
                id:4,
                text: 'Contact'
            },],
        }
    }
}
</script>

<style scoped>
.Nav{
    position:fixed;
    overflow: hidden;
    top:0;
    display:block;
    width: 100%;
    z-index: 9999;
}
.Top{
    padding: 30px 37px 30px 50px;
    display: flex;
    justify-content: space-between;
    position: relative;
    height: auto;
    background-color: #BEBEBE;
}
.menu{
    list-style-type: none;
    display: flex;
    align-items: center;
    padding: 0;
    margin: 0;
    position: relative;
    gap: 100px;
    font-weight: bolder;
   
}

#MenuSlide{
    display:inline-flex;
    list-style-type: none;
    font-weight: bolder;
    gap:20px;
}

.menu-item{
    display:inline-flex;
}

.menu-link{
    color: white;
    text-decoration: none;
    width: 100%;

}

.menu-link:hover{
    box-shadow: 0 -10px 0 rgb(117, 117, 117) inset;
    transition: box-shadow 0.3s ease-in-out;
}

.Burger{
    display: none; /* A changer pour le menu burger */
}

#SlideBar{
    display: none;
}

@media screen and (max-width: 768px){

    .menu{
        display: none;
    }

    .Burger{
        display: block;
    }

    #SlideBar{
        display: block;
    }

    #menuSlide .menu-item .menu-link{ 
        display: block;
        font-size: 5px;
    }
}
    
</style>