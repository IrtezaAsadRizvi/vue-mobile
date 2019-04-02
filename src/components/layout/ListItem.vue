<template>
    <div class="list-item"
         ref="component"
         @click="handleClick()">
        <slot></slot>
    </div>
</template>

<script>
    import Styleable from '../base/Styleable';

    export default {
        name: "ListItem",
        extends: Styleable,
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
    .list-item {
        padding: var(--padding_side);
        border-bottom: 1px solid rgba(0, 0, 0, 0.05);
    }
    .list-item:first-child {
        border-top: 1px solid rgba(0, 0, 0, 0.05);
    }
</style>