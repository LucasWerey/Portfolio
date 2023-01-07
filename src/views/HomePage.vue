<template>
    <div class="Home">
        <div class="Container">
            <div class="Container-left">
                <div class="Image" id="square">
                    <img src="../images/PhotoProfil.jpg" alt="Lights">
                </div>
                <div class="Circle">
                    <h1>1</h1>
                </div>
            </div>
            <div class="Container-right">
                <div class="Text">
                    Lorem ipsum dolor sit amet, consectetur adipiscing elit.ezaeza eezaezae ezaezae ddd
                </div>
            </div>
        </div>
    </div>
</template>

<script>
</script>

<style scoped>
.Home {
    margin-top: 20px;
    height: 90vh;
    width: 100%;
    display: block;
}

.Container {
    width: 60%;
    height: 100%;
    display: flex;
    flex-direction: row;
    align-items: center;
    margin-left: 20%;
}

.Container #square {
    position: relative;
    width: 450px;
    height: 450px;
    clip-path: polygon(50% 0%, 100% 50%, 50% 100%, 0% 50%);
    transform-origin: bottom left;
    box-sizing: border-box;
    background: #ffffff;
    border: 5px solid #ffffff;
    display: flex;
    justify-content: center;
    align-items: center;
}



#square img {
    width: 99%;
    height: 99%;
    object-fit: cover;
    clip-path: polygon(50% 0%, 100% 50%, 50% 100%, 0% 50%);
    position: absolute;
    top: 2px;
}

.Container-left {
    display: flex;
    flex-direction: column;
    align-items: center;
    padding-top: 2%;
}

.Circle {
    width: 200px;
    height: 200px;
    border-radius: 50%;
    background-color: #BEBEBE;
    border: #ffffff 5px solid;
    position: relative;
    top: -90px;
    display: flex;
    justify-content: center;
    align-items: center;
}

.Circle h1 {
    font-size: 100px;
    color: #ffffff;
}

@media screen and (max-width: 768px) {

    .Home {
        margin-top: 50px;
        height: 100%;
        width: 100%;
        display: block;
    }
    .Container {
        margin-left: 0%;
        width: 100%;
        display: flex;
        flex-direction: column;
        padding-top: 30px;
        gap : 40px;
    }

    .Container-left {
        display:block;
        width: 80vw;
    }

    .Container-right {
        display:block;
        width: 80vw;
    }
    .Circle{
        display:none;
    }
    .Container #square { 
       clip-path: none;
       border: none;
        background: none;
        width: 80vw;
        height: 50vh;
    }
    .Container #square img {
        clip-path: none;
        width: 100%;
        height: 100%;
        top:0;
        border:#ffffff 5px solid;
        border-radius: 15%;
        box-shadow: 7px 7px 7px 0 rgba(0, 0, 0, 0.25);
    }
}
</style>