<template>
    <div>
        <div id="bottom-menu"
             :class="{'active': activeStatus}"
             ref="component"
             @touchmove="preventScroll">
            <slot></slot>
        </div>
        <div class="overlay" v-if="activeStatus" @click="openMenu()" @touchmove="preventScroll"></div>
    </div>
</template>

<script>
    import Styleable from '../mixins/Styleable';

    export default {
        name: "BottomMenu",
        mixins: [Styleable],
        props: {
            activeStatus: {
                type: Boolean,
                default: false,
            }
        },
        methods: {
            openMenu() {
                this.$emit('close')
            },
            preventScroll(e){
                e.preventDefault();
            },
        }
    }
</script>

<style lang="css" scoped>
    #bottom-menu {
        position: fixed;
        overflow-y: auto;
        right: 0;
        bottom: 0;
        left: 0;
        height: auto;
        color: var(--color_black);
        background-color: var(--color_white);
        font-size: var(--font_size_regular);
        z-index: 1000;
        transform: translateY(100%);
        transition: 0.3s;
    }
    #bottom-menu.active {
        transform: translateY(0%);
    }
    .overlay {
        position: fixed;
        top: 0;
        bottom: 0;
        left: 0;
        right: 0;
        background-color: rgba(0, 0, 0, 0.4);
        z-index: 990;
    }
</style>