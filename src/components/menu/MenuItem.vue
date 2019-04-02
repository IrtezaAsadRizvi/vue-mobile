<template>
    <button id="menu-item" class="btn--transparent" @click="handleClick()">
        <i class="material-icons icon--in-text"
           style="font-size: var(--font_size_semi_large)"
        >{{icon}}</i>
    </button>
</template>

<script>
    export default {
        name: "MenuItem",
        props: {
            color: {
                type: String,
                default: "#212121",
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