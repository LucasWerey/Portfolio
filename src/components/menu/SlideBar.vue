<template>
    <div class="slidebar">
        <transition name="slide">
            <div v-if="isPanelOpen" class="slidebar-panel">
                <slot></slot>
            </div>
        </transition>
    </div>
</template>

<script>
import { store, mutations } from '../../store'
export default {
    methods: {
        closeslidebarPanel: mutations.toggleNav
    },
    computed: {
        isPanelOpen() {
            return store.isNavOpen
        }
    }
}
</script>
<style>
.slidebar-panel {
    position: fixed;
    left: 0;
    height: 50px;
    width: 90%;
    display: flex;
    justify-content: end;
    align-items: center;
    z-index: 100;
}
</style>