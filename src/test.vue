<template>
    <div id="test">
        <!--taskbar-->
        <vm-task-bar viewName="Settings" @backButtonPress="test()" :enableFixedOnTop="true" :styles="{color: 'red'}">
            <template v-slot:left_action>
                <menu-item @click="sideMenu = !sideMenu" icon="menu"/>
            </template>
            <template v-slot:right_action>
                <menu-item @click="test" :styles="{color: 'red'}"/> <menu-item @click="bottomMenu = !bottomMenu" icon="add"/>
            </template>
        </vm-task-bar>

    </div>
</template>

<script>
    export default {
        name: "test",
        data() {
          return {
              sideMenu: false,
              bottomMenu: false,
          }
        },
        components: {
            // layout
            'vm-task-bar': () => import('./components/layout/Taskbar'),
            'vm-list-item': () => import('./components/layout/ListItem'),
            'vm-side-menu': () => import('./components/layout/SideMenu'),
            'vm-bottom-menu': () => import('./components/layout/BottomMenu'),
            'vm-card': () => import('./components/layout/Card'),
            // menu
            'vm-menu-item': () => import('./components/menu/MenuItem'),
            // form
            'vm-button': () => import('./components/form/Button'),
            'vm-radio': () => import('./components/form/Radio'),
            // utils
            'vm-progressBar': () => import('./components/utils/ProgressBar'),
        },
        mounted() {
            var viewPortTag=document.createElement('meta');
            viewPortTag.id="viewport";
            viewPortTag.name = "viewport";
            viewPortTag.content = "width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=0";
            document.getElementsByTagName('head')[0].appendChild(viewPortTag);
        },
        methods: {
            test() {
                console.log('test: working!')
            }
        }
    }
</script>

<style>
    html, body {
        padding: 0;
        margin: 0;
    }
</style>

<style scoped>
    p, h4 {
        padding: 16px;
    }
</style>