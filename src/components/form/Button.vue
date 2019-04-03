<template>
    <button class="button"
            ref="component"
            @click="handleClick($event)">
        <slot></slot>
    </button>
</template>

<script>
    import Styleable from '../mixins/Styleable';
    import Tappable from '../mixins/Tappable';

    export default {
        name: "Button",
        mixins: [Styleable, Tappable]
    }
</script>

<style lang="css" scoped>
    @import url('../../assets/global.css');

    .button {
        padding: var(--padding_side);
        border: 0;
        outline: 0;
        color: var(--color_black);
        background-color: var(--color_white);
        font-size: var(--font_size_regular);
        text-transform: uppercase;
        border-radius: var(--border_radius_standard);
        box-shadow: 0 3px 1px -2px rgba(0,0,0,.2), 0 2px 2px 0 rgba(0,0,0,.14), 0 1px 5px 0 rgba(0,0,0,.12);
        transition: box-shadow 280ms cubic-bezier(.4,0,.2,1);

        overflow: hidden;
        position: relative;
    }
</style>