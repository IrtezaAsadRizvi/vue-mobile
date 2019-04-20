<template>
    <div id="test">
        <!--taskbar-->
        <vm-task-bar viewName="Settings" @backButtonPress="test()" :enableFixedOnTop="true" :styles="{color: 'red'}">
            <template v-slot:left_action>
                <vm-menu-item @click="sideMenu = !sideMenu" icon="menu"/>
            </template>
            <template v-slot:right_action>
                <vm-menu-item @click="test" :styles="{color: 'red'}"/> <vm-menu-item @click="bottomMenu = !bottomMenu" icon="add"/>
            </template>
        </vm-task-bar>

        <!--side menu-->
        <vm-side-menu :activeStatus="sideMenu" @close="sideMenu = false">

        </vm-side-menu>

        <vm-bottom-menu :activeStatus="bottomMenu" @close="bottomMenu = false">
            <p>botttom menu content</p>
        </vm-bottom-menu>


        <div style="padding: 16px">
            <h5>Radio</h5>
            <vm-radio>Demo Radio</vm-radio>
            <h5>Button</h5>
            <vm-button :styles="{color: 'red'}" :activeStyles="{backgroundColor: 'blue'}">Button</vm-button>
        </div>

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
                // eslint-disable-next-line
                console.log('test');
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