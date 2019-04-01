<template>
    <div class="task-bar__container">
        <div id="task-bar"
             :class="{
              'task-bar--box-shadowed': enableBoxShadow,
              'task-bar--bordered': enableBorder,
              'task-bar--fixed-on-top': enableFixedOnTop,
         }"
             :style="{color: color, backgroundColor: backgroundColor}">

            <div>
                <!--back button-->
                <button class="btn--transparent"
                        @click="handleBackButtonPress()"
                        style="padding-left: 0; margin-right: 10px">
                    <i class="material-icons icon--in-text"
                       style="font-size: var(--font_size_semi_large)"
                    >arrow_back</i>
                </button>

                <!--view name-->
                <span class="task-bar__view-name"
                >{{viewName}}</span>
            </div>

            <!--action in right-->
            <div style="display: flex" v-cloak>
                <slot></slot>
            </div>

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
            enableFixedOnTop: {
                type: Boolean,
                default: true,
            },
            viewName: {
                type: String,
                default: ''
            },
        },
        methods: {
            handleBackButtonPress() {
                this.$emit('backButtonPress')
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
        position: relative;
    }
    .task-bar__container {
        position: relative;
        min-height: 56px;
    }
    .task-bar--box-shadowed {
        box-shadow: 0 2px 5px 0 rgba(0, 0, 0, 0.05);
    }
    .task-bar--bordered {
        border-bottom: 1px solid rgba(0, 0, 0, 0.05);
    }
    .task-bar--fixed-on-top {
        position: fixed !important;
        top: 0;
        left: 0;
        right: 0;
    }
    .task-bar__view-name {
        text-transform: capitalize;
        font-size: var(--font_size_semi_large);
    }
</style>