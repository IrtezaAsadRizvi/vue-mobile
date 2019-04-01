<template>
    <div>
        <div id="side-menu" :class="{'active': activeStatus}" @touchmove="preventScroll">
            <slot></slot>
        </div>
        <div class="overlay" v-if="activeStatus" @click="openSideMenu()" @touchmove="preventScroll"></div>
    </div>
</template>

<script>
    export default {
        name: "SideMenu",
        data() {
            return {
                side_menu_active: false
            }
        },
        props: {
            activeStatus: {
                type: Boolean,
                default: false,
            }
        },
        methods: {
            openSideMenu() {
                this.$emit('close')
            },
            preventScroll(e){
                e.preventDefault();
            },
        }
    }
</script>

<style lang="css" scoped>
    #side-menu {
        position: fixed;
        overflow-y: auto;
        top: 0;
        bottom: 0;
        left: 0;
        width: 75%;
        background: var(--color_white);
        z-index: 1000;
        transform: translate(-100%);
        transition: 0.3s;
    }
    #side-menu.active {
        transform: translate(0%);
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