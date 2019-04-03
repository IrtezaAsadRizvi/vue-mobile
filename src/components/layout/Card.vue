<template>
    <div class="card"
         @click="handleClick()"
         ref="component">
        <slot></slot>
    </div>
</template>

<script>
    import Styleable from '../base/Styleable';

    export default {
        name: "Card",
        mixins: [Styleable],
        props: {
            styles: {
                type: Object,
                default: () => {
                    return {
                        color: '#212121',
                        backgroundColor: 'transparent',
                        fontSize: '16px'
                    }
                },
            },
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

    .card {
        box-shadow: 0 2px 1px -1px rgba(0,0,0,.2), 0 1px 1px 0 rgba(0,0,0,.14), 0 1px 3px 0 rgba(0,0,0,.12);
        transition: box-shadow 280ms cubic-bezier(.4,0,.2,1);
        display: block;
        position: relative;
        padding: var(--padding_side);
        border-radius: var(--border_radius_standard);
        margin: 10px var(--padding_side);
    }
</style>