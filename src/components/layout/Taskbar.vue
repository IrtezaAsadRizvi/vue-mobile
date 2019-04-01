<template>
    <div id="task-bar" :style="{color: color, backgroundColor: backgroundColor}">
        <button class="btn--transparent"
                @click="backButtonPressed()">
            <i class="material-icons icon--in-text"
               style="font-size: var(--font_size_regular)"
            >arrow_back</i>
        </button>
        <span>{{viewName}}</span>
    </div>
</template>

<script>
    export default {
        name: 'Taskbar',
        props: {
            color: {
                type: String,
                default: "#212121",
            },
            backgroundColor: {
                type: String,
                default: "#FFFFFF",
            },
            viewName: {
                type: String,
                default: ''
            }
        },
        methods: {
            backButtonPressed() {
                this.$emit('backButtonPressed')
            }
        }
    }
</script>

<style lang="css" scoped>
    @import url('../../assets/global.css');
    .task-bar {
        display: flex;
    }
</style>