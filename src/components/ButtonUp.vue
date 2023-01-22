<template>
    <div class="BTN">
        <button class="GoTopBtn" v-on:click="goToTop"><span class="arrowup"></span></button>
    </div>
</template>

<script>
export default {
    methods: {
        goToTop() {
            window.scrollTo({ top: 0, behavior: 'smooth' });
        }
    }
}
</script>

<style>
.BTN {
    position: fixed;
    bottom: 7%;
    right: 5%;
    display: flex;
    justify-content: center;
    align-items: center;
}

.GoTopBtn {
    border: 1px solid #F37335;
    background-color: #F37335;
    border-radius: 100%;
    width: 50px;
    height: 50px;
    color: #fff;
    font-size: 20px;
    font-weight: bold;
    text-align: center;
    text-decoration: none;
    display: inline-block;
    cursor: pointer;
}

.GoTopBtn:hover {
    animation-duration: 1.2s;
    animation-name: bounce;
    animation-iteration-count: infinite;
}

.arrowup {
    border: solid #fff;
    width: 8px;
    height: 8px;
    border-width: 0 3px 3px 0;
    display: inline-block;

    transform: rotate(-135deg);
    -webkit-transform: rotate(-135deg);
}

@keyframes bounce {
    from {
        transform: translateY(0);
    }

    50% {
        transform: translateY(-10px);
    }

    to {
        transform: translateY(0);
    }
}
</style>