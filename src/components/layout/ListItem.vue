<template>
    <div class="list-item"
         ref="component"
         @click="handleClick()">
        <slot></slot>
    </div>
</template>

<script>
    import Styleable from '../mixins/Styleable';

    export default {
        name: "ListItem",
        mixins: [Styleable],
        methods: {
            handleClick() {
                this.$emit('click');
            }
        }
    }
</script>

<style lang="css" scoped>
    .list-item {
        padding: var(--padding_side);
        color: var(--color_black);
        background-color: var(--color_white);
        font-size: var(--font_size_regular);
        border-bottom: 1px solid rgba(0, 0, 0, 0.05);
    }
    .list-item:first-child {
        border-top: 1px solid rgba(0, 0, 0, 0.05);
    }
</style>