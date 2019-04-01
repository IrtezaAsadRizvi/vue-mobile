<template>
    <div id="test">
        <task-bar viewName="Settings" @backButtonPressed="test()">yup</task-bar>
    </div>
</template>

<script>
    export default {
        name: "test",
        components: {
            'nice-handsome-button': () => import('./NiceHandsomeButton'),
            'task-bar': () => import('./components/layout/Taskbar'),
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