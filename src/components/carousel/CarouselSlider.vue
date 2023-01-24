<template>
    <transition name="right" mode="in-out">
        <div v-show="visibleSlide === index" class="carousel-slider">
            <slot></slot>
        </div>
    </transition>
</template>

<script>
export default {
    props: ['index', 'visibleSlide'],
    data() {
        return {
            // ...
        }
    },
}

</script>


<style scoped>

.carousel-slider {
    top:0;
    right:0;
    left:0;
    bottom:0;
    width: 100%;
    height: 100%;
    overflow: hidden;
}
.left-slide-enter-active {
    animation: leftInAnim 0.4s ease-in-out;
}

.left-slide-leave-active {
    animation: leftOutAnim 0.4s ease-in-out;
}

@keyframes leftInAnim {
    from {
        transform: translateX(100%);
    }

    to {
        transform: translateX(0);
    }
}

@keyframes leftOutAnim {
    from {
        transform: translateX(0);
    }

    to {
        transform: translateX(-100%);
    }

}

.right-enter-active {
    animation: rightInAnim 0.4s ease-in-out;
}

.right-leave-active {
    animation: rightOutAnim 0.4s ease-in-out;
}

@keyframes rightInAnim {
    from {
        transform: translateX(-100%);
    }

    to {
        transform: translateX(0);
    }
}

@keyframes rightOutAnim {
    from {
        transform: translateX(0);
    }

    to {
        transform: translateX(100%);
    }

}
</style>