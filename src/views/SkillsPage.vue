<template>
    <div class="container">
        <div class="spinner">
    
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            images: [
                { src: "icons8-css3.fdf257b7.svg", alt: "css3" },
                { src: "icons8-html-5.964cf5a7.svg", alt: "html5" },
                { src: "xml-svgrepo-com.1b6818d9.svg", alt: "xml" },
            ]
        }
    }
}

</script>

<style scoped>
.container {
    height: 100vh;
    width: 100%;
    display: flex;
    justify-content: center;
    align-items: center;
}
</style>