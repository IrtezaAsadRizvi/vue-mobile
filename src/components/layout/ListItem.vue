<template>
    <div class="list-item"
         :style="{color: color}"
         @click="handleClick()">
        <slot></slot>
    </div>
</template>

<script>
    export default {
        name: "ListItem",
        props: {
            color: {
                type: String,
                default: "#212121",
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
    .list-item {
        padding: var(--padding_side);
        border-bottom: 1px solid rgba(0, 0, 0, 0.05);
    }
    .list-item:first-child {
        border-top: 1px solid rgba(0, 0, 0, 0.05);
    }
</style>