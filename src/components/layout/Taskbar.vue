<template>
    <div id="task-bar"
         :class="{
              'task-bar--box-shadowed': enableBoxShadow,
              'task-bar--bordered': enableBorder,
         }"
         :style="{color: color, backgroundColor: backgroundColor}">

        <div>
            <!--back button-->
            <button class="btn--transparent"
                    @click="backButtonPressed()"
                    style="padding-left: 0">
                <i class="material-icons icon--in-text"
                   style="font-size: var(--font_size_regular)"
                >arrow_back</i>
            </button>

            <!--view name-->
            <span style="text-transform: capitalize"
            >{{viewName}}</span>
        </div>

        <!--action in right-->
        <div v-cloak>
            <slot></slot>
        </div>

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
            enableBoxShadow: {
                type: Boolean,
                default: false,
            },
            enableBorder: {
                type: Boolean,
                default: true,
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
    #task-bar {
        display: flex;
        justify-content: space-between;
        padding: var(--padding_side);
    }
    .task-bar--box-shadowed {
        box-shadow: 0 2px 5px 0 rgba(0, 0, 0, 0.05);
    }
    .task-bar--bordered {
        border-bottom: 1px solid rgba(0, 0, 0, 0.05);
    }
</style>