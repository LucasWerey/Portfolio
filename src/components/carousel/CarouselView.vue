<template>
    <div class="carousel">
        <slot></slot>

        <button @click="previous" class="previous">Previous</button>
        <button @click="next" class="next">Next</button>
    </div>
</template>

<script>
export default {
    data() {
        return {
            // ...
        }
    },

    methods: {
        next() {
            this.$emit('next');
        },
        previous() {
            this.$emit('previous');
        }
    }
}
</script>

<style scoped>

.carousel {
    position: relative;
    width: 100%;
    height: 100%;
    overflow: hidden;
}

button{
    position : absolute;
    height: 40px;
    width: 50px;
    top: calc(50% - 20px);
    background-color: rgba(0,0,0,0.8);
    color: white;
    border: none;
}

button:focus, button:hover{
outline: none;
cursor: pointer;
}

.next{
    right: 0;
}

.previous{
    left: 0;
}

</style>