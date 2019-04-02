<template>
    <button id="menu-item"
            class="btn--transparent"
            ref="component"
            @click="handleClick()">
        <i class="material-icons icon--in-text"
           style="font-size: var(--font_size_semi_large)"
        >{{icon}}</i>
    </button>
</template>

<script>
    import Styleable from '../base/Styleable';

    export default {
        name: "MenuItem",
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
</style>