<template>
    <button class="menu-item btn--transparent"
            ref="component"
            @click="handleClick()">
        <i class="material-icons icon--in-text"
           style=""
        >{{icon}}</i>
    </button>
</template>

<script>
    import Styleable from '../mixins/Styleable';

    export default {
        name: "MenuItem",
        mixins: [Styleable],
        props: {
            icon: {
                type: String,
                default: "crop_square",
            }
        },
        methods: {
            handleClick() {
                this.$emit('click');
            }
        }
    }
</script>

<style lang="css" scoped>
    @import url('../../assets/global.css');

    .menu-item {
        color: var(--color_black);
        background-color: var(--color_white);
    }
    .menu-item i{
        font-size: var(--font_size_semi_large);
    }
</style>