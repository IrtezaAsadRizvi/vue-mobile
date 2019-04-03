<template>
    <div class="task-bar__container">
        <div id="task-bar"
             :class="{
              'task-bar--box-shadowed': enableBoxShadow,
              'task-bar--bordered': enableBorder,
              'task-bar--fixed-on-top': enableFixedOnTop,
             }"
             ref="component">

            <div>
                <!--action in left-->
                <slot name="left_action"></slot>

                <!--view name-->
                <span class="task-bar__view-name"
                >{{viewName}}</span>
            </div>

            <!--action in right-->
            <div style="display: flex" v-cloak>
                <slot name="right_action"></slot>
            </div>

        </div>
    </div>
</template>

<script>
    import Styleable from '../base/Styleable';

    export default {
        name: 'Taskbar',
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
        background-color: var(--color_white);
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
        margin-left: 10px;
    }
</style>