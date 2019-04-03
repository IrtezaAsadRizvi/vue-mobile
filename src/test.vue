<template>
    <div id="test">
        <task-bar viewName="Settings" @backButtonPress="test()" :enableFixedOnTop="true" :styles="{color: 'red'}">
            <template v-slot:left_action>
                <menu-item @click="sideMenu = !sideMenu" icon="menu"/>
            </template>
            <template v-slot:right_action>
                <menu-item @click="test" :styles="{color: 'red'}"/> <menu-item @click="bottomMenu = !bottomMenu" icon="add"/>
            </template>
        </task-bar>


        <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit, labore et dolore magna aliqua. Sit amet volutpat consequat mauris nunc congue. Facilisi morbi tempus iaculis urna id. Est placerat in egestas erat. Facilisis leo vel fringilla est ullamcorper. Turpis egestas pretium aenean pharetra magna ac placerat vestibulum lectus. Id faucibus nisl tincidunt eget nullam non nisi. Mauris sit amet massa vitae tortor condimentum lacinia. Tempus quam pellentesque nec nam aliquam. Consequat id porta nibh venenatis cras sed felis. Phasellus faucibus scelerisque eleifend donec pretium vulputate sapien nec sagittis. Est sit amet facilisis magna. Vel elit scelerisque mauris pellentesque pulvinar pellentesque. Neque convallis a cras semper auctor neque vitae tempus. Facilisis gravida neque convallis a cras semper.</p>

        <h4>List Item</h4>

        <list-item>sed do eiusmod tempor incididunt ut</list-item>
        <list-item :styles="{
            color: 'blue'
        }">sed do eiusmod tempor incididunt ut</list-item>
        <list-item>sed do eiusmod tempor incididunt ut</list-item>

        <h4>Card</h4>

        <card :styles="{color: 'red'}">Lorem ipsum dolor sit amet, consectetur adipiscing elit, labore et dolore magna aliqua. </card>
        <card>Lorem ipsum dolor sit amet, consectetur adipiscing elit, labore et dolore magna aliqua. </card>

        <h4>Buttons</h4>
        <Button :styles="{color: 'red'}">Action</Button>


        <side-menu :activeStatus="sideMenu" @close="sideMenu = false">
            <list-item>eiusmod tempor</list-item>
            <list-item>sed do</list-item>
        </side-menu>

        <bottom-menu :styles="{color: 'blue'}" :activeStatus="bottomMenu" @close="bottomMenu = false">
            sdsd
            <list-item>eiusmod tempor</list-item>
            <list-item>sed do</list-item>
        </bottom-menu>

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
            'task-bar': () => import('./components/layout/Taskbar'),
            'list-item': () => import('./components/layout/ListItem'),
            'menu-item': () => import('./components/menu/MenuItem'),
            'side-menu': () => import('./components/layout/SideMenu'),
            'bottom-menu': () => import('./components/layout/BottomMenu'),
            'card': () => import('./components/layout/Card'),
            'Button': () => import('./components/form/Button'),
        },
        mounted() {
            var viewPortTag=document.createElement('meta');
            viewPortTag.id="viewport";
            viewPortTag.name = "viewport";
            viewPortTag.content = "width=device-width, initial-scale=1.0; maximum-scale=1.0; user-scalable=0;";
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